# Dynatrace Prometheus → Custom Device Extension

This repository contains a **Dynatrace Python Extension** that collects metrics from a **Prometheus endpoint** (for example, Node Exporter) and sends them to **Dynatrace as Custom Device metrics**.

This approach allows monitoring systems **without deploying Dynatrace OneAgent**, which is useful when OneAgent is not supported or when optimizing licenses.

---

## What It Does

- Scrapes metrics from a Prometheus `/metrics` endpoint  
- Sends all metrics to Dynatrace  
- Attaches metrics to a **Custom Device** (`dt.entity.custom_device`)  
- Enables correlation, alerting, and analysis in Dynatrace

---

## How to Use

1. Build the extension using the Dynatrace Extension SDK  
2. Upload the extension ZIP file to Dynatrace  
3. Create a monitoring configuration:
   - Metrics URL
   - Custom Device ID
   - Collection interval
4. Enable the extension

---

## Documentation

- Dynatrace Extensions overview:  
  https://docs.dynatrace.com/docs/ingest-from/extensions

- Developing Python extensions:  
  https://dynatrace-extensions.github.io/dt-extensions-python-sdk/

---

## Notes

- Prometheus exporters (e.g. Node Exporter) are required  
- Dynatrace OneAgent is **not required**  
- This is a custom, self-authored extension

---

## Author

Ariel
