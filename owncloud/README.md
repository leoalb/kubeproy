# **Helm package for ownCloud**

ownCloud is a file server that enables secure storage, collaboration and sharing. It is convenient to store files in the cloud, so they are available on any device and can be shared with a few clicks.

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
| `owncloud.strategy.type` | Description for value 2 | `defaultValue` |
| `owncloud.containers.image.repository` | Description for value 3 | `defaultValue` |
| `owncloud.containers.image.version` | Description for value 3 | `defaultValue` |
| `owncloud.containers.image.pullPolicy` | Description for value 3 | `defaultValue` |
| `owncloud.containers.livenessProbe.failureThreshold` | Description for value 3 | `defaultValue` |
| `owncloud.containers.livenessProbe.periodSeconds` | Description for value 3 | `defaultValue` |
| `owncloud.containers.livenessProbe.timeoutSeconds` | Description for value 3 | `defaultValue` |
| `owncloud.containers.name` | Description for value 3 | `defaultValue` |
| `owncloud.containers.ports.containerPort` | Description for value 3 | `defaultValue` |
| `owncloud.containers.ports.protocol` | Description for value 3 | `defaultValue` |
| `owncloud.containers.volumeMounts.mountPath` | Description for value 3 | `defaultValue` |
| `owncloud.containers.volumeMounts.name` | Description for value 3 | `defaultValue` |
| `owncloud.containers.env.AdminPass.name` | Description for value 3 | `defaultValue` |
| `owncloud.containers.env.AdminPass.value` | Description for value 3 | `defaultValue` |
| `owncloud.containers.env.AdminUser.name` | Description for value 3 | `defaultValue` |
| `owncloud.containers.env.AdminUser.value` | Description for value 3 | `defaultValue` |
| `owncloud.containers.env.DbHost.name` | Description for value 3 | `defaultValue` |
| `owncloud.containers.env.DbHost.value` | Description for value 3 | `defaultValue` |
| `owncloud.containers.env.DbName.name` | Description for value 3 | `defaultValue` |
| `owncloud.containers.env.DbName.value` | Description for value 3 | `defaultValue` |
| `owncloud.containers.env.DbPass.name` | Description for value 3 | `defaultValue` |
| `owncloud.containers.env.DbPass.value` | Description for value 3 | `defaultValue` |
| `owncloud.containers.env.DbType.name` | Description for value 3 | `defaultValue` |
| `owncloud.containers.env.DbType.value` | Description for value 3 | `defaultValue` |
| `owncloud.containers.env.DbUser.name` | Description for value 3 | `defaultValue` |
| `owncloud.containers.env.DbUser.value` | Description for value 3 | `defaultValue` |
| `owncloud.containers.env.DbDomain.name` | Description for value 3 | `defaultValue` |
| `owncloud.containers.env.DbDomain.value` | Description for value 3 | `defaultValue` |
| `owncloud.containers.env.MySqlUtf.name` | Description for value 3 | `defaultValue` |
| `owncloud.containers.env.MySqlUtf.value` | Description for value 3 | `defaultValue` |
| `owncloud.containers.env.RedisEn.name` | Description for value 3 | `defaultValue` |
| `owncloud.containers.env.RedisEn.value` | Description for value 3 | `defaultValue` |
| `owncloud.containers.env.RedisHost.name` | Description for value 3 | `defaultValue` |
| `owncloud.containers.env.RedisHost.value` | Description for value 3 | `defaultValue` |
| `owncloud.containers.env.TrustedDomains.name` | Description for value 3 | `defaultValue` |
| `owncloud.containers.env.TrustedDomains.value` | Description for value 3 | `defaultValue` |
| `owncloud.restartPolicy` | Description for value 3 | `defaultValue` |
| `owncloud.volumes.name` | Description for value 3 | `defaultValue` |
| `owncloud.volumes.persistentVolumeClaim.claimName` | Description for value 3 | `defaultValue` |
| `owncloud.volumes.persistentVolumeClaim.storage` | Description for value 3 | `defaultValue` |
| `owncloud.service.ports.name` | Description for value 3 | `defaultValue` |
| `owncloud.service.ports.port` | Description for value 3 | `defaultValue` |
| `owncloud.service.ports.targetPort` | Description for value 3 | `defaultValue` |
| `owncloud.service.type` | Description for value 3 | `defaultValue` |




### redis

| Name      | Description             | Default        |
|:----------|:------------------------|:---------------|
| `redis.name` | Description for value 1 | `defaultValue` |
| `redis.containers.name` | Description for value 2 | `defaultValue` |
| `redis.containers.volumeMounts.mountPath` | Description for value 2 | `defaultValue` |
| `redis.containers.volumeMounts.name` | Description for value 2 | `defaultValue` |
| `redis.containers.replicas` | Description for value 2 | `defaultValue` |
| `redis.containers.image.repository` | Description for value 2 | `defaultValue` |
| `redis.containers.image.version` | Description for value 2 | `defaultValue` |
| `redis.containers.livenessProbe.failureThreshold` | Description for value 2 | `defaultValue` |
| `redis.containers.livenessProbe.periodSeconds` | Description for value 2 | `defaultValue` |
| `redis.containers.livenessProbe.timeoutSeconds` | Description for value 2 | `defaultValue` |
| `redis.restartPolicy` | Description for value 2 | `defaultValue` |
| `redis.volumes.name` | Description for value 2 | `defaultValue` |
| `redis.volumes.persistentVolumeClaim.claimName` | Description for value 2 | `defaultValue` |
| `redis.volumes.persistentVolumeClaim.storage` | Description for value 2 | `defaultValue` |
| `redis.service.ports.name` | Description for value 2 | `defaultValue` |
| `redis.service.ports.port` | Description for value 2 | `defaultValue` |
| `redis.service.ports.targetPort` | Description for value 2 | `defaultValue` |

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








