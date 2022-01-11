# helm-charts
My own helm charts repository

## How to use it:
#### By Helmfile
```yaml
repositories:
  - name: behoof4mind
    url:  https://behoof4mind.github.io/helm-charts

releases:
  - name: weather-service
    namespace: weather-service
    chart: behoof4mind/weather-service
    version: 0.1.0
    atomic: true
    values:
      - image:
...
```
#### By Helm itself:
```yaml
helm repo add behoof4mind https://behoof4mind.github.io/helm-charts
```
```yaml
helm repo update
```
```yaml
helm install weather-service behoof4mind/weather-service -n weather-service --create-namespace
```

## How to add new chart:
- Clone repo
- Put chart to the `helm-chart-sources` directory
- Lint charts to be sure that it does not have errors
```shell
helm lint charts/*
```
- Package charts by:
```shell
helm package charts/*
```  
- Regenerate index.html file by:
```shell
helm repo index --url https://behoof4mind.github.io/helm-charts/ --merge index.yaml .
```
- Push your changes back to the repo

## How to add new chart version
- Clone repo
- Put new changes
- Lint charts to be sure that it does not have errors
```shell
helm lint charts/*
```
- Increment chart version in `Chart.yaml` file
  db-configmap.yaml- Package charts by:
```shell
helm package charts/*
``` 
- Regenerate index.html file by:
```shell
helm repo index --url https://behoof4mind.github.io/helm-charts --merge index.yaml .
```
- Push your changes back to the repo

## List of available charts:

[workadventure-chart](charts/workadventure-chart/README.md) <br>
[weather-service](charts/weather-service/README.md)


## License

[The MIT License (MIT)](LICENSE)

Copyright © 2021 [Denis Lavrushko](https://dlavrushko.de)
