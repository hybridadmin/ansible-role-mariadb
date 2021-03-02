## mysql

> A role to install mysql/mariadb on supported distros.

## Requirements

None.

## Role Variables

The variables below can be edited in [`defaults/main.yml`](defaults/main.yml) to customize the deployment:


### MySQL installation settings
```yaml
mysql_install_settings:
  use_mariadb: false
  version: 8.0
  root_password: ''
```

### Configuration settings
```yaml
mysql_conf_settings:
  port: 3306
  bind_address: "127.0.0.1"
  datadir: "/var/lib/mysql/"
  socket: "/var/run/mysqld/mysqld.sock"
  pid_file: "/var/run/mysqld/mysqld.pid"
  skip_name_resolve: false
  sql_mode: ''
  log_error: ''
  slow_query_log_file: '/var/log/mysql/mysql-slow.log'
  slow_query_time: 2
  key_buffer_size: "256M"
  max_allowed_packet: "64M"
  table_open_cache: 256
  sort_buffer_size: "1M"
  read_buffer_size: "1M"
  read_rnd_buffer_size: "4M"
  myisam_sort_buffer_size: "64M"
  thread_cache_size: 8
  query_cache_type: 0
  query_cache_size: "16M"
  query_cache_limit: "1M"
  max_connections: 150
  tmp_table_size: "16M"
  max_heap_table_size: "16M"
  group_concat_max_len: 1024
  join_buffer_size: 262144
  wait_timeout: 28800
  lower_case_table_names: 0
  event_scheduler_state: "OFF"
  binlog_format: "ROW"
  innodb_file_per_table: 1
  innodb_buffer_pool_size: "1G"
  innodb_log_file_size: "256M"
  innodb_log_buffer_size: "128M"
  innodb_flush_log_at_trx_commit: 1
  innodb_lock_wait_timeout: 50
  innodb_flush_method: "O_DIRECT"
  innodb_autoinc_lock_mode: 2
  innodb_thread_concurrency: 0
  innodb_stats_on_metadata: "OFF"
  innodb_buffer_pool_instances: 1
```

### Cluster installation settings
```yaml
galera_cluster_settings:
  enabled: true
  wsrep_sst_method: rsync
  wsrep_provider_options: "gcache.size=300M; gcache.page_size=300M"
  wsrep_cluster_name: "GaleraCluster"
```


## Dependencies

None.

## Example Playbook

An example playbook is included below:

```yaml
    - hosts: servers
      roles:
         - { role: hybridadmin.mysql }
```


## License

[`Apache License 2.0`](./LICENSE)


## Author Information

Created by [`hybridadmin`](https://github.com/hybridadmin)
