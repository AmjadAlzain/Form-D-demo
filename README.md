# Form-D Converter Service

This project is a containerized web application and API service designed to automate the conversion of shipment spreadsheets into the K1 Import format (XLSX).

It features a lightweight FastAPI backend for data processing and a simple HTML/JS frontend for user interaction.

## Features

-   **Automated Conversion:** Transforms complex Excel/CSV shipment data into the strict K1 format required for import declarations.
-   **Intelligent HS Code Mapping:** Uses an optimized, in-memory JSON lookup to map thousands of HS Codes to their correct Statistical Units (KGM, UNT, etc.).
-   **Performance:** High-speed processing using Pandas and direct JSON indexing, capable of handling large datasets instantly.
-   **Containerized:** Fully Dockerized for consistent deployment across any environment (Local, Cloud Run, AWS, Azure).
-   **API First:** Exposes a RESTful endpoint (`/api/convert`) for integration with other systems.

## Project Structure

```text
.
├── Dockerfile              # Instructions for building the container image
├── server/
│   ├── app/
│   │   ├── main.py         # FastAPI entry point and routing
│   │   ├── convert.py      # Core conversion logic and data mapping
│   │   └── __init__.py
│   ├── templates/
│   │   ├── HSCODE.json     # Optimized HS Code mapping database
│   │   └── K1...Template.xls # Base template for output generation
│   ├── tests/              # Unit tests
│   └── requirements.txt    # Python dependencies
└── web/                    # Static frontend assets (HTML, CSS, JS)