# 03 - Country-Based Order Routing

An e-commerce app sends order JSON over HTTPS to SAP CPI with a CountryCode header. A Router sends the order to an HTTP receiver (IN), SFTP receiver (US) or Mail receiver (UK).
The routing header is deleted before the receiver.

## Key points
- Router uses Non-XML expressions on the CountryCode header.
- Allowed Header(s) lets CPI accept the header, so JSON/XML converters are not needed.
- A Content Modifier deletes CountryCode before the receiver.
