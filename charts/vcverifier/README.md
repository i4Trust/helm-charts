# vcverifier

![Version: 0.0.7](https://img.shields.io/badge/Version-0.0.7-informational?style=flat-square) ![AppVersion: 0.0.1](https://img.shields.io/badge/AppVersion-0.0.1-informational?style=flat-square)

A Helm chart for running the i4Trust DSBA VCVerifier.

**Homepage:** <https://github.com/fiware/vcverifier>

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| wistefan | <stefan.wiedemann@fiware.org> |  |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| db | object | `{"fileBased":true,"pvc":{"size":"1Gi"},"store":{"connectionString":"file:/db/issuer.sqlite?mode=rwc&cache=shared&_fk=1","driver":"sqlite3"},"verifiableregistry":{"connectionString":"file:/db/verifiableregistry.sqlite?mode=rwc&cache=shared&_fk=1","driver":"sqlite3"},"verifier":{"connectionString":"file:/db/verifier.sqlite?mode=rwc&cache=shared&_fk=1","driver":"sqlite3"}}` | configuration for the databse |
| db.fileBased | bool | `true` | should a filebased db used?  |
| db.pvc | object | `{"size":"1Gi"}` | pvc to be used for the sqlite |
| db.store | object | `{"connectionString":"file:/db/issuer.sqlite?mode=rwc&cache=shared&_fk=1","driver":"sqlite3"}` | config for the individual components |
| db.store.driver | string | `"sqlite3"` | database driver to be used |
| db.verifiableregistry.driver | string | `"sqlite3"` | database driver to be used |
| db.verifier.driver | string | `"sqlite3"` | database driver to be used |
| deployment.additionalAnnotations | object | `{}` | additional annotations for the deployment, if required |
| deployment.additionalLabels | object | `{}` | additional labels for the deployment, if required |
| deployment.affinity | object | `{}` | affinity template ref: https://kubernetes.io/docs/concepts/configuration/assign-pod-node/#affinity-and-anti-affinity |
| deployment.image.pullPolicy | string | `"IfNotPresent"` | specification of the image pull policy |
| deployment.image.repository | string | `"quay.io/fiware/vcverifier"` | image name |
| deployment.image.tag | string | `"0.0.1"` | tag of the image to be used |
| deployment.logLevel | string | `"DEBUG"` | logLevel of the application |
| deployment.nodeSelector | object | `{}` | selector template ref: https://kubernetes.io/docs/user-guide/node-selection/ |
| deployment.port | int | `3000` | port to run the container at |
| deployment.protectedResource | string | `nil` | url of the resource to request  |
| deployment.replicaCount | int | `1` | initial number of target replications, can be different if autoscaling is enabled |
| deployment.revisionHistoryLimit | int | `3` | number of old replicas to be retained |
| deployment.tirAddress | string | `nil` |  |
| deployment.tolerations | list | `[]` | tolerations template ref: ref: https://kubernetes.io/docs/concepts/configuration/taint-and-toleration/ |
| deployment.updateStrategy.rollingUpdate | object | `{"maxSurge":1,"maxUnavailable":0}` | new pods will be added gradually |
| deployment.updateStrategy.rollingUpdate.maxSurge | int | `1` | number of pods that can be created above the desired amount while updating |
| deployment.updateStrategy.rollingUpdate.maxUnavailable | int | `0` | number of pods that can be unavailable while updating |
| deployment.updateStrategy.type | string | `"RollingUpdate"` | type of the update |
| deployment.walt | object | `{"auditorUrl":"https://auditor.walt","coreUrl":"https://core.walt","custodianUrl":"https://custodian.walt","essifUrl":"https://essif.walt","signatoryUrl":"https://signatory.walt"}` | urls of vcwalt to connect to |
| deployment.walt.auditorUrl | string | `"https://auditor.walt"` | address of the auditor api |
| deployment.walt.coreUrl | string | `"https://core.walt"` | address of the core api |
| deployment.walt.custodianUrl | string | `"https://custodian.walt"` | address of the custodian api |
| deployment.walt.essifUrl | string | `"https://essif.walt"` | address of the essif api |
| deployment.walt.signatoryUrl | string | `"https://signatory.walt"` | address of the signatory api |
| fullnameOverride | string | `""` |  |
| ingress.annotations | object | `{}` | annotations to be added to the ingress |
| ingress.enabled | bool | `false` | should there be an ingress to connect the activation service with the public internet |
| ingress.hosts | list | `[]` | all hosts to be provided |
| ingress.tls | list | `[]` | configure the ingress' tls |
| nameOverride | string | `""` |  |
| route.annotations | object | `{}` | annotations to be added to the route |
| route.certificate | object | `{}` | see: https://github.com/FIWARE-Ops/fiware-gitops/blob/master/doc/ROUTES.md |
| route.enabled | bool | `false` |  |
| route.tls | object | `{"termination":"edge"}` | tls configuration for the route |
| service.annotations | object | `{}` | additional annotations, if required |
| service.port | int | `3000` | port to be set for the internal service |
| service.type | string | `"ClusterIP"` | service type |
| serviceAccount | object | `{"create":false}` | if a specific service account should be used, it can be configured here ref: https://kubernetes.io/docs/tasks/configure-pod-container/configure-service-account/ |
| serviceAccount.create | bool | `false` | specifies if the account should be created |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.11.0](https://github.com/norwoodj/helm-docs/releases/v1.11.0)
