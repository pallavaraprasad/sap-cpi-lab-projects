# 02 - HTTP to SFTP (Poll Enrich)
Overview
Receives an Invoice XML from JSW ERP via HTTPS, dynamically polls and pulls the matching Order file from BME SFTP (/Processed_OrderData) using Poll Enrich, combines both payloads, and sends the final data to the destination SFTP server.

Step-by-Step Flow
HTTPS Receiver: Receives Invoice XML from JSW ERP.

Property Extraction: Extracts Order_Filename from the payload.

Poll Enrich: Pulls the matching order file from BME SFTP (/Processed_OrderData).

Data Combination: Merges Invoice XML and Order data into one payload.

SFTP Sender: Transmits the combined payload to the target SFTP destination.

Key Components
HTTPS Adapter: For receiving invoice payload.

Poll Enrich Pattern: For dynamic SFTP file retrieval.

SFTP Adapter: For file transfer.

Content Modifier / Script: For parameter extraction and payload merging.
