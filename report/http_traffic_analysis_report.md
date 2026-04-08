# HTTP Traffic Analysis Report (Wireshark)

## 1. Introduction

This report documents the analysis of HTTP network traffic using Wireshark. The objective was to identify unusual patterns, detect anomalies, and simulate real-world traffic investigation in a SOC environment.

## 2. Data Source

* PCAP file containing captured network traffic
* Analysis performed using Wireshark

## 3. Methodology

The following steps were taken during analysis:

### 3.1 Traffic Filtering

* Applied Wireshark display filters such as:

  * `http`
  * `tcp.stream eq X`
* Isolated HTTP requests for focused analysis
* "http.request.method == "POST" and frame.len > 500"

### 3.2 Packet Inspection

* Examined HTTP request methods (GET, POST)
* Reviewed headers, URIs, and response codes
* Identified irregular or unexpected values

### 3.3 Stream Analysis

* Followed TCP streams to reconstruct full communication sessions
* Observed interaction between client and server

## 4. Findings

### 4.1 Unusual HTTP Requests

* Detected abnormal request patterns that deviated from typical browsing behavior
* Observed repeated or irregular access attempts to certain endpoints
* POST uploads to external servers: Bulk data is sent to attacker-controlled hosts  in POST request bodies.

### 4.2 Suspicious Patterns

* Identified anomalies in request structure and frequency
* Noted potentially suspicious URIs

### 4.3 Indicators of Compromise (IOCs)

* Unusual request frequency
* Suspicious endpoints
* possible data exfiltration

## 5. Analysis

The observed traffic patterns suggest possible reconnaissance or probing activity. While no confirmed malware was identified, the anomalies indicate behavior that warrants further investigation in a real-world environment.

## 6. Conclusion

This analysis demonstrates the importance of packet-level inspection in detecting suspicious network activity. Wireshark proved effective in identifying anomalies and reconstructing communication sessions.

## 7. Skills Demonstrated

* Network Traffic Analysis
* Wireshark Usage
* HTTP Protocol Analysis
* Threat Detection
* Analytical Thinking


*End of Report*
