# Weather MCP Server

A Model Context Protocol (MCP) server that provides weather forecast and alert tools using the [National Weather Service (NWS) API](https://www.weather.gov/documentation/services-web-api).

## Tools

### `get_forecast`
Retrieves a weather forecast for a given location.

**Parameters:**
- `latitude` (float) — Latitude of the location
- `longitude` (float) — Longitude of the location

> **Note:** The NWS API only covers US locations.

### `get_alerts`
Retrieves active weather alerts for a US state.

**Parameters:**
- `state` (string) — Two-letter US state code (e.g. `CA`, `NY`)

## Setup

### Prerequisites
- Python 3.10+
- [uv](https://docs.astral.sh/uv/) package manager

### Install dependencies

```bash
uv sync
```

### Run the server

```bash
uv run mcp run weather.py
```

### Test with MCP Inspector

```bash
uv run mcp dev weather.py
```

This opens the MCP Inspector in your browser where you can interactively test the tools.

## Example Usage

**Forecast for New York City:**
- latitude: `40.7128`
- longitude: `-74.0060`

**Alerts for California:**
- state: `CA`

## Dependencies

- [httpx](https://www.python-httpx.org/) — Async HTTP client
- [mcp[cli]](https://modelcontextprotocol.io/) — Model Context Protocol SDK
