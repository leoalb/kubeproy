# **Helm package for local ownCloud**

ownCloud is a file server that enables secure storage, collaboration and sharing. It is convenient to store files in the cloud, so they are available on any device and can be shared with a few clicks.

The ownCloud image used has database connectors for MySQL / MariaDB.

The deployment exposes ports 8080, allowing for HTTP connections and uses separate MariaDB and Redis containers. It mounts the data and MySQL data directories on the host for persistent storage.

## **TL;DR**
```console
git clone https://github.com/leoalb/kubeproy.git
cd kubeproy
helm install my-release-name ./owncloud
```

## **Introduction**
This chart bootstraps a ownCloud deployment on a Kubernetes cluster using the Helm package manager.

## **Prerequisites**
- Kubernetes 1.28.2+
- Helm 3.13.2+
- ReadWriteMany volumes for deployment scaling

## Installing the Chart

To install the chart with the release name my-release:

`helm install my-release ./owncloud `

Tip: List all releases using helm list

## Uninstalling the Chart

To uninstall/delete the my-release deployment:

helm delete my-release

The command removes all the Kubernetes components associated with the chart and deletes the release.

## Parameters

### owncloud

| Name       | Description               | Default     |
|:-----------|:--------------------------|:------------|
| `owncloud.replicas` | Replicas server container | `1`         |
| `owncloud.strategy.type` | Strategy type | `Recreate` |
| `owncloud.containers.image.repository` | Owncloud image repository | `owncloud/server` |
| `owncloud.containers.image.version` | Owncloud image version | `10.13` |
| `owncloud.containers.image.pullPolicy` | Owncloud image pull policy | `IfNotPresent` |
| `owncloud.containers.livenessProbe.failureThreshold` | Failure threshold of the liveness probe | `5` |
| `owncloud.containers.livenessProbe.periodSeconds` | Period seconds of the liveness probe | `30` |
| `owncloud.containers.livenessProbe.timeoutSeconds` | Timeout seconds of the liveness probe | `10` |
| `owncloud.containers.name` | Containers base name | `owncloud-server` |
| `owncloud.containers.ports.containerPort` | container listening port number | `8080` |
| `owncloud.containers.ports.protocol` | container listening port protocol | `TCP` |
| `owncloud.containers.volumeMounts.mountPath` | Volume mount-path | `/mnt/data` |
| `owncloud.containers.volumeMounts.name` | Volume name | `files` |
| `owncloud.containers.env.AdminPass.name` | Owncloud env variable | `OWNCLOUD_ADMIN_PASSWORD` |
| `owncloud.containers.env.AdminPass.value` | Administrator password | `admin` |
| `owncloud.containers.env.AdminUser.name` | Owncloud env variable | `OWNCLOUD_ADMIN_USERNAME` |
| `owncloud.containers.env.AdminUser.value` | Administrator username | `admin` |
| `owncloud.containers.env.DbHost.name` | Owncloud env variable | `OWNCLOUD_DB_HOST` |
| `owncloud.containers.env.DbHost.value` | DB hostname | `mariadb` |
| `owncloud.containers.env.DbName.name` | Owncloud env variable | `OWNCLOUD_DB_NAME` |
| `owncloud.containers.env.DbName.value` | DB name | `defaultValue` |
| `owncloud.containers.env.DbPass.name` | Owncloud env variable | `OWNCLOUD_DB_PASSWORD` |
| `owncloud.containers.env.DbPass.value` | DB password | `owncloud` |
| `owncloud.containers.env.DbType.name` | Owncloud env variable | `OWNCLOUD_DB_TYPE` |
| `owncloud.containers.env.DbType.value` | DB type | `mysql` |
| `owncloud.containers.env.DbUser.name` | Owncloud env variable | `OWNCLOUD_DB_USERNAME` |
| `owncloud.containers.env.DbUser.value` | DB username | `owncloud` |
| `owncloud.containers.env.DbDomain.name` | Owncloud env variable | `OWNCLOUD_DOMAIN` |
| `owncloud.containers.env.DbDomain.value` | Owncloud domain | `localhost:8080` |
| `owncloud.containers.env.MySqlUtf.name` | Owncloud env variable | `OWNCLOUD_MYSQL_UTF8MB4` |
| `owncloud.containers.env.MySqlUtf.value` | Mysql character set enabled | `true` |
| `owncloud.containers.env.RedisEn.name` | Owncloud env variable | `OWNCLOUD_REDIS_ENABLED` |
| `owncloud.containers.env.RedisEn.value` | Boolean if redis is enabled | `true` |
| `owncloud.containers.env.RedisHost.name` | Owncloud env variable | `OWNCLOUD_REDIS_HOST` |
| `owncloud.containers.env.RedisHost.value` | Redis host name | `redis` |
| `owncloud.containers.env.TrustedDomains.name` | Owncloud env variable | `OWNCLOUD_TRUSTED_DOMAINS` |
| `owncloud.containers.env.TrustedDomains.value` | Trusted domains | `localhost` |
| `owncloud.restartPolicy` | Restart policy | `Always` |
| `owncloud.volumes.name` | Volume name | `files` |
| `owncloud.volumes.persistentVolumeClaim.claimName` | Description for value 3 | `files` |
| `owncloud.volumes.persistentVolumeClaim.storage` | Description for value 3 | `100` |
| `owncloud.service.ports.name` | Service port name  | `service-owncloud` |
| `owncloud.service.ports.port` | Service port number | `8080` |
| `owncloud.service.ports.targetPort` | Service target port number  | `8080` |
| `owncloud.service.type` | Service type | `LoadBalancer` |




### redis

| Name      | Description             | Default        |
|:----------|:------------------------|:---------------|
| `redis.name` | Deployment name | `redis` |
| `redis.containers.name` | Containers base name | `owncloud-redis` |
| `redis.containers.volumeMounts.mountPath` | Volume mount-path  | `/data` |
| `redis.containers.volumeMounts.name` | Volume name  | `redis` |
| `redis.containers.replicas` | Number of replicas | `1` |
| `redis.containers.image.repository` | Redis image repository | `redis` |
| `redis.containers.image.version` | Redis image version | `6` |
| `redis.containers.livenessProbe.failureThreshold` | Failure threshold of the liveness probe | `5` |
| `redis.containers.livenessProbe.periodSeconds` | Period seconds of the liveness probe | `10` |
| `redis.containers.livenessProbe.timeoutSeconds` | Timeout seconds of the liveness probe | `5` |
| `redis.restartPolicy` | Restart policy | `Always` |
| `redis.volumes.name` | Volume name | `redis` |
| `redis.volumes.persistentVolumeClaim.claimName` | DB volume name | `redis` |
| `redis.volumes.persistentVolumeClaim.storage` | DB volume size | `100Mi` |
| `redis.service.ports.name` | Service port name | `service-redis` |
| `redis.service.ports.port` | Service port number | `6379` |
| `redis.service.ports.targetPort` | Service target port number | `6379` |

### mariaDb

| Name      | Description             | Default        |
|:----------|:------------------------|:---------------|
| `mariaDb.restartPolicy` | Restart Policy | `Always` |
| `mariaDb.replicas` | Number of replicas | `1` |
| `mariaDb.strategy.type` | Strategy type | `Recreate` |
| `mariaDb.volumes.name` | Volume name | `mysql` |
| `mariaDb.volumes.persistentVolumeClaim.claimName` | DB volume name | `mysql` |
| `mariaDb.volumes.persistentVolumeClaim.storage` | DB volume size | `100Mi` |
| `mariaDb.service.ports.name` | Service port name | `service-mariadb` |
| `mariaDb.service.ports.port` | Service port number | `3306` |
| `mariaDb.service.ports.targetPort` | Service target port number | `3306` |
| `mariaDb.containers.image.repository` | MariaDB image repository | `mariadb` |
| `mariaDb.containers.image.version` | MariaDB image version | `10.11` |
| `mariaDb.containers.name` | Containers base name | `owncloud-mariadb` |
| `mariaDb.containers.volumeMounts.mountPath` | Volume mount-path  | ` /var/lib/mysql` |
| `mariaDb.containers.volumeMounts.name` | Volume name | `mysql` |
| `mariaDb.containers.livenessProbe.failureThreshold` | Failure threshold of the liveness probe| `5` |
| `mariaDb.containers.livenessProbe.periodSeconds` | Period seconds of the liveness probe | `10` |
| `mariaDb.containers.livenessProbe.timeoutSeconds` | Timeout seconds of the liveness probe | `5` |
| `mariaDb.containers.env.autoUpgrade.name` | mariadb env variable | `MARIADB_AUTO_UPGRADE` |
| `mariaDb.containers.env.autoUpgrade.value` | mariadb env variable | `1` |
| `mariaDb.containers.env.mySql.db.name` | mariadb env variable | `MYSQL_DATABASE` |
| `mariaDb.containers.env.mySql.db.value` | db name | `owncloud` |
| `mariaDb.containers.env.mySql.pass.name` | mariadb env variable | `MYSQL_PASSWORD` |
| `mariaDb.containers.env.mySql.pass.value` | mysql db password | `owncloud` |
| `mariaDb.containers.env.mySql.rootPass.name` | mariadb env variable | `MYSQL_ROOT_PASSWORD` |
| `mariaDb.containers.env.mySql.rootPass.value` | mysql root password | `owncloud` |
| `mariaDb.containers.env.mySql.user.name` | mariadb env variable | `MYSQL_USER` |
| `mariaDb.containers.env.mySql.user.value` | mysql username | `owncloud` |








