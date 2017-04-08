# VMware Data Queries

* Cluster Metrics Query:

```SQL
SELECT st.SAMPLE_TIME, pe.NAME AS ENTITY_NAME, (sd.GROUP_NAME + '.' + sd.NAME) AS METRIC,
COUNT(hs.STAT_VAL) AS "cnt",
AVG(CASE sd.UNIT WHEN 'percent' THEN hs.STAT_VAL/100.0 ELSE hs.STAT_VAL END) AS "avg",
SUM(CASE sd.UNIT WHEN 'percent' THEN hs.STAT_VAL/100.0 ELSE hs.STAT_VAL END) AS "sum",
MAX(CASE sd.UNIT WHEN 'percent' THEN hs.STAT_VAL/100.0 ELSE hs.STAT_VAL END) AS "max",
MIN(CASE sd.UNIT WHEN 'percent' THEN hs.STAT_VAL/100.0 ELSE hs.STAT_VAL END) AS "min"
FROM dbo.VPX_SAMPLE_TIME1 AS st (NOLOCK)
INNER JOIN dbo.VPX_HIST_STAT1 AS hs (NOLOCK)
INNER JOIN dbo.VPX_STAT_COUNTER AS sc (NOLOCK) ON hs.COUNTER_ID = sc.COUNTER_ID
INNER JOIN dbo.VPX_STAT_DEF AS sd (NOLOCK) ON sc.STAT_ID = sd.ID
INNER JOIN dbo.VPX_DEVICE AS d (NOLOCK)
LEFT OUTER JOIN dbo.VPX_STAT_DEV_TYPE AS sdt (NOLOCK) ON d.DEVICE_ID = sdt.DEVICE_ID
LEFT OUTER JOIN dbo.VPX_STAT_DEV_TYPE_DEF AS sdtd (NOLOCK)
ON sdt.DEVICE_TYPE_ID = sdtd.DEVICE_TYPE_ID ON sc.DEVICE_ID = ISNULL(d.DEVICE_ID, 1)
ON st.TIME_ID = hs.TIME_ID
INNER JOIN dbo.VPX_STAT_ID AS si (NOLOCK) ON sc.ENTITY_ID = si.ID
INNER JOIN VPXV_ENTITY_MOID em (NOLOCK) on si.MOID = em.MOID
INNER JOIN VPXV_ENTITY e (NOLOCK) on em.ENTITYID = e.id
INNER JOIN VPXV_ENTITY pe (NOLOCK) on e.parent_id = pe.id
WHERE sd.GROUP_NAME NOT IN ('sys', 'rescpu') AND st.SAMPLE_TIME > DATEADD(MINUTE, -10, ?)
AND ISNULL(d.DEVICE_ID, 1) = 1 AND e.PARENT_ENTITY_TYPE = 'CLUSTER_COMPUTE_RESOURCE'
AND sd.UNIT != 'millisecond'
GROUP BY pe.NAME, st.SAMPLE_TIME, sd.GROUP_NAME, sd.NAME, sd.UNIT
HAVING COUNT(hs.STAT_VAL) > 1
ORDER BY SAMPLE_TIME
```

* Host Metrics Query:

```SQL
SELECT st.SAMPLE_TIME, e.NAME AS ENTITY_NAME, LOWER(e.ENTITY_TYPE) AS ENTITY_TYPE,
(sd.GROUP_NAME + '.' + sd.NAME) AS METRIC, d.DEVICE_NAME,
CASE sd.UNIT WHEN 'percent' THEN hs.STAT_VAL/100.0 ELSE hs.STAT_VAL END AS STAT_VALUE
FROM dbo.VPX_SAMPLE_TIME1 AS st (NOLOCK)
INNER JOIN dbo.VPX_HIST_STAT1 AS hs (NOLOCK)
INNER JOIN dbo.VPX_STAT_COUNTER AS sc (NOLOCK) ON hs.COUNTER_ID = sc.COUNTER_ID
INNER JOIN dbo.VPX_STAT_DEF AS sd (NOLOCK) ON sc.STAT_ID = sd.ID
INNER JOIN dbo.VPX_DEVICE AS d (NOLOCK)
LEFT OUTER JOIN dbo.VPX_STAT_DEV_TYPE AS sdt (NOLOCK) ON d.DEVICE_ID = sdt.DEVICE_ID
LEFT OUTER JOIN dbo.VPX_STAT_DEV_TYPE_DEF AS sdtd (NOLOCK)
ON sdt.DEVICE_TYPE_ID = sdtd.DEVICE_TYPE_ID ON sc.DEVICE_ID = ISNULL(d.DEVICE_ID, 1)
ON st.TIME_ID = hs.TIME_ID
INNER JOIN dbo.VPX_STAT_ID AS si (NOLOCK) ON sc.ENTITY_ID = si.ID
INNER JOIN VPXV_ENTITY_MOID em (NOLOCK) on si.MOID = em.MOID
INNER JOIN VPXV_ENTITY e (NOLOCK) on em.ENTITYID = e.id
WHERE sd.GROUP_NAME != 'sys' AND e.PARENT_ID IS NOT NULL AND e.ENTITY_TYPE != 'VM' AND st.SAMPLE_TIME > DATEADD(MINUTE, -10, ?)
ORDER BY st.SAMPLE_TIME
```

* VM Metrics Query:

```SQL
SELECT st.SAMPLE_TIME, e.NAME AS ENTITY_NAME, LOWER(e.ENTITY_TYPE) AS ENTITY_TYPE,
(sd.GROUP_NAME + '.' + sd.NAME) AS METRIC, d.DEVICE_NAME,
CASE sd.UNIT WHEN 'percent' THEN hs.STAT_VAL/100.0 ELSE hs.STAT_VAL END AS STAT_VALUE
FROM dbo.VPX_SAMPLE_TIME1 AS st (NOLOCK)
INNER JOIN dbo.VPX_HIST_STAT1 AS hs (NOLOCK)
INNER JOIN dbo.VPX_STAT_COUNTER AS sc (NOLOCK) ON hs.COUNTER_ID = sc.COUNTER_ID
INNER JOIN dbo.VPX_STAT_DEF AS sd (NOLOCK) ON sc.STAT_ID = sd.ID
INNER JOIN dbo.VPX_DEVICE AS d (NOLOCK)
LEFT OUTER JOIN dbo.VPX_STAT_DEV_TYPE AS sdt (NOLOCK) ON d.DEVICE_ID = sdt.DEVICE_ID
LEFT OUTER JOIN dbo.VPX_STAT_DEV_TYPE_DEF AS sdtd (NOLOCK)
ON sdt.DEVICE_TYPE_ID = sdtd.DEVICE_TYPE_ID ON sc.DEVICE_ID = ISNULL(d.DEVICE_ID, 1)
ON st.TIME_ID = hs.TIME_ID
INNER JOIN dbo.VPX_STAT_ID AS si (NOLOCK) ON sc.ENTITY_ID = si.ID
INNER JOIN VPXV_ENTITY_MOID em (NOLOCK) on si.MOID = em.MOID
INNER JOIN VPXV_ENTITY e (NOLOCK) on em.ENTITYID = e.id
WHERE sd.GROUP_NAME != 'sys' AND e.PARENT_ID IS NOT NULL AND e.ENTITY_TYPE = 'VM' AND st.SAMPLE_TIME > DATEADD(MINUTE, -10, ?)
ORDER BY st.SAMPLE_TIME
```

* Cluster Properties Query:

```SQL
SELECT pe.NAME AS CLUSTER, vms.NAME as VM, e.NAME AS HOST, vms.POWER_STATE,
vms.MEM_SIZE_MB, vms.NUM_VCPU, vms.DESCRIPTION
FROM VPXV_ENTITY e (NOLOCK)
INNER JOIN VPXV_ENTITY pe (NOLOCK) on e.parent_id = pe.id
INNER JOIN VPXV_VMS vms (NOLOCK) on vms.hostid = e.id
WHERE e.PARENT_ENTITY_TYPE = 'CLUSTER_COMPUTE_RESOURCE' AND e.ENTITY_TYPE = 'HOST'
AND VMS.POWER_STATE = 'On'
```

* Resource Pool Properties Query:

```SQL
SELECT C.NAME, R.ALLOCATED_CPU, ALLOCATED_VM_CPU, AVAILABLE_POOL_CPU, AVAILABLE_VM_CPU,
ALLOCATED_MEM, ALLOCATED_VM_MEM, AVAILABLE_POOL_MEM,
AVAILABLE_VM_MEM, CURRENT_CPU, CURRENT_MEM, OVERALL_STATUS
FROM VPXV_RESOURCE_POOL R (NOLOCK) INNER JOIN VPXV_COMPUTE_RESOURCE C (NOLOCK) ON R.PARENT_ID = C.RESOURCEPOOLID
```

* Host Properties Query:

```SQL
SELECT NAME AS ESXHOSTNAME, * FROM VPXV_HOSTS
```

* VM Properties Query:

```SQL
SELECT REPLACE(NAME, ' ', '_') AS VMNAME, * FROM VPXV_VMS
```