quarkus.openapi-generator.codegen.additional-api-type-annotations=@org.eclipse.microprofile.rest.client.annotation.ClientHeaderParam(name="\"Authorization\"", value="\"\${header.value}\"")

  
header.value=Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJhcmdvY2QiLCJzdWIiOiJhcmdvLWFjY291bnQ6YXBpS2V5IiwibmJmIjoxNzQ3Mzg1NDU3LCJpYXQiOjE3NDczODU0NTcsImp0aSI6IjFiNzExYjA0LTYxM2EtNGIxZi1hNzVjLThlNjViNDFlOTgzNyJ9.OO8YTLukS7muP6Ro7VT5miy6QCkXr02VA2ohNIimwnI

quarkus.rest-client.argocd_openapi_json.uri=https://horsprod-argocd.gcatrans.com

# OpenTelemetry  
#quarkus.otel.exporter.otlp.traces.endpoint=http://devops-sandbox.gcatrans.com:4317  
quarkus.otel.exporter.otlp.traces.endpoint = http://gcav526.gcatrans.com:4318  
quarkus.otel.exporter.otlp.traces.protocol = http/protobuf  
quarkus.otel.propagators = tracecontext,baggage,b3,b3multi,jaeger,ottrace  
quarkus.opentelemetry.enabled=true  
quarkus.opentelemetry.tracer.exporter.otlp.endpoint=http://localhost:4317

  
quarkus.native.enabled=true  
quarkus.native.container-image.build=true  
quarkus.native.verbose-build=true  
quarkus.native.enable-reports=true