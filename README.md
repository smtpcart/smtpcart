<p align="center">
  <a href="https://smtpcart.com/"><img src="https://smtpcart.com/wp-content/uploads/2026/09/SMTPCart_Logo_Image.png" alt="SMTPCart" width="260"></a>
</p>

<h3 align="center">Your business email, in the inbox. Every time.</h3>

<p align="center">
  <a href="https://smtpcart.com/">Website</a> ·
  <a href="https://www.linkedin.com/company/smtpcartcom/">LinkedIn</a> ·
  <a href="https://www.crunchbase.com/organization/smtpcart">Crunchbase</a> ·
  <a href="https://dev.to/smtpcartcom">DEV</a>
</p>

---

**SMTPCart** is a managed SMTP relay for businesses whose email has to arrive: order confirmations, invoices, password resets, booking reminders and newsletters.

You connect your app over standard SMTP. We run the sending infrastructure behind it.

### What we handle

- **Authentication**: SPF, DKIM and DMARC setup, plus TLS encryption
- **Reputation**: isolated or dedicated IPs, domains and routing
- **Warm-up**: planned volume ramp for new IPs and domains
- **Monitoring**: daily checks on bounces, complaints and blocklists
- **Separation**: transactional and marketing streams kept apart
- **Migration**: phased move from your current provider, run in parallel until each stream is proven

### Works with anything that speaks SMTP

WordPress & WooCommerce · Laravel · Django · Ruby on Rails · Node.js (Nodemailer) · PHP (PHPMailer) · CRMs, booking, billing and help desk tools

Every SMTP client needs the same four settings. Use the host, port and credentials from your SMTPCart account:

```env
SMTP_HOST=<your SMTPCart host>
SMTP_PORT=587          # STARTTLS
SMTP_USER=<your SMTPCart username>
SMTP_PASS=<your SMTPCart password>
```

<details>
<summary><b>Node.js (Nodemailer)</b></summary>

```js
import nodemailer from "nodemailer";

const transporter = nodemailer.createTransport({
  host: process.env.SMTP_HOST,
  port: 587,
  secure: false, // STARTTLS is negotiated on 587
  auth: { user: process.env.SMTP_USER, pass: process.env.SMTP_PASS },
});

await transporter.sendMail({
  from: '"Your Shop" <orders@yourdomain.com>',
  to: "customer@example.com",
  subject: "Your order has shipped",
  text: "Thanks for your order!",
});
```
</details>

<details>
<summary><b>Laravel (.env)</b></summary>

```env
MAIL_MAILER=smtp
MAIL_HOST=${SMTP_HOST}
MAIL_PORT=587
MAIL_USERNAME=${SMTP_USER}
MAIL_PASSWORD=${SMTP_PASS}
MAIL_ENCRYPTION=tls
MAIL_FROM_ADDRESS=orders@yourdomain.com
```
</details>

<details>
<summary><b>Django (settings.py)</b></summary>

```python
import os

EMAIL_BACKEND = "django.core.mail.backends.smtp.EmailBackend"
EMAIL_HOST = os.environ["SMTP_HOST"]
EMAIL_PORT = 587
EMAIL_USE_TLS = True
EMAIL_HOST_USER = os.environ["SMTP_USER"]
EMAIL_HOST_PASSWORD = os.environ["SMTP_PASS"]
DEFAULT_FROM_EMAIL = "orders@yourdomain.com"
```
</details>

<details>
<summary><b>WordPress / WooCommerce</b></summary>

Install any SMTP plugin (for example WP Mail SMTP or FluentSMTP), choose **Other SMTP**, and enter your SMTPCart host, port 587 with TLS, username and password.
</details>

### Plans

| Plan | Volume | Highlights |
|---|---|---|
| Essentials | up to 50K emails/month | Isolated pool, SPF/DKIM/DMARC setup, daily monitoring |
| Growth | 50K – 1M emails/month | Separate streams, dedicated IP when volume supports it, managed warm-up |
| Dedicated | 1M+ emails/month | Dedicated IPs, domains and routing, capacity planning |
| Enterprise | Custom | Custom regions and terms, DPA, dedicated deliverability team |

Pricing is quoted after a short assessment, with no hidden overage fees. **[Get a free deliverability check →](https://smtpcart.com/)**

---

<sub>SMTPCart is a BEINCART LLC company · team@smtpcart.com</sub>
