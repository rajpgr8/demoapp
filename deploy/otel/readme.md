```
https://medium.com/opentelemetry/deploying-the-opentelemetry-collector-on-kubernetes-2256eca569c9#:~:text=The%20OpenTelemetry%20Collector%20is%20a,a%20container%20platform%20like%20Kubernetes.

$ kubectl port-forward deployment/oteltestapp 8080:8080
$ http:127.0.0.1:8080/order


$ kubectl logs deployments/opentelemetrycollector -f
shuod see:
2021-01-22T13:26:49.320Z INFO loggingexporter/logging_exporter.go:313 TracesExporter {"#spans": 2}
2021-01-22T13:26:49.430Z INFO loggingexporter/logging_exporter.go:313 TracesExporter {"#spans": 1}
```
