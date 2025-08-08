
# 📄 PSP Webhook Notification – Troubleshooting & Classification Guide

## 🔍 Purpose

This document outlines the process of checking webhook notifications received from Payment Service Providers (PSPs). It also explains the classification of webhook handling methods and provides a detailed guide to troubleshoot missing or delayed notifications.

---

## 📚 Classification of Webhook Handling

Webhook notifications from PSPs are handled in two primary ways:

1. **Traditional Method**
2. **PSP Engine Method**

This document focuses on the **Traditional Method**.

---

## 1️⃣ Traditional Method

### 🛠 Where to Check:
- **IIS API Logs** – These logs capture all incoming webhook notifications from PSPs.
- Use these logs to trace transactions and confirm whether a webhook was received for a particular transaction.

### 🔍 How to Check:
1. **Identify the Transaction**:
   - Use the **Transaction ID** or the **Payment Gateway Name** associated with the transaction you are investigating.

2. **Locate the Logs**:
   - Navigate to the **IIS API log directory** corresponding to the date the transaction was expected.

3. **Verify Log Entries**:
   - Search for the transaction details in the logs using identifiers such as Transaction ID or gateway name.

4. **Check Date Accuracy**:
   - Ensure you are looking at the **correct log date**.
   - If no entry is found for the expected date, check the **following day's log file**.
     - Webhook delivery timing varies by PSP. Some send notifications immediately; others may delay by a few hours or up to a full day.

5. **Handling Missing Notifications**:
   - In some scenarios, **webhook notifications may not be received at all** due to issues at the PSP's end.
   - If no relevant log is found even after checking subsequent days, consider raising a query with the respective PSP.

---

## ⚠️ Important Notes

- Webhook response time is **PSP-dependent**.
- Some gateways are **synchronous** and respond instantly, while others operate **asynchronously** and may take longer.
- Always **verify transaction timestamps** before concluding a webhook is missing.
- **Maintain logs for at least 7 days** to allow for late notifications.
