# Windows Brute-Force Detection Using Splunk

## Project Overview

This project demonstrates the detection of repeated failed Windows
authentication attempts using Splunk Universal Forwarder and Splunk
Enterprise Security.

The project covers Windows Security Event Collection, SPL-based detection,
Correlation Search configuration, and scheduler troubleshooting.

## Architecture

```text
Windows Laptop
      |
      | Windows Security Logs
      | Event ID 4625
      v
Splunk Universal Forwarder
      |
      | TCP 9997
      v
Splunk Enterprise
      |
      v
Splunk Enterprise Security
      |
      v
Correlation Search
      |
      v
Detection
