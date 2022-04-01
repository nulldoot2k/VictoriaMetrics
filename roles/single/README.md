# VM single

Installs VictoriaMetrics single binary running with systemd

## Parameters

See full list at [defaults.yml](./defaults/main.yml)

| Parameter                                 | Description                                            | Default                                                                                                                                       |
|-------------------------------------------|--------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| victoriametrics_repo_url                  | Repository to get binaries                             | `https://github.com/VictoriaMetrics/VictoriaMetrics`                                                                                          |
| victoriametrics_version                   | Version to install                                     | `v1.75.0`                                                                                                                                     |
| victoriametrics_download_url              | Resulting download url.                                | `"{{ victoriametrics_repo_url }}/releases/download/{{ victoriametrics_version }}/vmutils-{{ go_arch }}-{{ victoriametrics_version }}.tar.gz"` |
| victoriametrics_utils_download_url        | Resulting download url.                                | `"{{ victoriametrics_repo_url }}/releases/download/{{ victoriametrics_version }}/vmutils-{{ go_arch }}-{{ victoriametrics_version }}.tar.gz"` |
| victoriametrics_system_user               | User to run service.                                   | `victoriametrics`                                                                                                                             |
| victoriametrics_system_group              | Group to run service.                                  | `{{ victoriametrics_system_user }}`                                                                                                           |
| victoriametrics_data_dir                  | Directory to store data configs.                       | `/var/lib/victoria-metrics/`                                                                                                                  |
| victoriametrics_backup_enabled            | Enable usage of `vmbackup` to backup to S3 .           | `false`                                                                                                                                       |
| victoriametrics_backup_destination        | S3 backups destination.                                | `s3://`                                                                                                                                       |
| victoriametrics_backup_cron_hour          | Backups schedule.                                      | `*/2`                                                                                                                                         |
| victoriametrics_backup_access_key         | S3 access key.                                         | ``                                                                                                                                            |
| victoriametrics_backup_secret_key         | S3 secret key.                                         | ``                                                                                                                                            |
| victoriametrics_backup_custom_s3_endpoint | Custom S3 endpoint(useful for S3-compatible services). | ``                                                                                                                                            |
| victoriametrics_service_args              | Passes options defined above to single.                | see [defaults.yml](./defaults/main.yml)                                                                                                       |
