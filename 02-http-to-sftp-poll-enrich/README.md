# 02 - HTTP to SFTP (Poll Enrich)

## Overview
This integration receives an Invoice XML from JSW ERP over HTTPS in SAP CPI. Using the `Order_Filename` value from the Invoice, it retrieves the matching Order file from the BME SFTP server (`/Processed_OrderData`) with the Poll Enrich step, combines both payloads, and sends the final file to the target SFTP folder.

## Flow
1. **HTTPS Sender:** Receives the Invoice XML from JSW ERP.
2. **Content Modifier:** Extracts `Order_Filename` from the payload using XPath and stores it as a property.
3. **Poll Enrich:** Pulls the matching Order file from SFTP using `${property.Order_Filename}`.
4. **Aggregation:** Merges the Invoice and Order data into a single payload.
5. **SFTP Receiver:** Writes the combined file to `/JSW_OrderData_Receiver`.

## Key Components
- HTTPS Adapter (sender)
- Content Modifier
- Poll Enrich (dynamic SFTP file retrieval)
- SFTP Adapter (receiver)

## Folder Structure
| Folder | Content |
|---|---|
| `iflow/` | Exported iFlow zip |
| `screenshots/` | iFlow and SFTP screenshots |
| `test-data/` | Sample Invoice, Order and combined output XML |

## Sample Input
The Invoice contains `<Order_Filename>ORD00994.xml</Order_Filename>`. The referenced file must exist in the `/Processed_OrderData` folder on the SFTP server.
