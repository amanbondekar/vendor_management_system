﻿# vendor_management_system
# Vendor Management System

Vendor Management System is a Django-based application designed to handle vendor profiles, track purchase orders, and calculate vendor performance metrics.

## Table of Contents

- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [API Endpoints](#api-endpoints)
  - [Vendor Management](#vendor-management)
  - [Purchase Order Tracking](#purchase-order-tracking)
  - [Vendor Performance Evaluation](#vendor-performance-evaluation)
- [Running Tests](#running-tests)
- [Contributing](#contributing)

## Getting Started

### Prerequisites

- Python 3.x
- Virtual Environment (optional but recommended)

### Installation

1. **Clone the repository:**

    ```bash
    git clone https://github.com/your-username/vendor-management-system.git
    cd vendor-management-system
    ```

2. **Create and activate a virtual environment:**

    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows: venv\Scripts\activate
    ```

3. **Install dependencies:**

    ```bash
    pip install -r requirements.txt
    ```

4. **Run migrations:**

    ```bash
    python manage.py migrate
    ```

5. **Load initial data (optional):**

    ```bash
    python manage.py loaddata initial_data
    ```

## API Endpoints

### Vendor Management

- **Create a new vendor:**
  - `POST /api/vendors/`
  - Request Body:
    ```json
    {
      "name": "Vendor1",
      "contact_details": "Contact1",
      "address": "Address1",
      "vendor_code": "V1"
    }
    ```

- **List all vendors:**
  - `GET /api/vendors/`

- **Retrieve a specific vendor's details:**
  - `GET /api/vendors/{vendor_id}/`

- **Update a vendor's details:**
  - `PUT /api/vendors/{vendor_id}/`
  - Request Body:
    ```json
    {
      "name": "UpdatedVendorName"
    }
    ```

- **Delete a vendor:**
  - `DELETE /api/vendors/{vendor_id}/`

### Purchase Order Tracking

- **Create a purchase order:**
  - `POST /api/purchase_orders/`
  - Request Body:
    ```json
    {
      "po_number": "PO123",
      "vendor": 1,
      "order_date": "2023-01-01",
      "delivery_date": "2023-02-01",
      "items": {"item1": 5, "item2": 10},
      "quantity": 15,
      "status": "pending"
    }
    ```

- **List all purchase orders:**
  - `GET /api/purchase_orders/`

- **Retrieve details of a specific purchase order:**
  - `GET /api/purchase_orders/{po_id}/`

- **Update a purchase order:**
  - `PUT /api/purchase_orders/{po_id}/`
  - Request Body:
    ```json
    {
      "status": "completed"
    }
    ```

- **Delete a purchase order:**
  - `DELETE /api/purchase_orders/{po_id}/`

### Vendor Performance Evaluation

- **Retrieve a vendor's performance metrics:**
  - `GET /api/vendors/{vendor_id}/performance/`

## Running Tests

To run the test suite, use the following command:

```bash
python manage.py test
