
# Webhook Integration

AntiPay sends a webhook request when payment status changes.

## Why Webhook?
Webhook is the reliable server-to-server notification system.  
Do not trust redirect parameters alone.

## Webhook Payload
```json
{
  "status": "verified",
  "trxId": "8J9A1X7K",
  "amount": 145.5,
  "sessionId": "SESS_123",
  "val_id": "ORDER_88721"
}
