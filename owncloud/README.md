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