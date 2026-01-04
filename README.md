# Odoo 19 Developer Assessment

## Overview
**Time Limit:** 3-4 hours  
**Odoo Version:** 19.0 Community Edition  

---

## Business Context

A company uses biometric devices (fingerprint scanners) at office entrances to track employee attendance. They need an Odoo module to:

1. **Manage devices** — Register devices installed at different locations
2. **Collect punch data** — Store attendance records sent from devices
3. **Integrate with devices** — Receive data via API from external devices

---

## Requirements

### Part 1: Device Management (30%)

The system must allow HR managers to:

- Register new biometric devices with their connection details (IP, port, serial number, etc.)
- Track where each device is physically located
- See which devices are currently active or inactive
- Know when a device last synchronized data
- Ensure no two devices share the same serial number
- Test if a device is reachable (simulated — just update status and notify user)

---

### Part 2: Attendance Records (30%)

When devices send attendance data, the system must:

- Store each punch with: which device sent it, which employee, timestamp, and whether it's a check-in or check-out
- Track which records have been processed and which are pending
- Allow marking records as processed or flagging errors
- Handle the case when a device is deleted (what happens to its records?)

---

### Part 3: User Interface (20%)

Create appropriate views so HR managers can:

- View and manage all registered devices
- See attendance records with filtering options (by device, by status, by date)
- Quickly identify device status and record states visually
- Navigate the module from the Attendances app menu

---

### Part 4: API Endpoint (20%)

External devices need to push attendance data to Odoo. Create an endpoint that:

- Accepts attendance punches from a device (device identifier + list of punches)
- Validates the device exists and is active
- Creates attendance records for valid data
- Updates the device's last sync timestamp
- Returns a response indicating success/failure with details

---

## Deliverables

1. A complete, installable Odoo module
2. Proper security access rights
3. Brief README with:
   - Any assumptions you made
   - How to test the main features

---

## Evaluation Criteria

| What We Evaluate | Examples |
|------------------|----------|
| **Data modeling decisions** | Field types, relationships, constraints |
| **Odoo conventions** | Naming, module structure, coding standards |
| **User experience** | Logical views, appropriate widgets, usability |
| **API design** | Route design, error handling, response format |
| **Code quality** | Readability, organization, documentation |

We value **working, well-structured code** over feature completeness.

---

## Tips

- Plan your data model before coding
- Test that your module installs cleanly
- Odoo's `hr_attendance` module is a good reference
- Handle errors gracefully with clear messages
- Document any design decisions in your README

**Good luck! 🚀**
