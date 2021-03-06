#### Collected SCOM Metrics


## SQL Server
```css
scom.sqlserver.msas:connection.current_connections
scom.sqlserver.msas:data_mining_model_processing.current_models_processing
scom.sqlserver.msas:data_mining_prediction.concurrent_dm_queries
scom.sqlserver.msas:memory.memory_limit_high_kb
scom.sqlserver.msas:processing.rows_read_sec
scom.sqlserver.msas:processing.rows_written_sec
scom.sqlserver.msas:storage_engine_query.avg_time_query
scom.sqlserver.msas:storage_engine_query.bytes_sent_sec
scom.sqlserver.msas:storage_engine_query.rows_sent_sec
scom.sqlserver.mssql.rtc:broker_activation.stored_procedures_invoked_sec
scom.sqlserver.mssql.rtc:broker_activation.task_limit_reached
scom.sqlserver.mssql.rtc:broker_activation.task_limit_reached_sec
scom.sqlserver.mssql.rtc:broker_activation.tasks_aborted_sec
scom.sqlserver.mssql.rtc:broker_activation.tasks_started_sec
scom.sqlserver.mssql.rtc:broker_dbm_transport.message_fragment_receives_sec
scom.sqlserver.mssql.rtc:broker_dbm_transport.message_fragment_sends_sec
scom.sqlserver.mssql.rtc:broker_dbm_transport.open_connection_count
scom.sqlserver.mssql.rtc:broker_dbm_transport.receive_ios_sec
scom.sqlserver.mssql.rtc:broker_dbm_transport.send_ios_sec
scom.sqlserver.mssql.rtc:broker_statistics.broker_transaction_rollbacks
scom.sqlserver.mssql.rtc:broker_statistics.enqueued_messages_sec
scom.sqlserver.mssql.rtc:broker_statistics.enqueued_transport_msgs_sec
scom.sqlserver.mssql.rtc:broker_statistics.sql_receives_sec
scom.sqlserver.mssql.rtc:broker_statistics.sql_sends_sec
scom.sqlserver.mssql.rtc:buffer_manager.buffer_cache_hit_ratio
scom.sqlserver.mssql.rtc:databases.transactions_sec
scom.sqlserver.mssql.rtc:general_statistics.logins_sec
scom.sqlserver.mssql.rtc:general_statistics.user_connections
scom.sqlserver.mssql.rtc:locks.average_wait_time_ms
scom.sqlserver.mssql.rtc:locks.lock_requests_sec
scom.sqlserver.mssql.rtc:locks.lock_timeouts_sec
scom.sqlserver.mssql.rtc:locks.lock_waits_sec
scom.sqlserver.mssql.rtc:locks.number_of_deadlocks_sec
scom.sqlserver.mssql.rtc:sql_statistics.sql_compilations_sec
scom.sqlserver.mssql.rtc:sql_statistics.sql_re-compilations_sec
scom.sqlserver.mssql.rtc:transactionlog.log_free_space_%
scom.sqlserver.mssql.rtc_database.db_active_connections
scom.sqlserver.mssql.rtc_database.db_active_requests
scom.sqlserver.mssql.rtc_database.db_active_sessions
scom.sqlserver.mssql.rtc_database.db_active_transactions
scom.sqlserver.mssql.rtc_database.db_allocated_size_mb
scom.sqlserver.mssql.rtc_database.db_avg_disk_ms_read
scom.sqlserver.mssql.rtc_database.db_avg_disk_ms_write
scom.sqlserver.mssql.rtc_database.db_total_free_space_%
scom.sqlserver.mssql.rtc_database.db_total_free_space_mb
scom.sqlserver.mssql.rtc_database.db_transactions_sec
scom.sqlserver.mssql.rtc_database_db_log_file.db_log_file_allocated_space_left_%
scom.sqlserver.mssql.rtc_database_db_log_file.db_log_file_allocated_space_left_mb
scom.sqlserver.mssql.rtc_database_db_log_file.db_log_file_free_space_%
scom.sqlserver.mssql.rtc_database_db_log_file.db_log_file_free_space_mb
scom.sqlserver.mssql.rtc_database_file_group.db_file_group_allocated_space_left_%
scom.sqlserver.mssql.rtc_database_file_group.db_file_group_allocated_space_left_mb
scom.sqlserver.mssql.rtc_database_file_group.db_file_group_free_space_%
scom.sqlserver.mssql.rtc_database_file_group.db_file_group_free_space_mb
scom.sqlserver.mssql.rtc_database_file_group_db_file.db_file_allocated_space_left_%
scom.sqlserver.mssql.rtc_database_file_group_db_file.db_file_allocated_space_left_mb
scom.sqlserver.mssql.rtc_database_file_group_db_file.db_file_free_space_%
scom.sqlserver.mssql.rtc_database_file_group_db_file.db_file_free_space_mb
scom.sqlserver.mssqlserver_buffer_manager.stolen_server_memory_mb
scom.sqlserver.rtc_buffer_manager.stolen_server_memory_mb
scom.sqlserver.sqlserver.cpu_usage
scom.sqlserver.sqlserver.page_life_expectancy
scom.sqlserver.sqlserver.thread_count
scom.sqlserver.sqlserver:broker_activation.stored_procedures_invoked_sec
scom.sqlserver.sqlserver:broker_activation.task_limit_reached
scom.sqlserver.sqlserver:broker_activation.task_limit_reached_sec
scom.sqlserver.sqlserver:broker_activation.tasks_aborted_sec
scom.sqlserver.sqlserver:broker_activation.tasks_started_sec
scom.sqlserver.sqlserver:broker_dbm_transport.message_fragment_receives_sec
scom.sqlserver.sqlserver:broker_dbm_transport.message_fragment_sends_sec
scom.sqlserver.sqlserver:broker_dbm_transport.open_connection_count
scom.sqlserver.sqlserver:broker_dbm_transport.receive_ios_sec
scom.sqlserver.sqlserver:broker_dbm_transport.send_ios_sec
scom.sqlserver.sqlserver:broker_statistics.broker_transaction_rollbacks
scom.sqlserver.sqlserver:broker_statistics.enqueued_messages_sec
scom.sqlserver.sqlserver:broker_statistics.enqueued_transport_msgs_sec
scom.sqlserver.sqlserver:broker_statistics.sql_receives_sec
scom.sqlserver.sqlserver:broker_statistics.sql_sends_sec
scom.sqlserver.sqlserver:buffer_manager.buffer_cache_hit_ratio
scom.sqlserver.sqlserver:databases.transactions_sec
scom.sqlserver.sqlserver:general_statistics.logins_sec
scom.sqlserver.sqlserver:general_statistics.user_connections
scom.sqlserver.sqlserver:locks.average_wait_time_ms
scom.sqlserver.sqlserver:locks.lock_requests_sec
scom.sqlserver.sqlserver:locks.lock_timeouts_sec
scom.sqlserver.sqlserver:locks.lock_waits_sec
scom.sqlserver.sqlserver:locks.number_of_deadlocks_sec
scom.sqlserver.sqlserver:sql_statistics.sql_compilations_sec
scom.sqlserver.sqlserver:sql_statistics.sql_re-compilations_sec
scom.sqlserver.sqlserver:ssis_pipeline_10.0.buffers_spooled
scom.sqlserver.sqlserver:ssis_pipeline_10.0.rows_read
scom.sqlserver.sqlserver:ssis_pipeline_10.0.rows_written
scom.sqlserver.sqlserver:transactionlog.log_free_space_%
scom.sqlserver.sqlserver_database.db_active_connections
scom.sqlserver.sqlserver_database.db_active_requests
scom.sqlserver.sqlserver_database.db_active_sessions
scom.sqlserver.sqlserver_database.db_active_transactions
scom.sqlserver.sqlserver_database.db_allocated_size_mb
scom.sqlserver.sqlserver_database.db_avg_disk_ms_read
scom.sqlserver.sqlserver_database.db_avg_disk_ms_write
scom.sqlserver.sqlserver_database.db_total_free_space_%
scom.sqlserver.sqlserver_database.db_total_free_space_mb
scom.sqlserver.sqlserver_database.db_transactions_sec
scom.sqlserver.sqlserver_database_db_log_file.db_log_file_allocated_space_left_%
scom.sqlserver.sqlserver_database_db_log_file.db_log_file_allocated_space_left_mb
scom.sqlserver.sqlserver_database_db_log_file.db_log_file_free_space_%
scom.sqlserver.sqlserver_database_db_log_file.db_log_file_free_space_mb
scom.sqlserver.sqlserver_database_file_group.db_file_group_allocated_space_left_%
scom.sqlserver.sqlserver_database_file_group.db_file_group_allocated_space_left_mb
scom.sqlserver.sqlserver_database_file_group.db_file_group_free_space_%
scom.sqlserver.sqlserver_database_file_group.db_file_group_free_space_mb
scom.sqlserver.sqlserver_database_file_group_db_file.db_file_allocated_space_left_%
scom.sqlserver.sqlserver_database_file_group_db_file.db_file_allocated_space_left_mb
scom.sqlserver.sqlserver_database_file_group_db_file.db_file_free_space_%
scom.sqlserver.sqlserver_database_file_group_db_file.db_file_free_space_mb
```

## Active Directory

```css
scom.ad.directoryservices.dra_inbound_bytes_compressed_between_sites_after_compression_sec
scom.ad.directoryservices.dra_inbound_bytes_compressed_between_sites_before_compression_sec
scom.ad.directoryservices.dra_inbound_bytes_not_compressed_within_site_sec
scom.ad.directoryservices.dra_inbound_bytes_total_sec
scom.ad.directoryservices.dra_outbound_bytes_compressed_between_sites_after_compression_sec
scom.ad.directoryservices.dra_outbound_bytes_compressed_between_sites_before_compression_sec
scom.ad.directoryservices.dra_outbound_bytes_not_compressed_within_site_sec
scom.ad.directoryservices.dra_outbound_bytes_total_sec
scom.ad.directoryservices.ds_search_sub-operations_sec
scom.ad.directoryservices.ldap_client_sessions
scom.ad.directoryservices.ldap_searches_sec
scom.ad.directoryservices.ldap_udp_operations_sec
scom.ad.directoryservices.ldap_writes_sec
scom.ad.domain_naming_op_master.op_master_domain_naming_last_bind
scom.ad.domain_naming_op_master.op_master_domain_naming_last_ping
scom.ad.general_response.active_directory_last_bind
scom.ad.general_response.global_catalog_search_time
scom.ad.infrastructure_op_master.op_master_infrastructure_last_bind
scom.ad.infrastructure_op_master.op_master_infrastructure_last_ping
scom.ad.library.ad_storage.database_drive_free_space
scom.ad.library.ad_storage.database_size
scom.ad.library.ad_storage.log_file_drive_free_space
scom.ad.library.ad_storage.log_file_size
scom.ad.memory.available_bytes
scom.ad.memory.committed_bytes
scom.ad.memory.pages_sec
scom.ad.pdc_op_master.op_master_pdc_last_bind
scom.ad.pdc_op_master.op_master_pdc_last_ping
scom.ad.process.%_processor_time
scom.ad.process.handle_count
scom.ad.process.private_bytes
scom.ad.processor.%_processor_time
scom.ad.rid_op_master.op_master_rid_last_bind
scom.ad.rid_op_master.op_master_rid_last_ping
scom.ad.schema_op_master.op_master_schema_last_bind
scom.ad.schema_op_master.op_master_schema_last_ping
scom.ad.security_system-wide_statistics.kdc_as_requests
scom.ad.security_system-wide_statistics.kdc_tgs_requests
scom.ad.security_system-wide_statistics.kerberos_authentications
scom.ad.security_system-wide_statistics.ntlm_authentications
scom.ad.server.server_sessions
scom.ad.system.system_up_time
scom.ad.tcpv4.connections_established
scom.ad.tcpv6.connections_established
```

## SCOM Windows Server

```css
scom.server.logicaldisk.%_free_space
scom.server.logicaldisk.%_idle_time
scom.server.logicaldisk.avg_disk_sec_transfer
scom.server.logicaldisk.current_disk_queue_length
scom.server.logicaldisk.free_megabytes
scom.server.memory.%_committed_bytes_in_use
scom.server.memory.available_mbytes
scom.server.memory.free_system_page_table_entries
scom.server.memory.pages_sec
scom.server.memory.percentmemoryused
scom.server.memory.pool_nonpaged_bytes
scom.server.memory.pool_paged_bytes
scom.server.network_adapter.percentbandwidthusedtotal
scom.server.network_interface.bytes_total_sec
scom.server.network_interface.current_bandwidth
scom.server.paging_file.%_usage
scom.server.processor.%_interrupt_time
scom.server.processor.%_processor_time
scom.server.processor_information.%_processor_time
scom.server.system.processor_queue_length
```


## System Center

```css
scom.systemcenter.datawarehouse.opsmgr_dw_synchronization_module.avg_batch_processing_time_ms
scom.systemcenter.datawarehouse.opsmgr_dw_synchronization_module.avg_batch_size
scom.systemcenter.datawarehouse.opsmgr_dw_synchronization_module.batch_age_sec
scom.systemcenter.datawarehouse.opsmgr_dw_synchronization_module.batch_size
scom.systemcenter.datawarehouse.opsmgr_dw_synchronization_module.batches_sec
scom.systemcenter.datawarehouse.opsmgr_dw_synchronization_module.data_items_sec
scom.systemcenter.datawarehouse.opsmgr_dw_synchronization_module.errors_sec
scom.systemcenter.datawarehouse.opsmgr_dw_synchronization_module.total_error_count
scom.systemcenter.datawarehouse.opsmgr_dw_writer_module.avg_batch_processing_time_ms
scom.systemcenter.datawarehouse.opsmgr_dw_writer_module.avg_batch_size
scom.systemcenter.datawarehouse.opsmgr_dw_writer_module.batches_sec
scom.systemcenter.datawarehouse.opsmgr_dw_writer_module.data_items_sec
scom.systemcenter.datawarehouse.opsmgr_dw_writer_module.dropped_batch_count
scom.systemcenter.datawarehouse.opsmgr_dw_writer_module.dropped_data_item_count
scom.systemcenter.datawarehouse.opsmgr_dw_writer_module.errors_sec
scom.systemcenter.datawarehouse.opsmgr_dw_writer_module.total_error_count
scom.systemcenter.health_service.active_file_uploads
scom.systemcenter.health_service.agent_processor_utilization
scom.systemcenter.health_service.module_count
scom.systemcenter.health_service.workflow_count
scom.systemcenter.health_service_management_groups.bind_data_source_item_drop_rate
scom.systemcenter.health_service_management_groups.bind_data_source_item_incoming_rate
scom.systemcenter.health_service_management_groups.send_queue_%_used
scom.systemcenter.health_service_management_groups.send_queue_size
scom.systemcenter.ntservice.library.process.handle_count
scom.systemcenter.ntservice.library.process.percent_processor_time
scom.systemcenter.ntservice.library.process.private_bytes
scom.systemcenter.ntservice.library.process.thread_count
scom.systemcenter.ntservice.library.process.working_set
scom.systemcenter.operationsmanager.dataaccessservice.opsmgr_sdk_service.client_connections
scom.systemcenter.operationsmanager.defaultuser.paging_file.%_usage
scom.systemcenter.operationsmanager.defaultuser.paging_file.%_usage_peak
scom.systemcenter.opsmgr_config_service.number_of_queued_requests
scom.systemcenter.opsmgr_db_write_action_modules.avg_batch_size
scom.systemcenter.opsmgr_db_write_action_modules.avg_processing_time
scom.systemcenter.opsmgr_sdk_service.client_connections
scom.systemcenter.system.system_up_time
```
