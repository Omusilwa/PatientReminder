## Clinical Reminder

Send automated next-day clinic appointment reminders to patients via email, powered by Python and CSV data.

  - **Stack**: `datetime` (`dt`), `random`, `pandas`, `smtplib`
  - **Data sources**: `patients.csv`, `clinics.csv`, `doctors.csv`, `smtp_config.csv`
  - **Scheduler**: OS-level (Windows Task Scheduler / cron)

---
### 1) What this does
- Reads patient, clinic, and doctor rosters from CSV files.
- Validates and aligns each patient’s booked date_of_visit with clinic sessions.
- Every day, finds all appointments scheduled for tomorrow.
- Sends each patient a plain-text reminder email containing:
    - Patient name
    - Clinic name
    - Date of visit
    - Assigned doctor
- Ensures idempotency (no duplicate reminders for the same visit).
- Optionally randomizes send order and (if not assigned) doctor selection.

---
