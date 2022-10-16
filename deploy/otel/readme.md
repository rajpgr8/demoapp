```
$ kubectl logs -f opentelemetrycollector-76796f55f6-89qk6

2022-10-16T21:05:50.879Z        info    builder/pipelines_builder.go:207        Pipeline is enabled.    {"pipeline_name": "traces", "pipeline_datatype": "traces"}
2022-10-16T21:05:50.879Z        info    service/service.go:352  Starting processors...
2022-10-16T21:05:50.879Z        info    builder/pipelines_builder.go:51 Pipeline is starting... {"pipeline_name": "traces", "pipeline_datatype": "traces"}
2022-10-16T21:05:50.879Z        info    builder/pipelines_builder.go:61 Pipeline is started.    {"pipeline_name": "traces", "pipeline_datatype": "traces"}
2022-10-16T21:05:50.879Z        info    builder/receivers_builder.go:235        Receiver is enabled.    {"component_kind": "receiver", "component_type": "otlp", "component_name": "otlp", "datatype": "traces"}
2022-10-16T21:05:50.879Z        info    service/service.go:364  Starting receivers...
2022-10-16T21:05:50.879Z        info    builder/receivers_builder.go:70 Receiver is starting... {"component_kind": "receiver", "component_type": "otlp", "component_name": "otlp"}
2022-10-16T21:05:50.879Z        info    otlpreceiver/otlp.go:93 Starting GRPC server on endpoint 0.0.0.0:4317   {"component_kind": "receiver", "component_type": "otlp", "component_name": "otlp"}
2022-10-16T21:05:50.879Z        info    otlpreceiver/otlp.go:130        Setting up a second GRPC listener on legacy endpoint 0.0.0.0:55680      {"component_kind": "receiver", "component_type": "otlp", "component_name": "otlp"}
2022-10-16T21:05:50.879Z        info    otlpreceiver/otlp.go:93 Starting GRPC server on endpoint 0.0.0.0:55680  {"component_kind": "receiver", "component_type": "otlp", "component_name": "otlp"}
2022-10-16T21:05:50.879Z        info    builder/receivers_builder.go:75 Receiver started.       {"component_kind": "receiver", "component_type": "otlp", "component_name": "otlp"}
2022-10-16T21:05:50.879Z        info    service/service.go:267  Everything is ready. Begin running and processing data.
........
........
2022-10-16T21:09:35.830Z        INFO    loggingexporter/logging_exporter.go:313 TracesExporter  {"#spans": 10}
2022-10-16T21:09:40.835Z        INFO    loggingexporter/logging_exporter.go:313 TracesExporter  {"#spans": 15}
2022-10-16T21:09:55.840Z        INFO    loggingexporter/logging_exporter.go:313 TracesExporter  {"#spans": 3}
```

```
Also read: https://github.com/open-telemetry/opentelemetry-operator/
```
