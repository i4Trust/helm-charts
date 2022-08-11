# pdc-portal

![Version: 2.1.0](https://img.shields.io/badge/Version-2.1.0-informational?style=flat-square) ![AppVersion: 2.0.0](https://img.shields.io/badge/AppVersion-2.0.0-informational?style=flat-square)

A Helm chart for running the Packet Delivery Portal application on kubernetes.

**Homepage:** <https://github.com/i4trust/pdc-portal>

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| dwendland | <dennis.wendland@fiware.org> |  |

## Source Code

* <https://github.com/i4trust/pdc-portal>

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| autoscaling.enabled | bool | `false` | should autoscaling be enabled for the activation service |
| autoscaling.maxReplicas | int | `10` | maximum number of running pods |
| autoscaling.metrics | list | `[]` | metrics to react on |
| autoscaling.minReplicas | int | `1` | minimum number of running pods |
| config.cb.endpoint | string | `"https://localhost/ngsi-ld/v1"` | Endpoint of (API-Umbrella protected) NGSI-LD API |
| config.client.crt | string | `"<pdc-certs>"` | Client certificate (PEM certificate chain) |
| config.client.id | string | `"EU.EORI.NLPACKETDEL"` | Client ID |
| config.client.key | string | `"<pdc-private-key>"` | Client key (PEM private key) |
| config.express.port | int | `7000` | Port (Internal port of the express web server) |
| config.external.host | string | `"http://localhost"` | Host (Hostname for external access) |
| config.idp[0].authorize_endpoint | string | `"https://idp.happypets.com/authorize"` |  |
| config.idp[0].id | string | `"EU.EORI.NLHAPPYPETS"` |  |
| config.idp[0].name | string | `"Happy Pets Inc."` |  |
| config.idp[0].token_endpoint | string | `"https://idp.happypets.com/token"` |  |
| config.idp[0].url | string | `"https://idp.happypets.com"` |  |
| config.idp[1].authorize_endpoint | string | `"https://idp.nocheaper.com/authorize"` |  |
| config.idp[1].id | string | `"EU.EORI.NLNOCHEAPER"` |  |
| config.idp[1].name | string | `"No Cheaper Inc."` |  |
| config.idp[1].token_endpoint | string | `"https://idp.nocheaper.com/token"` |  |
| config.idp[1].url | string | `"https://idp.nocheaper.com"` |  |
| config.oidc.acr | string | `"urn:http://eidas.europa.eu/LoA/NotNotified/high"` | ACR values |
| config.oidc.redirect_path | string | `"/openid_connect1.0/return"` | Path for OIDC redirect callback |
| config.title | string | `"Packet Delivery Portal"` | Title of application |
| debug.enabled | bool | `false` |  |
| debug.output | string | `"portal:*"` |  |
| deployment.additionalAnnotations | object | `{}` | additional annotations for the deployment, if required |
| deployment.additionalLabels | object | `{}` | additional labels for the deployment, if required |
| deployment.affinity | object | `{}` | affinity template ref: https://kubernetes.io/docs/concepts/configuration/assign-pod-node/#affinity-and-anti-affinity |
| deployment.image.pullPolicy | string | `"IfNotPresent"` | specification of the image pull policy |
| deployment.image.repository | string | `"i4trust/pdc-portal"` | image name ref: https://hub.docker.com/r/i4trust/pdc-portal |
| deployment.image.tag | string | `"2.0.0"` | tag of the image to be used |
| deployment.livenessProbe.initialDelaySeconds | int | `20` |  |
| deployment.livenessProbe.periodSeconds | int | `10` |  |
| deployment.livenessProbe.successThreshold | int | `1` |  |
| deployment.livenessProbe.timeoutSeconds | int | `30` |  |
| deployment.nodeSelector | object | `{}` | selector template ref: https://kubernetes.io/docs/user-guide/node-selection/ |
| deployment.readinessProbe.initialDelaySeconds | int | `21` |  |
| deployment.readinessProbe.periodSeconds | int | `10` |  |
| deployment.readinessProbe.successThreshold | int | `1` |  |
| deployment.readinessProbe.timeoutSeconds | int | `30` |  |
| deployment.replicaCount | int | `1` | initial number of target replications, can be different if autoscaling is enabled |
| deployment.revisionHistoryLimit | int | `3` | number of old replicas to be retained |
| deployment.tolerations | list | `[]` | tolerations template ref: ref: https://kubernetes.io/docs/concepts/configuration/taint-and-toleration/ |
| deployment.updateStrategy.rollingUpdate | object | `{"maxSurge":1,"maxUnavailable":0}` | new pods will be added gradually |
| deployment.updateStrategy.rollingUpdate.maxSurge | int | `1` | number of pods that can be created above the desired amount while updating |
| deployment.updateStrategy.rollingUpdate.maxUnavailable | int | `0` | number of pods that can be unavailable while updating |
| deployment.updateStrategy.type | string | `"RollingUpdate"` | type of the update |
| fullnameOverride | string | `""` | option to override the fullname config in the _helpers.tpl for the whole chart |
| ingress.annotations | object | `{}` | annotations to be added to the ingress |
| ingress.enabled | bool | `false` | should there be an ingress to connect the activation service with the public internet |
| ingress.hosts | list | `[]` | all hosts to be provided |
| ingress.tls | list | `[]` | configure the ingress' tls |
| nameOverride | string | `""` | option to override the name config in the _helpers.tpl for the whole chart |
| route.annotations | object | `{}` | annotations to be added to the route |
| route.certificate | object | `{}` | see: https://github.com/FIWARE-Ops/fiware-gitops/blob/master/doc/ROUTES.md |
| route.enabled | bool | `false` | should the deployment create openshift routes |
| route.tls | object | `{}` | tls configuration for the route |
| service.annotations | object | `{}` | addtional annotations, if required |
| service.port | int | `80` | port to be used by the service |
| service.type | string | `"ClusterIP"` | service type |
| serviceAccount | object | `{"create":false}` | if a specific service account should be used, it can be configured here ref: https://kubernetes.io/docs/tasks/configure-pod-container/configure-service-account/ |
| serviceAccount.create | bool | `false` | specifies if the account should be created |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.9.1](https://github.com/norwoodj/helm-docs/releases/v1.9.1)
