
https://opentelemetry.io/docs/collector/configuration/  
https://github.com/open-telemetry/opentelemetry-operator/  


```
Can see traces/metrics for 'springpet' app.

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
(Logs in Debug Mode)

Metric #4
Descriptor:
     -> Name: otelcol_process_runtime_total_sys_memory_bytes
     -> Description: Total bytes of memory obtained from the OS (see 'go doc runtime.MemStats.Sys')
     -> Unit: By
     -> DataType: DoubleGauge
DoubleDataPoints #0
Data point labels:
     -> service_instance_id: f47ae099-0e74-4c62-b4d7-7c91075e5c1a
StartTime: 0
Timestamp: 1665958879077000000
Value: 74793984.000000
...
Span #1
    Trace ID       : 4fa028fa6b732005d7cfcc724f2497ca
    Parent ID      : d038aada879c5db0
    ID             : 27a16843fc709907
    Name           : Render owners/createOrUpdateOwnerForm
    Kind           : SPAN_KIND_INTERNAL
    Start time     : 2022-10-16 22:24:32.180365142 +0000 UTC
    End time       : 2022-10-16 22:24:32.234371721 +0000 UTC
    Status code    : STATUS_CODE_UNSET
 .....
DoubleDataPoints #7
Data point labels:
     -> receiver: hostmetrics
     -> scraper: processes
     -> service_instance_id: f47ae099-0e74-4c62-b4d7-7c91075e5c1a
StartTime: 1665958929077000000
Timestamp: 1665958999077000000
Value: 2.000000

```

```

```
