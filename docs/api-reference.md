# API Reference Guide

The AntiPay API is organized around REST. Our API has predictable resource-oriented URLs, returns JSON-encoded responses, and uses standard HTTP response codes, authentication, and verbs.

This guide will walk you through the process of creating a payment session and verifying it on your backend.

To start integrating, you will need an API Key which can be generated from your Brand Dashboard.

---

## Base URL
https://pay.antipay.site/v1/

---

## 1. Create Payment Session

POST /v1/create

### Request Parameters

- `amount` *(number, required)*  
  The total amount to be charged in BDT.

- `val_id` *(string, optional)*  
  Your internal reference (e.g. Order ID).

- `webhook_url` *(string, required)*  
  Your backend endpoint to receive payment updates.

- `redirect_success_url` *(string, required)*  
  Redirect URL after successful payment.

- `redirect_cancel_url` *(string, required)*  
  Redirect URL after cancel.

### Example (cURL)
```bash
curl -X POST "https://pay.antipay.site/v1/create" \
-H "Content-Type: application/json" \
-H "x-api-key: YOUR_API_KEY" \
-d '{
  "amount": 145.50,
  "val_id": "ORDER_88721",
  "webhook_url": "https://your-site.com/api/webhook",
  "redirect_success_url": "https://your-site.com/payment/success",
  "redirect_cancel_url": "https://your-site.com/payment/cancel"
}'
