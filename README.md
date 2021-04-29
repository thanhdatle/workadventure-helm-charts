# helm-charts
My own helm charts repository

## How to add new chart:
- Clone repo
- Put chart to the `helm-chart-sources` directory
- Lint charts to be sure that it does not have errors
```shell
helm lint helm-chart-sources/*
```
- Package charts by:
```shell
helm package helm-chart-sources/*
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
helm lint helm-chart-sources/*
```
- Increment chart version in `Chart.yaml` file
  db-configmap.yaml- Package charts by:
```shell
helm package helm-chart-sources/*
``` 
- Regenerate index.html file by:
```shell
helm repo index --url https://behoof4mind.github.io/helm-charts --merge index.yaml .
```
- Push your changes back to the repo

## List of available charts:

[workadventure-chart](./helm-chart-sources/workadventure-chart/README.md)
[weather-service](./helm-chart-sources/weather-service/README.md)


## License

[The MIT License (MIT)](LICENSE)

Copyright © 2021 [Denis Lavrushko](https://dlavrushko.de)