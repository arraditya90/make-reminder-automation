# 📅 Automation Reminder - Google Sheets + Gmail (Make.com)

This project is an automated reminder system built using **Make.com** (formerly Integromat). It reads deal data from a Google Sheet and sends personalized follow-up emails to lenders who haven't taken action within 2 days of receiving the deal.

---

## ✅ How It Works

### 1. 📥 Read Data from Google Sheets
- Connects to the **"Leads"** Google Sheet.
- Filters rows based on:
  - **Date Shared** is older than 2 days
  - **Status** is `"Pending"`
  - **Reminder Sent** is `"No"`

### 2. 📤 Send Reminder Emails
- Sends an email to the lender’s email address.
- The email includes:
  - Lender Name
  - Deal ID
  - Date Shared
  - A polite reminder to take action

### ✨ (Optional Enhancements)
- **Update “Reminder Sent”** field to `"Yes"` after email is sent
- **Schedule the scenario to run daily** using a Scheduler module

---

## ⚙️ Why Make.com?

- 🧱 **No-code/Low-code**: Easy to implement and iterate without programming
- 🔗 **Native integrations**: With Google Sheets and Gmail
- 🖼️ **Visual builder**: Makes the workflow easy to build, debug, and scale
- 🔁 **Scalability**: Easily adapts to more rows or additional branching logic

Alternatives like **Zapier** or **n8n** are viable, but **Make.com** offers:
- Superior date logic
- More robust filter conditions
- Advanced customizations with ease

---

## 💡 Future Improvements

If extended further, here’s what could be added:

- ✅ Automatically update `"Reminder Sent"` to `"Yes"` after sending
- 💬 **WhatsApp reminders** via Twilio or Meta’s WhatsApp API
- 📊 Logging to a separate Google Sheet for tracking sent reminders
- 🛠️ Built-in **error handling** and fallback notifications
- 🧑‍💼 Manual override or opt-out column (e.g., `"Exclude = Yes"`)
- 🧠 Dynamic templates based on delay duration (2 days, 5 days, etc.)

---

## 🔧 Technical Details

### 📄 Google Sheet Columns:
| Column | Label             |
|--------|-------------------|
| A      | Deal ID           |
| B      | Lender Name       |
| C      | Lender Email      |
| D      | Date Shared       |
| E      | Status            |
| F      | Reminder Sent     |

### 🔌 Make.com Modules:
- **Module 1**: Google Sheets - *Filter Rows*
- **Module 2**: Gmail - *Send Email*

### ✉️ Email Template:
```html
Hi {{Lender Name}},<br><br>

This is a gentle reminder to take action on <strong>Deal ID: {{Deal ID}}</strong>,<br>
which was shared with you on <strong>{{Date Shared}}</strong>.<br><br>

Please get back to us as soon as possible.<br><br>

Regards,<br>
Team Recur Club
