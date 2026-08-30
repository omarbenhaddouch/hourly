
# Hourly Production Monitoring Dashboard
**CITIC Dicastal — SW CNC Production Line**

## 1. Purpose

This tool digitizes and automates hourly production tracking on the SW CNC line, replacing manual paper shift logs with a live, shared, web-based system. It gives operators a fast way to record hourly output per machine, and gives supervisors and management a real-time, visual view of line performance (OEE, efficiency, actual vs. target) without waiting for end-of-shift reports.


## 📸 Application Preview

## Live app: 
https://omarbenhaddouch.github.io/hourly
### 📱 Mobile View
<img width="2358" height="5112" alt="image" src="https://github.com/user-attachments/assets/803c5d32-28b2-4dca-9e5c-588227f058a6" />

### Manager Dashboard: 
https://omarbenhaddouch.github.io/hourly/dashboard

<img width="2358" height="5112" alt="image" src="https://github.com/user-attachments/assets/96b8f8d1-4834-476d-9033-c1bf55252dc6" />

### 💻 Desktop / Manager Dashboard:

<img width="7680" height="4320" alt="image" src="https://github.com/user-attachments/assets/31e60342-33b0-4ca6-93d9-38d4a33857e2" />



# 🚀 Main Features

- 📅 Select production **date and shift**
<img width="2048" height="572" alt="Untitled design" src="https://github.com/user-attachments/assets/15668239-c07c-430f-866b-4013aa664933" />



- 🏭 Monitor **21 CNC machines**
- 👷 Record the operator number (matricule) for each machine
<img width="500" height="759" alt="image" src="https://github.com/user-attachments/assets/9bdde946-f3bf-45f3-b510-0dedda4ee0b0" />

- 🔧 Select the part/project running on each machine
<img width="457" height="658" alt="image" src="https://github.com/user-attachments/assets/996f04a5-8f95-469c-9e38-8a2aa4bbdb23" />

- 🎯 Automatically apply the production target per hour
- ⏱️ Enter production for up to **8 hourly periods**
- 📊 Automatically calculate planned production and actual production
- 🟢🟡🔴 Automatically show machine performance status
- 🏷️ Add downtime reason tags
<img width="1169" height="2048" alt="image" src="https://github.com/user-attachments/assets/9bb2bb32-b5c3-4f39-8535-bcddc34c2938" />

- ☁️ Automatically save production data to Firebase every 1s
- 📈 View live production data in the Manager Dashboard
- 🔄 Real-time synchronization between devices
- 📱 Responsive design for phones, tablets, and computers

## 3. What the App Does

### Data Entry (operator/team leader view)
- Select **date**, **shift** (A/B/C/D), and **hour block**.
- Log actual production per machine against target, across all 21 machines (MSA01–MSA21).
- Add machine rows as needed; save, load, and clear entries per shift.
- Password-protected data clearing to prevent accidental loss of shift records.
- Shift log view to review what has been entered for a given shift/date.

### Manager Dashboard (live view)
- Real-time clock and auto-refreshing data (updates every second) — always current, no manual refresh needed.
- **OEE / Efficiency %** headline figure for the line.
- **Machine Status** grid — at-a-glance which machines are on target vs. off target (color-coded).
- **Actual vs. Target** chart across all machines.
- **Efficiency % by machine** chart.
- **Cumulative production trend** over the shift.
- **Top 5 machines by output** ranking.
- Installable as a PWA (Progressive Web App) — can be added to a phone/tablet home screen and used like a native app, including on iPhone/iPad.

## 4. How It Works (Technical Overview)

- **Frontend:** Vanilla JavaScript, HTML, CSS (no framework overhead) — split into separate, maintainable files rather than one monolithic page.
- **Charts:** Chart.js for all live visualizations.
- **Backend / Data:** Firebase (project `factory-monitor-70095`) — real-time database so data entered on one device appears instantly on the manager dashboard on another.
- **Design:** Dark industrial HUD-style interface (glassmorphism panels, cyan/green/red status colors, monospace + technical fonts) designed to be readable at a glance on the shop floor and in the office.
- **Hosting:** Deployed via Netlify, accessible from any browser — desktop, tablet, or phone — no installation required (with optional PWA install for quick access).

## 5. Scope

- Coverage: 21 SW CNC machines (MSA01–MSA21).
- Shifts: A, B, C, D.
- Data granularity: hourly, per machine, per shift.

## 6. Benefits to the Line

- **Faster reaction time:** off-target machines are visible immediately, not at shift-end.
- **Less admin overhead:** no paper forms to transcribe or file.
- **Better decisions:** management can see trends (which machines/shifts underperform) and act on data instead of impressions.
- **Transparency:** one shared source of truth for hourly output across all shifts.
- **Low cost / no license fees:** built in-house with free-tier tools (Netlify + Firebase), no purchased software.

## 7. Status & Next Steps

This is a working, actively used prototype. Suggested next steps for wider rollout:
- Gather feedback from team leaders after a trial period on the line.
- Define user roles/permissions (operator entry vs. manager-only views).
- Add historical reporting/export (e.g., daily/weekly summary export).
- Evaluate integrating with existing plant systems if/when needed.

---
*Developed internally by Omar — Machining / SW CNC Production Line Department.*
