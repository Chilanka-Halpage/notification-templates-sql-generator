# Notification Template SQL Generator

A single-page web tool that generates Oracle `MERGE` (insert) and `MERGE ... WHEN MATCHED` (update)
scripts for the notification template tables

Type the Arabic text normally; the tool converts it to the escaped formats the database expects.

## Features

- Inputs: event ID, institute IDs (blank = all), SMS, email subject, email template and push notification templates, each with an Arabic version
- Arabic encoding per field: `\uXXXX`, `UNISTR('\XXXX')`, or HTML entities `&#xXXXX;`
- Target table selector, with **Change status** (Add = 1 / Edit = 2) for the customized `_c` table
- **Rebranded templates**: builds the styled HTML (header band with configurable colour, default `#0f2a4a`) and sets `m149_template_mode = 1`
- Email templates written as `TO_CLOB(...)`, split automatically only if a literal would exceed Oracle's 4000-byte limit
- Insert, Update, or both; optional `SET DEFINE OFF` and `COMMIT`
- Syntax-highlighted output, copy and download as `.sql`, light/dark theme

## Privacy

Everything runs in your browser. Nothing you type is sent to a server or stored.

## Run locally

Open `index.html` in any modern browser. No build step or dependencies.

## Licence

Copyright (c) 2026 Chilanka Halpage. All rights reserved. See [LICENSE](LICENSE).
