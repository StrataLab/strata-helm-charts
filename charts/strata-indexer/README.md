# strata-indexer

![Version: 0.1.0](https://img.shields.io/badge/Version-0.1.0-informational?style=flat-square) ![AppVersion: 0.0.0-8187-60827f3f](https://img.shields.io/badge/AppVersion-0.0.0--8187--60827f3f-informational?style=flat-square)

A Helm chart for Stratalab's blockchain indexer.

**Homepage:** <https://www.stratalab.xyz/>

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| stratalab |  | <https://github.com/StrataLab> |

## Source Code

* <https://github.com/StrataLab/strata-helm-charts>
* <https://stratalab.github.io/helm-charts>

## Requirements

Kubernetes: `>=1.23.0-0`

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| database.existingSecret | string | `""` |  |
| env[0].name | string | `"_JAVA_OPTIONS"` |  |
| env[0].value | string | `"-Xmx1g -Xms1g -Dstorage.diskCache.bufferSize=2000 -XX:ActiveProcessorCount=4 -XX:+AlwaysPreTouch"` |  |
| image.imagePullPolicy | string | `"IfNotPresent"` |  |
| image.repository | string | `"stratalab/strata-indexer"` |  |
| image.tag | string | `""` |  |
| istio.annotations | object | `{}` |  |
| istio.corsPolicy.allowCredentials | bool | `true` |  |
| istio.corsPolicy.allowHeaders[0] | string | `"grpc-timeout"` |  |
| istio.corsPolicy.allowHeaders[10] | string | `"x-grpc-web"` |  |
| istio.corsPolicy.allowHeaders[1] | string | `"content-type"` |  |
| istio.corsPolicy.allowHeaders[2] | string | `"keep-alive"` |  |
| istio.corsPolicy.allowHeaders[3] | string | `"user-agent"` |  |
| istio.corsPolicy.allowHeaders[4] | string | `"cache-control"` |  |
| istio.corsPolicy.allowHeaders[5] | string | `"content-type"` |  |
| istio.corsPolicy.allowHeaders[6] | string | `"content-transfer-encoding"` |  |
| istio.corsPolicy.allowHeaders[7] | string | `"x-accept-content-transfer-encoding"` |  |
| istio.corsPolicy.allowHeaders[8] | string | `"x-accept-response-streaming"` |  |
| istio.corsPolicy.allowHeaders[9] | string | `"x-user-agent"` |  |
| istio.corsPolicy.allowMethods[0] | string | `"POST"` |  |
| istio.corsPolicy.allowMethods[1] | string | `"GET"` |  |
| istio.corsPolicy.allowMethods[2] | string | `"OPTIONS"` |  |
| istio.corsPolicy.allowMethods[3] | string | `"PUT"` |  |
| istio.corsPolicy.allowMethods[4] | string | `"DELETE"` |  |
| istio.corsPolicy.allowOrigins[0].regex | string | `".*"` |  |
| istio.corsPolicy.exposeHeaders[0] | string | `"grpc-status"` |  |
| istio.corsPolicy.exposeHeaders[1] | string | `"grpc-message"` |  |
| istio.corsPolicy.maxAge | string | `"24h"` |  |
| istio.createGrpcWebFilter | bool | `true` |  |
| istio.enabled | bool | `false` |  |
| istio.ingress.gateways[0] | string | `"istio-gateways/gateway"` |  |
| istio.ingress.host | string | `"strata-indexer.example.com"` |  |
| istio.ingress.redirectHosts | list | `[]` |  |
| istio.outlierDetection | object | `{}` |  |
| istio.overallTimeout | string | `nil` |  |
| istio.rateLimiting.p2p.enabled | bool | `false` |  |
| istio.rateLimiting.p2p.fill_interval | string | `"60s"` |  |
| istio.rateLimiting.p2p.max_tokens | int | `5000` |  |
| istio.rateLimiting.p2p.tokens_per_fill | int | `5000` |  |
| istio.rateLimiting.rpc.enabled | bool | `false` |  |
| istio.rateLimiting.rpc.fill_interval | string | `"60s"` |  |
| istio.rateLimiting.rpc.max_tokens | int | `5000` |  |
| istio.rateLimiting.rpc.tokens_per_fill | int | `5000` |  |
| istio.retries | object | `{}` |  |
| istio.virtualServiceRoutes.http[0].matchPrefix | list | `[]` |  |
| istio.virtualServiceRoutes.http[0].port | int | `443` |  |
| istio.virtualServiceRoutes.http[0].targetPort | int | `9084` |  |
| maxUnavailable | int | `1` |  |
| networkPolicy.enabled | bool | `true` |  |
| nodeRpc.host | string | `"localhost"` |  |
| nodeRpc.port | int | `9084` |  |
| nodeRpc.tls | bool | `false` |  |
| nodeSelector | list | `[]` |  |
| podSecurityContext.fsGroup | int | `0` |  |
| podSecurityContext.runAsGroup | int | `0` |  |
| podSecurityContext.runAsUser | int | `1001` |  |
| podSecurityContext.seccompProfile.type | string | `"RuntimeDefault"` |  |
| ports[0].name | string | `"http2"` |  |
| ports[0].port | int | `9084` |  |
| ports[0].targetPort | int | `9084` |  |
| probes.readinessProbe.grpc.port | int | `9084` |  |
| probes.readinessProbe.timeoutSeconds | int | `20` |  |
| probes.startupProbe.failureThreshold | int | `30` |  |
| probes.startupProbe.grpc.port | int | `9084` |  |
| probes.startupProbe.timeoutSeconds | int | `20` |  |
| replicaCount | int | `1` |  |
| replicator.enable | bool | `true` |  |
| resources.limits.ephemeral-storage | string | `"500Mi"` |  |
| resources.limits.memory | string | `"4000Mi"` |  |
| resources.requests.cpu | string | `"250m"` |  |
| resources.requests.memory | string | `"4000Mi"` |  |
| securityContext.allowPrivilegeEscalation | bool | `false` |  |
| securityContext.capabilities.drop[0] | string | `"ALL"` |  |
| securityContext.readOnlyRootFilesystem | bool | `true` |  |
| service | string | `"strata-indexer"` |  |
| serviceAccount.automountToken | bool | `false` |  |
| serviceAccount.create | bool | `true` |  |
| serviceAccount.name | string | `"strata-indexer"` |  |
| serviceType | string | `"ClusterIP"` |  |
| system | string | `"strata-indexer"` |  |
| version | int | `1` |  |
| volume.storageClass | string | `nil` |  |
| volume.storageSize | string | `"10Gi"` |  |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.13.1](https://github.com/norwoodj/helm-docs/releases/v1.13.1)
