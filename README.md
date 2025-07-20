
# 📅 Placement Details -  Calendar Automation (n8n Workflow)

This n8n workflow automates the process of extracting placement opportunity details from emails and adds them to a Google Calendar.

---

## 🚀 Features

- **Email Trigger (Gmail):** Watches for new emails from `pc.rajagiri@gmail.com`.
- **LLM Extraction (LangChain + Google Gemini):** Extracts structured placement details like company name, eligibility, and deadlines from the email content.
- **Google Calendar Integration:** Automatically creates a calendar event with relevant info like CGPA, salary, and registration link.

---

## 📦 Workflow Overview

1. **Gmail Trigger**: Checks for new emails from a specific sender every minute.
2. **Field Formatter**: Extracts and cleans important fields (sender, subject, text, date).
3. **LLM Chain (LangChain)**: Uses a prompt-based language model to extract structured placement info as JSON.
4. **Structured Output Parser**: Ensures the LLM output adheres to a fixed JSON schema.
5. **Google Calendar Node**: Creates a calendar event based on the extracted details.

---

## 📂 Required Credentials

To use this workflow, set up the following credentials in your n8n instance:

- ✅ **Gmail OAuth2** — to read placement-related emails.
- ✅ **Google Gemini (PaLM) API** — for extracting structured placement info using LLM.
- ✅ **Google Calendar OAuth2** — to create calendar events.

> 🛡️ Credentials are referenced by ID in the workflow. You’ll need to reassign them after importing this workflow.

---

## 🧪 Example Output (from LLM)
<img width="1558" height="906" alt="image" src="https://github.com/user-attachments/assets/75e05f45-bc1b-4f21-b419-83b461763108" />


```json
{
  "company_name": "DeltaX",
  "job_role": "Associate Product Engineer",
  "eligibility_criteria": {
    "branches": ["AD", "CS", "CSBS", "IT"],
    "cgpa": "6.5",
    "graduation_year": "2026"
  },
  "salary_package": "INR 7 LPA CTC",
  "last_date_to_register_with_time": "2025-07-21T17:00:00",
  "test_or_event_date": null,
  "application_link": "https://forms.gle/e2QoZSVpma4q99DT9",
  "job_location": "Bangalore, Hyderabad, Pune"
}



