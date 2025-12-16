# Dynatrace Prometheus → Custom Device Extension

This repository contains a **Dynatrace Extension (Python-based)** that collects metrics from a **Prometheus endpoint** (for example, Node Exporter) and sends them to **Dynatrace as Custom Device metrics**.

The extension allows ingesting infrastructure metrics **without deploying Dynatrace OneAgent**, which is useful for:
- Unsupported operating systems
- Network or edge devices
- License optimization scenarios

---

## What This Extension Does

- Scrapes metrics from a Prometheus `/metrics` endpoint
- Parses all exposed Prometheus metrics
- Sends metrics to Dynatrace
- Attaches metrics to a **Custom Device** using `dt.entity.custom_device`
- Enables correlation, alerting, and analysis in Dynatrace

---

## Repository Content

This repository contains **only the extension artifacts**, such as:

- `extension.yaml`
- `activationSchema.json`
- Python source code (`prom_customdevice`)
- Build and packaging files

No infrastructure or Prometheus setup is included.

---

## How It Works (High Level)

1. Prometheus exporter exposes metrics (e.g. Node Exporter)
2. Dynatrace Extension (Python) scrapes the metrics endpoint
3. Metrics are reported to Dynatrace
4. Metrics are linked to a Custom Device entity

---

## How to Use

1. Clone this repository
2. Build the extension using the Dynatrace Extension SDK
3. Upload the extension ZIP file to Dynatrace
4. Create a monitoring configuration:
   - Metrics URL (Prometheus endpoint)
   - Custom Device ID
   - Collection interval
5. Enable the extension

Once enabled, metrics will start appearing in Dynatrace under the Custom Device.

---

## Requirements

- Dynatrace Environment (SaaS or Managed)
- Dynatrace ActiveGate (for remote extensions)
- Prometheus-compatible metrics endpoint
- Python 3.10+

---

## Notes

- This extension ingests **raw Prometheus metrics** as Dynatrace metrics
- Metric filtering is optional and configurable
- OneAgent is **not required**

---

## Disclaimer

This is a **custom extension** provided as-is.
It is not an official Dynatrace product.

---

## Author

Ariel
