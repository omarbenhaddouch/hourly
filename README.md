
# Hourly Production Monitoring Dashboard
**CITIC Dicastal — SW CNC Production Line**

## Purpose

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

- Password-protected data clearing to prevent accidental loss of shift records

<img width="1179" height="1865" alt="image" src="https://github.com/user-attachments/assets/d4b5ee77-86ee-4652-ad8c-c726895f04ff" />

**password : 1234**

- ☁️ Automatically save production data to Firebase every 1s
- 📈 View live production data in the Manager Dashboard
- 🔄 Real-time synchronization between devices
- 📱 Responsive design for phones, tablets, and computers


### Manager Dashboard (live view)
- Real-time clock and auto-refreshing data (updates every second) — always current, no manual refresh needed.
- **OEE / Efficiency %** headline figure for the line.
- **Machine Status** grid — at-a-glance which machines are on target vs. off target (color-coded).
- **Actual vs. Target** chart across all machines.
- **Efficiency % by machine** chart.
- **Cumulative production trend** over the shift.
- **Top 5 machines by output** ranking.
- Installable as a PWA (Progressive Web App) — can be added to a phone/tablet home screen and used like a native app, including on iPhone/iPad.

# 🖼️ Report Shift

## 📸 Report Button

Anytime or at the end of the shift, click the **Report** button in the top action bar. This function automatically creates a professional **A4 Landscape production report** as a PNG image.

<img width="2048" height="1448" alt="image" src="https://github.com/user-attachments/assets/2ea31d3e-5fb0-4371-9110-3b00d30ccc9b" />


### How the Report Works

1. Complete the hourly production data for the shift.
2. Make sure the correct **Date** and **Shift** are selected.
3. Click **Report**.
4. The application automatically collects all machine data and calculates the final shift summary.
5. A formatted **A4 Landscape report image** is generated.
6. Depending on the device, the user can **Share**, **Save**, or **Download** the PNG report.

Example generated filename:

```text
monitoring_2026-08-30_shiftA.png
```

This makes the Report function useful for **end-of-shift documentation, supervisor review, production meetings, and sending the final shift results to management**.

---

### 📊 Information Included in the Generated Report

The end-of-shift report automatically includes:

- 🏭 Company and application header
- 📅 Production date
- 🔤 Shift letter
- 🕒 Report generation time
- 🎯 **Total Plan**
- 📦 **Total Actual Production**
- 📈 **Overall Efficiency / OEE percentage**
- 🟢 Number of machines **On Target**
- 🔴 Number of machines **Off Target**
- ⚠️ Number of machines with logged issues/comments
- 👷 Operator number for every machine
- 🧩 Part name for every machine
- 🎯 Target per hour
- ⏱️ All hourly production values (H1–H8)
- 🧮 Planned and actual totals for every machine
- 🏷️ Comments and downtime tags
- 📊 Final totals row
- 🔐 Generated timestamp and report footer


## How It Works (Technical Overview)

- **Frontend:** Vanilla JavaScript, HTML, CSS (no framework overhead) — split into separate, maintainable files rather than one monolithic page.
- **Charts:** Chart.js for all live visualizations.
- **Backend / Data:** Firebase — real-time database so data entered on one device appears instantly on the manager dashboard on another.
- **Hosting:** Deployed via Github.

## Benefits to the Line

- **Less admin overhead:** no paper forms to transcribe or file.
- **Better decisions:** management can see trends (which machines/shifts underperform) and act on data instead of impressions.
- **Transparency:** one shared source of truth for hourly output across all shifts.

# 👨‍💻 Developed By

**Omar Ben Haddouch**

**License**
This project was developed for educational and professional portfolio purposes.
