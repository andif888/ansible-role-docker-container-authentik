# ansible-role-docker-container-authentik

Role to run authentik in a docker container

## Table of content

- [Requirements](#requirements)
- [Default Variables](#default-variables)
  - [docker_container_authentik_command](#docker_container_authentik_command)
  - [docker_container_authentik_comparisons](#docker_container_authentik_comparisons)
  - [docker_container_authentik_database_name](#docker_container_authentik_database_name)
  - [docker_container_authentik_database_password](#docker_container_authentik_database_password)
  - [docker_container_authentik_database_user](#docker_container_authentik_database_user)
  - [docker_container_authentik_env](#docker_container_authentik_env)
  - [docker_container_authentik_image](#docker_container_authentik_image)
  - [docker_container_authentik_labels](#docker_container_authentik_labels)
  - [docker_container_authentik_name](#docker_container_authentik_name)
  - [docker_container_authentik_networks](#docker_container_authentik_networks)
  - [docker_container_authentik_ports](#docker_container_authentik_ports)
  - [docker_container_authentik_restic_enable](#docker_container_authentik_restic_enable)
  - [docker_container_authentik_restic_retention](#docker_container_authentik_restic_retention)
  - [docker_container_authentik_restic_s3_bucket_name](#docker_container_authentik_restic_s3_bucket_name)
  - [docker_container_authentik_restic_s3_endpoint](#docker_container_authentik_restic_s3_endpoint)
  - [docker_container_authentik_restic_s3_repo](#docker_container_authentik_restic_s3_repo)
  - [docker_container_authentik_restic_s3_repo_access_key](#docker_container_authentik_restic_s3_repo_access_key)
  - [docker_container_authentik_restic_s3_repo_password](#docker_container_authentik_restic_s3_repo_password)
  - [docker_container_authentik_restic_s3_repo_secret_key](#docker_container_authentik_restic_s3_repo_secret_key)
  - [docker_container_authentik_restic_tag](#docker_container_authentik_restic_tag)
  - [docker_container_authentik_secret_key](#docker_container_authentik_secret_key)
  - [docker_container_authentik_volume_dir](#docker_container_authentik_volume_dir)
  - [docker_container_authentik_volumes](#docker_container_authentik_volumes)
  - [docker_container_authentikdb_comparisons](#docker_container_authentikdb_comparisons)
  - [docker_container_authentikdb_env](#docker_container_authentikdb_env)
  - [docker_container_authentikdb_healthcheck](#docker_container_authentikdb_healthcheck)
  - [docker_container_authentikdb_image](#docker_container_authentikdb_image)
  - [docker_container_authentikdb_labels](#docker_container_authentikdb_labels)
  - [docker_container_authentikdb_name](#docker_container_authentikdb_name)
  - [docker_container_authentikdb_networks](#docker_container_authentikdb_networks)
  - [docker_container_authentikdb_ports](#docker_container_authentikdb_ports)
  - [docker_container_authentikdb_volume_dir](#docker_container_authentikdb_volume_dir)
  - [docker_container_authentikdb_volumes](#docker_container_authentikdb_volumes)
  - [docker_container_authentikredis_command](#docker_container_authentikredis_command)
  - [docker_container_authentikredis_comparisons](#docker_container_authentikredis_comparisons)
  - [docker_container_authentikredis_env](#docker_container_authentikredis_env)
  - [docker_container_authentikredis_healthcheck](#docker_container_authentikredis_healthcheck)
  - [docker_container_authentikredis_image](#docker_container_authentikredis_image)
  - [docker_container_authentikredis_labels](#docker_container_authentikredis_labels)
  - [docker_container_authentikredis_name](#docker_container_authentikredis_name)
  - [docker_container_authentikredis_networks](#docker_container_authentikredis_networks)
  - [docker_container_authentikredis_ports](#docker_container_authentikredis_ports)
  - [docker_container_authentikredis_volume_dir](#docker_container_authentikredis_volume_dir)
  - [docker_container_authentikredis_volumes](#docker_container_authentikredis_volumes)
  - [docker_container_authentikworker_command](#docker_container_authentikworker_command)
  - [docker_container_authentikworker_comparisons](#docker_container_authentikworker_comparisons)
  - [docker_container_authentikworker_env](#docker_container_authentikworker_env)
  - [docker_container_authentikworker_image](#docker_container_authentikworker_image)
  - [docker_container_authentikworker_labels](#docker_container_authentikworker_labels)
  - [docker_container_authentikworker_name](#docker_container_authentikworker_name)
  - [docker_container_authentikworker_networks](#docker_container_authentikworker_networks)
  - [docker_container_authentikworker_ports](#docker_container_authentikworker_ports)
  - [docker_container_authentikworker_volume_dir](#docker_container_authentikworker_volume_dir)
  - [docker_container_authentikworker_volumes](#docker_container_authentikworker_volumes)
  - [docker_image_authentik_name](#docker_image_authentik_name)
  - [docker_image_authentik_pull](#docker_image_authentik_pull)
  - [docker_image_authentikdb_name](#docker_image_authentikdb_name)
  - [docker_image_authentikdb_pull](#docker_image_authentikdb_pull)
  - [docker_image_authentikredis_name](#docker_image_authentikredis_name)
  - [docker_image_authentikredis_pull](#docker_image_authentikredis_pull)
  - [docker_image_authentikworker_name](#docker_image_authentikworker_name)
  - [docker_image_authentikworker_pull](#docker_image_authentikworker_pull)
  - [docker_network_authentik_name](#docker_network_authentik_name)
  - [docker_network_authentikdb_name](#docker_network_authentikdb_name)
  - [docker_network_authentikredis_name](#docker_network_authentikredis_name)
  - [docker_network_authentikworker_name](#docker_network_authentikworker_name)
- [Discovered Tags](#discovered-tags)
- [Dependencies](#dependencies)
- [License](#license)
- [Author](#author)

---

## Requirements

- Minimum Ansible version: `2.1`

## Default Variables

### docker_container_authentik_command

#### Default value

```YAML
docker_container_authentik_command: server
```

### docker_container_authentik_comparisons

Allows to specify how properties of existing containers are compared with module options
to decide whether the container should be recreated / updated or not.

#### Default value

```YAML
docker_container_authentik_comparisons:
  image: strict
  env: strict
  volumes: strict
```

### docker_container_authentik_database_name

Name of the database.

#### Default value

```YAML
docker_container_authentik_database_name: authentik
```

### docker_container_authentik_database_password

Password of the database user.

#### Default value

```YAML
docker_container_authentik_database_password: authentiksomethingsecret8888
```

### docker_container_authentik_database_user

Name of the database user.

#### Default value

```YAML
docker_container_authentik_database_user: authentik
```

### docker_container_authentik_env

Dictionery of key,value pairs for docker
environment variables to configure authentik.

#### Default value

```YAML
docker_container_authentik_env:
  AUTHENTIK_REDIS__HOST: redis
  AUTHENTIK_POSTGRESQL__HOST: db
  AUTHENTIK_POSTGRESQL__USER: '{{ docker_container_authentik_database_user }}'
  AUTHENTIK_POSTGRESQL__NAME: '{{ docker_container_authentik_database_name }}'
  AUTHENTIK_POSTGRESQL__PASSWORD: '{{ docker_container_authentik_database_password
    }}'
  AUTHENTIK_SECRET_KEY: '{{ docker_container_authentik_secret_key }}'
```

### docker_container_authentik_image

Repository path and tag used to create the container.
If an image is not found or pull is true, the image will be pulled from the registry.
If no tag is included, latest will be used.

#### Default value

```YAML
docker_container_authentik_image: '{{ docker_image_authentik_name }}'
```

### docker_container_authentik_labels

Dictionary of key value pairs for container labels.

Example:

```yaml

docker_container_authentik_labels:

traefik.enable: "true"

```

#### Default value

```YAML
docker_container_authentik_labels: {}
```

### docker_container_authentik_name

Name for the container

#### Default value

```YAML
docker_container_authentik_name: authentik
```

### docker_container_authentik_networks

List of networks the container belongs to.

#### Default value

```YAML
docker_container_authentik_networks:
  - name: '{{ docker_network_authentik_name }}'
    links:
      - '{{ docker_container_authentikdb_name }}:db'
      - '{{ docker_container_authentikredis_name }}:redis'
```

### docker_container_authentik_ports

List of ports to publish from the container to the host.

#### Default value

```YAML
docker_container_authentik_ports:
  - 9000:9000
  - 9443:9443
```

### docker_container_authentik_restic_enable

Enable restic backup for the container's mounted volumes.

#### Default value

```YAML
docker_container_authentik_restic_enable: false
```

### docker_container_authentik_restic_retention

Retention settions for `restic forget` after the `restic backup`.

#### Default value

```YAML
docker_container_authentik_restic_retention:
  keep_last: 1
  keep_daily: 7
  keep_weekly: 4
```

### docker_container_authentik_restic_s3_bucket_name

Minio S3 bucket name for restic backup storage.

#### Default value

```YAML
docker_container_authentik_restic_s3_bucket_name: restic-{{ docker_container_authentik_name
  }}
```

### docker_container_authentik_restic_s3_endpoint

Minio S3 endpoint for restic backup storage.

Example:

```yaml

docker_container__base__restic_s3_endpoint: "https://minio.{{ dns_domain }}"

docker_container_authentik_restic_s3_endpoint: "{{ docker_container__base__restic_s3_endpoint }}"

```

#### Default value

```YAML
docker_container_authentik_restic_s3_endpoint: '{{ docker_container__base__restic_s3_endpoint
  }}'
```

### docker_container_authentik_restic_s3_repo

Minio S3 repo URL for restic backup storage.

#### Default value

```YAML
docker_container_authentik_restic_s3_repo: s3:{{ docker_container_authentik_restic_s3_endpoint
  }}/{{ docker_container_authentik_restic_s3_bucket_name }}
```

### docker_container_authentik_restic_s3_repo_access_key

Minio S3 repo access key for restic backup storage.

#### Default value

```YAML
docker_container_authentik_restic_s3_repo_access_key: '{{ docker_container__base__restic_s3_repo_access_key
  }}'
```

### docker_container_authentik_restic_s3_repo_password

Minio S3 repo password for restic backup storage.

#### Default value

```YAML
docker_container_authentik_restic_s3_repo_password: '{{ docker_container__base__restic_s3_repo_password
  }}'
```

### docker_container_authentik_restic_s3_repo_secret_key

Minio S3 repo secret key for restic backup storage.

#### Default value

```YAML
docker_container_authentik_restic_s3_repo_secret_key: '{{ docker_container__base__restic_s3_repo_secret_key
  }}'
```

### docker_container_authentik_restic_tag

Tag for the `restic backup` command

#### Default value

```YAML
docker_container_authentik_restic_tag: '{{ docker_container_authentik_name }}'
```

### docker_container_authentik_secret_key

Secret key.

#### Default value

```YAML
docker_container_authentik_secret_key: MZcPm6VeXTbJAot9E8p1fqxN/fbz+8EMUjbRNcnI2NfeFU0uv5q4hNKgS/x7xOPhXnw7etY5qxEg6lXg
```

### docker_container_authentik_volume_dir

Volume mount host directory, where Treafik config files are stored.

#### Default value

```YAML
docker_container_authentik_volume_dir: '{{ docker_container__base__volume_dir }}/{{
  docker_container_authentik_name }}'
```

### docker_container_authentik_volumes

List of volumes to mount within the container.

#### Default value

```YAML
docker_container_authentik_volumes:
  - '{{ docker_container_authentik_volume_dir }}/media:/media'
  - '{{ docker_container_authentik_volume_dir }}/custom-templates:/templates'
```

### docker_container_authentikdb_comparisons

Allows to specify how properties of existing containers are compared with module options
to decide whether the container should be recreated / updated or not.

#### Default value

```YAML
docker_container_authentikdb_comparisons:
  image: strict
  env: strict
  volumes: strict
```

### docker_container_authentikdb_env

Dictionery of key,value pairs for docker
environment variables to configure authentikdb.

#### Default value

```YAML
docker_container_authentikdb_env:
  POSTGRES_PASSWORD: '{{ docker_container_authentik_database_password }}'
  POSTGRES_USER: '{{ docker_container_authentik_database_user }}'
  POSTGRES_DB: '{{ docker_container_authentik_database_name }}'
```

### docker_container_authentikdb_healthcheck

#### Default value

```YAML
docker_container_authentikdb_healthcheck:
  test: [CMD-SHELL, 'pg_isready -d {{ docker_container_authentik_database_name }}
        -U {{ docker_container_authentik_database_user }}']
  start_period: 20s
  interval: 30s
  retries: 5
  timeout: 5s
```

### docker_container_authentikdb_image

Repository path and tag used to create the container.
If an image is not found or pull is true, the image will be pulled from the registry.
If no tag is included, latest will be used.

#### Default value

```YAML
docker_container_authentikdb_image: '{{ docker_image_authentikdb_name }}'
```

### docker_container_authentikdb_labels

Dictionary of key value pairs for container labels.

Example:

```yaml

docker_container_authentikdb_labels:

traefik.enable: "true"

```

#### Default value

```YAML
docker_container_authentikdb_labels: {}
```

### docker_container_authentikdb_name

Name for the container

#### Default value

```YAML
docker_container_authentikdb_name: authentikdb
```

### docker_container_authentikdb_networks

List of networks the container belongs to.

#### Default value

```YAML
docker_container_authentikdb_networks:
  - name: '{{ docker_network_authentikdb_name }}'
```

### docker_container_authentikdb_ports

List of ports to publish from the container to the host.

#### Default value

```YAML
docker_container_authentikdb_ports: []
```

### docker_container_authentikdb_volume_dir

Volume mount host directory, where Treafik config files are stored.

#### Default value

```YAML
docker_container_authentikdb_volume_dir: '{{ docker_container__base__volume_dir }}/{{
  docker_container_authentik_name }}'
```

### docker_container_authentikdb_volumes

List of volumes to mount within the container.

#### Default value

```YAML
docker_container_authentikdb_volumes:
  - '{{ docker_container_authentik_volume_dir }}/postgres:/var/lib/postgresql/data'
```

### docker_container_authentikredis_command

#### Default value

```YAML
docker_container_authentikredis_command: --save 60 1 --loglevel warning
```

### docker_container_authentikredis_comparisons

Allows to specify how properties of existing containers are compared with module options
to decide whether the container should be recreated / updated or not.

#### Default value

```YAML
docker_container_authentikredis_comparisons:
  image: strict
  env: strict
  volumes: strict
```

### docker_container_authentikredis_env

Dictionery of key,value pairs for docker
environment variables to configure authentikredis.

#### Default value

```YAML
docker_container_authentikredis_env: {}
```

### docker_container_authentikredis_healthcheck

#### Default value

```YAML
docker_container_authentikredis_healthcheck:
  test: [CMD-SHELL, redis-cli ping | grep PONG]
  start_period: 20s
  interval: 30s
  retries: 5
  timeout: 3s
```

### docker_container_authentikredis_image

Repository path and tag used to create the container.
If an image is not found or pull is true, the image will be pulled from the registry.
If no tag is included, latest will be used.

#### Default value

```YAML
docker_container_authentikredis_image: '{{ docker_image_authentikredis_name }}'
```

### docker_container_authentikredis_labels

Dictionary of key value pairs for container labels.

Example:

```yaml

docker_container_authentikredis_labels:

traefik.enable: "true"

```

#### Default value

```YAML
docker_container_authentikredis_labels: {}
```

### docker_container_authentikredis_name

Name for the container

#### Default value

```YAML
docker_container_authentikredis_name: authentikredis
```

### docker_container_authentikredis_networks

List of networks the container belongs to.

#### Default value

```YAML
docker_container_authentikredis_networks:
  - name: '{{ docker_network_authentikredis_name }}'
```

### docker_container_authentikredis_ports

List of ports to publish from the container to the host.

#### Default value

```YAML
docker_container_authentikredis_ports: []
```

### docker_container_authentikredis_volume_dir

Volume mount host directory, where Treafik config files are stored.

#### Default value

```YAML
docker_container_authentikredis_volume_dir: '{{ docker_container__base__volume_dir
  }}/{{ docker_container_authentik_name }}'
```

### docker_container_authentikredis_volumes

List of volumes to mount within the container.

#### Default value

```YAML
docker_container_authentikredis_volumes: []
```

### docker_container_authentikworker_command

#### Default value

```YAML
docker_container_authentikworker_command: worker
```

### docker_container_authentikworker_comparisons

Allows to specify how properties of existing containers are compared with module options
to decide whether the container should be recreated / updated or not.

#### Default value

```YAML
docker_container_authentikworker_comparisons:
  image: strict
  env: strict
  volumes: strict
```

### docker_container_authentikworker_env

Dictionery of key,value pairs for docker
environment variables to configure authentikworker.

#### Default value

```YAML
docker_container_authentikworker_env:
  AUTHENTIK_REDIS__HOST: redis
  AUTHENTIK_POSTGRESQL__HOST: db
  AUTHENTIK_POSTGRESQL__USER: '{{ docker_container_authentik_database_user }}'
  AUTHENTIK_POSTGRESQL__NAME: '{{ docker_container_authentik_database_name }}'
  AUTHENTIK_POSTGRESQL__PASSWORD: '{{ docker_container_authentik_database_password
    }}'
  AUTHENTIK_SECRET_KEY: '{{ docker_container_authentik_secret_key }}'
```

### docker_container_authentikworker_image

Repository path and tag used to create the container.
If an image is not found or pull is true, the image will be pulled from the registry.
If no tag is included, latest will be used.

#### Default value

```YAML
docker_container_authentikworker_image: '{{ docker_image_authentikworker_name }}'
```

### docker_container_authentikworker_labels

Dictionary of key value pairs for container labels.

Example:

```yaml

docker_container_authentikworker_labels:

traefik.enable: "true"

```

#### Default value

```YAML
docker_container_authentikworker_labels: {}
```

### docker_container_authentikworker_name

Name for the container

#### Default value

```YAML
docker_container_authentikworker_name: authentikworker
```

### docker_container_authentikworker_networks

List of networks the container belongs to.

#### Default value

```YAML
docker_container_authentikworker_networks:
  - name: '{{ docker_network_authentikworker_name }}'
    links:
      - '{{ docker_container_authentikdb_name }}:db'
      - '{{ docker_container_authentikredis_name }}:redis'
```

### docker_container_authentikworker_ports

List of ports to publish from the container to the host.

#### Default value

```YAML
docker_container_authentikworker_ports: []
```

### docker_container_authentikworker_volume_dir

Volume mount host directory, where Treafik config files are stored.

#### Default value

```YAML
docker_container_authentikworker_volume_dir: '{{ docker_container__base__volume_dir
  }}/{{ docker_container_authentik_name }}'
```

### docker_container_authentikworker_volumes

List of volumes to mount within the container.

#### Default value

```YAML
docker_container_authentikworker_volumes:
  - /var/run/docker.sock:/var/run/docker.sock
  - '{{ docker_container_authentik_volume_dir }}/media:/media'
  - '{{ docker_container_authentik_volume_dir }}/certs:/certs'
  - '{{ docker_container_authentik_volume_dir }}/custom-templates:/templates'
```

### docker_image_authentik_name

Repository path and tag for the container image.

#### Default value

```YAML
docker_image_authentik_name: ghcr.io/goauthentik/server:2024.12.3
```

### docker_image_authentik_pull

Indicate to always pull the docker image.

#### Default value

```YAML
docker_image_authentik_pull: false
```

### docker_image_authentikdb_name

Repository path and tag for the container image.

#### Default value

```YAML
docker_image_authentikdb_name: docker.io/library/postgres:16-alpine
```

### docker_image_authentikdb_pull

Indicate to always pull the docker image.

#### Default value

```YAML
docker_image_authentikdb_pull: false
```

### docker_image_authentikredis_name

Repository path and tag for the container image.

#### Default value

```YAML
docker_image_authentikredis_name: docker.io/library/redis:alpine
```

### docker_image_authentikredis_pull

Indicate to always pull the docker image.

#### Default value

```YAML
docker_image_authentikredis_pull: false
```

### docker_image_authentikworker_name

Repository path and tag for the container image.

#### Default value

```YAML
docker_image_authentikworker_name: ghcr.io/goauthentik/server:2024.12.3
```

### docker_image_authentikworker_pull

Indicate to always pull the docker image.

#### Default value

```YAML
docker_image_authentikworker_pull: false
```

### docker_network_authentik_name

Name of the docker network created for authentik.

#### Default value

```YAML
docker_network_authentik_name: '{{ docker_container_authentik_name }}_backend'
```

### docker_network_authentikdb_name

Name of the docker network created for authentikdb.

#### Default value

```YAML
docker_network_authentikdb_name: '{{ docker_container_authentik_name }}_backend'
```

### docker_network_authentikredis_name

Name of the docker network created for authentikredis.

#### Default value

```YAML
docker_network_authentikredis_name: '{{ docker_container_authentik_name }}_backend'
```

### docker_network_authentikworker_name

Name of the docker network created for authentikworker.

#### Default value

```YAML
docker_network_authentikworker_name: '{{ docker_container_authentik_name }}_backend'
```

## Discovered Tags

**_docker-container-backup-all_**\
&emsp;Backup all containers' volume mounts.

**_docker-container-backup-authentik_**\
&emsp;Backup authentik volume mounts.

**_docker-container-backup-init-all_**\
&emsp;Run init backup task for all container.

**_docker-container-backup-init-authentik_**\
&emsp;Run init backup task for authentik if restic is enabled.

**_docker-container-backup-list-all_**\
&emsp;List all containers' backups.

**_docker-container-backup-list-authentik_**\
&emsp;List authentik backups.

**_docker-container-prereq-all_**\
&emsp;Ensure all pre-requisites are installed

**_docker-container-prereq-authentik_**\
&emsp;Ensure all pre-requisites for authentik are installed

**_docker-container-purge-all_**\
&emsp;Remove all containers and delete volume mounts.

**_docker-container-purge-authentik_**\
&emsp;Remove authentik and delete volume mounts.

**_docker-container-remove-all_**\
&emsp;Remove all containers.

**_docker-container-remove-authentik_**\
&emsp;Remove authentik.

**_docker-container-restore-all_**\
&emsp;Run restic restore for all restic enabled containers.

**_docker-container-restore-authentik_**\
&emsp;Run restic restore for authentik if restic is enabled.

**_docker-container-setup-all_**\
&emsp;Run setup task for all containers.

**_docker-container-setup-authentik_**\
&emsp;Run setup task for authentik.

**_never_**


## Dependencies

None.

## License

license (GPL-2.0-or-later, MIT, etc)

## Author

andif888
