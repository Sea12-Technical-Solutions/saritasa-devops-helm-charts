
# maintenance-page

## `license`
```
          ,-.
 ,     ,-.   ,-.
/ \   (   )-(   )
\ |  ,.>-(   )-<
 \|,' (   )-(   )
  Y ___`-'   `-'
  |/__/   `-'
  |
  |
  |    -hi-
__|_____________

/* Copyright (C) Saritasa,LLC - All Rights Reserved
 * Unauthorized copying of this file, via any medium is strictly prohibited
 * Proprietary and confidential
 * Written by Saritasa Devops Team, April 2022
 */

```

## `chart.deprecationWarning`

## `chart.name`

maintenance-page

## `chart.version`

![Version: 0.0.2](https://img.shields.io/badge/Version-0.0.2-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square)

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| Saritasa | <nospam@sea12tech.com> | <https://www.sea12tech.com/> |

## `chart.description`

A Helm chart for Kubernetes to display a simple maintenance page.
By default it displays the following content:
[https://codepen.io/Neil-Mayers/pen/XJJNqNv](https://codepen.io/Neil-Mayers/pen/XJJNqNv)

You can adjust the look by setting up the following values in the values.yaml file:

```yaml
message:
  backgroundColor: "#d6433b"
  textColor: "#fff"
  title: "Site Maintenance"
  header: "We&rsquo;ll be back soon!"
  body: |
    <p>Sorry for the inconvenience. We&rsquo;re performing some maintenance at the moment. We&rsquo;ll be back up shortly!</p>
  footer: |
    <p>&mdash; The DevOps Team</p>
```

or by supplying an entire HTML for the maintenance page via

```yaml
html: |
  hello, the maintenance page HTML + CSS code is here
```

## `chart.valuesTable`

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` |  |
| environment | string | `""` | name of the environment you're placing the maintenance page for like dev, prod, staging |
| fullnameOverride | string | `""` |  |
| html | string | `""` | html for the maintenance page. If you need a totally custom HTML design, then keep message config above empty and put here a full HTML (CSS+HTML). You can test the page here: https://codepen.io/Neil-Mayers/pen/XJJNqNv |
| image.pullPolicy | string | `"IfNotPresent"` | pull policy |
| image.repository | string | `"saritasallc/kubernetes-maintenance-page"` | container repository, adjust in https://github.com/saritasa-nest/saritasa-devops-docker-images/pull/29 |
| image.tag | string | `"0.1"` | Overrides the image tag whose default is the chart appVersion. |
| imagePullSecrets | list | `[]` | credentials for docker login |
| message | object | `{}` | message configuration in the maintenance page. |
| nameOverride | string | `""` |  |
| nodeSelector | object | `{}` |  |
| podAnnotations | object | `{}` |  |
| podSecurityContext | object | `{}` |  |
| replicaCount | int | `1` | how many replicas (pods) to run |
| resources.limits.cpu | string | `"100m"` |  |
| resources.limits.memory | string | `"128Mi"` |  |
| resources.requests.cpu | string | `"50m"` |  |
| resources.requests.memory | string | `"50Mi"` |  |
| securityContext.runAsNonRoot | bool | `true` | run the container as non-root user |
| securityContext.runAsUser | int | `101` | run under non-root user, 101 - is nginx user defined in the docker container |
| service.port | int | `8080` |  |
| service.type | string | `"ClusterIP"` |  |
| serviceAccount.annotations | object | `{}` | Annotations to add to the service account |
| serviceAccount.create | bool | `true` | Specifies whether a service account should be created |
| serviceAccount.name | string | `""` | The name of the service account to use. If not set and create is true, a name is generated using the fullname template |
| tolerations | list | `[]` |  |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.14.2](https://github.com/norwoodj/helm-docs/releases/v1.14.2)
