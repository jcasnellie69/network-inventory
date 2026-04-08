# Network Inventory Dashboard

A web-based network inventory dashboard for a **MOKERLINK 12-Port Switch** with **Pi-hole DNS correlation**. Displays all discovered network devices with enriched metadata, port mappings, and DNS hostname resolution.

## Overview

This dashboard correlates switch port data with Pi-hole DNS query logs to provide a comprehensive view of your local network. Each device entry includes:

- Switch port assignment (MOKERLINK 12-port)
- Pi-hole DNS hostname (when available)
- MAC address and IP address
- Device category and vendor
- Online/offline status
- Priority classification

## Data Summary

| Attribute | Value |
|-----------|-------|
| Total Devices | **124** |
| Filterable by | Status, Priority, Port, Category |

### Filter Options

- **Status**: Online / Offline / Unknown
- **Priority**: Critical / High / Medium / Low
- **Port**: Switch port 1–12
- **Category**: Server, IoT, Network, Workstation, etc.

## How to View

This dashboard is hosted via **GitHub Pages**:

👉 **[View Live Dashboard](https://jcasnellie.github.io/network-inventory/)**

To run locally, simply open `index.html` in any modern web browser — no build step required.

## Files

| File | Description |
|------|-------------|
| `index.html` | Dashboard UI with filtering and search |
| `network-inventory.json` | Device inventory data (124 devices) |

## Tech Stack

- Vanilla HTML/CSS/JavaScript (no dependencies)
- JSON data source
- GitHub Pages for hosting
