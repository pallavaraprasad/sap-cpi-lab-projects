# IF_I00001_Ecom_Order_Mail

SAP CPI iFlow: receives e-commerce order XML over HTTPS and sends a
dynamic email through Gmail SMTP.

## Flow
Sender (HTTPS) → Content Modifier → Mail Receiver (Gmail)

## Features
- Recipient read from payload using XPath (//email → header MailID)
- Dynamic subject/body using Camel Simple Expression Language
- Gmail App Password stored as Security Material (Gmail_Key)

## Mail Adapter
Address: smtp.gmail.com:587 | Protection: STARTTLS | Auth: Plain User/Password

## How to Test
1. Deploy iFlow
2. POST sample-payload/order_input.xml from Postman
3. Check inbox and CPI Monitor

## Tech Stack
SAP Integration Suite, Apache Camel, XPath, Gmail SMTP
