# Running the Flask examples

## Step 1: Install the required packages

```
pip install elastic-opentelemetry opentelemetry-api opentelemetry-sdk opentelemetry-exporter-otlp opentelemetry-instrumentation-flask
opentelemetry-bootstrap --action=install
```

## Step 2: Setting local environment variables 
Create an account with Elastic [here](https://www.elastic.co/cloud/cloud-trial-overview) and gather the OTLP Headers and Endpoint.

```
export OTEL_RESOURCE_ATTRIBUTES=service.name=otel-flask-demo
export OTEL_EXPORTER_OTLP_HEADERS="Authorization=Bearer <your-auth-token>"
export OTEL_EXPORTER_OTLP_ENDPOINT=https://<your-elastic-cloud-url>
export ELASTIC_OTEL_SYSTEM_METRICS_ENABLED=true
```

## Step 3: Running the app

### Automatic instrumentation
The Automatic Instrumentation demo will run on localhost:4999
```
OTEL_SERVICE_NAME='automatic-flask-demo' opentelemetry-instrument python app.py
```

### Manual instrumentation
The Manual Instrumentation demo will run on localhost:5000
```
flask run
```
### Hybrid instrumentation
The Hybrid Instrumentation demo will run on localhost:5001

```
OTEL_SERVICE_NAME='hybrid-flask-demo' opentelemetry-instrument python app.py
```