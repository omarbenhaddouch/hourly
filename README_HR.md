# ⏱️ Hourly Production Monitoring Dashboard

### CITIC Dicastal — SW CNC Production Line

A real-time web application designed to monitor hourly production across the SW CNC production line. The system replaces manual paper-based production logs with a shared digital solution where operators enter production data and managers can monitor performance live.

## 📸 Application Preview

### 📱 Mobile View

<img width="2358" height="5112" alt="Hourly Production Monitoring Dashboard on mobile" src="https://github.com/user-attachments/assets/96b8f8d1-4834-476d-9033-c1bf55252dc6" />

### 💻 Desktop / Manager Dashboard

<img width="7680" height="4320" alt="Hourly Production Monitoring Dashboard on desktop" src="https://github.com/user-attachments/assets/31e60342-33b0-4ca6-93d9-38d4a33857e2" />

### 🖥️ Full Application View

<img width="2358" height="5112" alt="Hourly monitoring application" src="https://github.com/user-attachments/assets/803c5d32-28b2-4dca-9e5c-588227f058a6" />

---

# 🚀 Main Features

- 📅 Select production **date and shift**
- 🏭 Monitor **21 CNC machines**
- 👷 Record the operator number for each machine
- 🔧 Select the part/project running on each machine
- 🎯 Automatically apply the production target per hour
- ⏱️ Enter production for up to **8 hourly periods**
- 📊 Automatically calculate planned production and actual production
- 🟢🟡🔴 Automatically show machine performance status
- 🏷️ Add downtime reason tags
- ☁️ Automatically save production data to Firebase
- 📈 View live production data in the Manager Dashboard
- 🔄 Real-time synchronization between devices
- 📱 Responsive design for phones, tablets, and computers

---

# 🧭 How the Application Works

## 1. Select the Date and Shift 📅

The operator first selects the production date and the shift.

The application supports four shifts:

| Shift | Description |
|---|---|
| A | Shift A production data |
| B | Shift B production data |
| C | Shift C production data |
| D | Shift D production data |

Each date and shift can have its own production record, allowing the system to keep production information separated correctly.

---

## 2. Machine Production Table 🏭

The main screen contains a production table for the SW CNC machines.

The default configuration includes:

**MSA01 → MSA21**

Each machine row contains the following information:

| Field | How it works |
|---|---|
| **Machine** | Displays the machine identification number |
| **Operator** | Enter the operator number assigned to the machine |
| **Part Name** | Select the part currently being produced |
| **Target/hr** | Production target expected every hour |
| **H1 – H8** | Enter actual production for each hour |
| **Total Plan** | Automatically calculates target × number of hours |
| **Actual** | Automatically totals all hourly production values |
| **Status** | Shows whether the machine is meeting its target |
| **Comments / Tags** | Add reasons for downtime or production issues |

---

# 🔧 Functions Explained

## 👷 Operator Number

The **Operator** field allows the user to enter the identification number of the person operating the machine.

This helps identify who was assigned to each machine during the selected shift.

Example:

```text
Machine: MSA01
Operator: 12345
```

When the value is changed, the application updates the machine data and automatically prepares it for saving.

---

## 🧩 Part Name Selection

Each machine can be assigned a production part from the available list.

Examples include:

- T-opal Front
- T-opal Rear
- VOLVO front LH
- VOLVO front RH
- VOLVO REAR
- GM-H
- GM S
- MEB 31 Front
- MEB 31 Rear
- NISSAN P42
- HONDA
- FORD
- FIAT

### How it works

When a part is selected, the application automatically assigns the correct **hourly production target** using the internal part-to-target map.

Example:

```text
Part: HONDA
Target per hour: 48
```

This avoids manually entering the production target every time a machine changes to a known part.

---

## 🎯 Target Per Hour

The **Target/hr** value represents the expected production quantity for one hour.

The target can be automatically assigned from the selected part and can also be edited when needed.

The target is used to calculate:

- Total planned production
- Machine efficiency
- Machine status
- Hourly performance colors

---

## ⏱️ Hourly Production Entry

The application provides hourly fields from:

```text
H1 → H8
```

The user enters the actual number of produced parts for each hour.

### Example

If the target is **24 parts/hour**:

| Hour | Actual Production |
|---|---:|
| H1 | 24 |
| H2 | 22 |
| H3 | 25 |
| H4 | 24 |

The application automatically evaluates the performance of each hourly value.

### Hourly Color Logic

🟢 **Green** — Production is at or above the target.

🟡 **Yellow** — Production is close to the target, approximately 80% or more.

🔴 **Red** — Production is significantly below the target.

This makes production problems easy to identify visually.

---

# 🧮 Automatic Calculations

## Total Plan

The system automatically calculates the planned production:

```text
Total Plan = Target per Hour × Number of Hours
```

### Example

```text
Target/hr = 24
Hours = 8

Total Plan = 24 × 8 = 192 parts
```

---

## Actual Production

The **Actual** value is calculated by adding all hourly production entries.

```text
Actual = H1 + H2 + H3 + H4 + H5 + H6 + H7 + H8
```

### Example

```text
20 + 24 + 23 + 25 + 24 + 22 + 24 + 24 = 186 parts
```

The user does not need to calculate the total manually.

---

## 📈 Efficiency Calculation

Machine efficiency is calculated automatically:

```text
Efficiency % = Actual Production ÷ Total Plan × 100
```

### Example

```text
Actual = 186
Plan = 192

Efficiency = 186 ÷ 192 × 100
Efficiency ≈ 97%
```

---

# 🚦 Machine Status Logic

Each machine receives a visual status based on its production efficiency.

### 🟢 On Target

The machine reaches or exceeds **100%** of the production plan.

```text
Efficiency ≥ 100%
```

### 🟡 Near Target

The machine is close to the expected production target.

```text
Efficiency ≥ 85% and < 100%
```

### 🔴 Off Target

The machine is below the acceptable production level.

```text
Efficiency < 85%
```

This allows supervisors to quickly find machines that need attention.

---

# 🏷️ Downtime Reason Tags

Instead of entering free-text comments, the application allows the user to select predefined production and downtime reasons.

Available tags include:

🔧 **Tool Change**

⚠️ **Alarm**

📦 **No Parts**

🔄 **Change Project**

### How it works

1. Click the **Tap to tag** button on a machine row.
2. Select one or more downtime reasons.
3. Save the selection.
4. The selected tags appear directly inside the machine row.

Multiple tags can be assigned to the same machine when more than one reason affected production.

This creates more consistent production data and makes downtime reasons easier to analyze.

---

# ☁️ Automatic Save

The application includes an automatic saving system.

When production information is changed:

1. The application detects the change.
2. It waits briefly to avoid unnecessary database requests.
3. The updated machine data is sent to Firebase.
4. Other connected dashboards receive the updated information.

This reduces the risk of losing data and removes the need to manually save after every hourly entry.

---

# 🔥 Firebase Real-Time Database

The application uses Firebase for storing and synchronizing production data.

### How it works

```text
Operator enters production data
            ↓
Application updates machine information
            ↓
Data is saved to Firebase
            ↓
Manager Dashboard receives the update
            ↓
Charts and machine status refresh automatically
```

Because the database is real-time, production entered on one device can be viewed from another device without manually refreshing the page.

---

# 📊 Manager Dashboard

The Manager Dashboard provides a live overview of the production line.

It is designed for supervisors, managers, and production leaders who need to quickly understand the current line performance.

## Dashboard Functions

### 🕒 Live Clock

The dashboard displays a live clock that updates every second.

This helps users understand the current production time while monitoring the line.

---

### 📈 Overall Efficiency / OEE

The dashboard calculates a headline performance value for the production line.

This provides a quick answer to:

> Is the production line currently achieving its expected output?

---

### 🏭 Machine Status Grid

All machines are displayed in a visual grid.

Each machine can be quickly identified as:

- 🟢 On Target
- 🟡 Near Target
- 🔴 Off Target

This is useful for finding production problems immediately.

---

### 📊 Actual vs Target Chart

The dashboard compares the actual production of every machine against its planned target.

This makes it easy to identify:

- Machines exceeding the target
- Machines close to the target
- Machines producing significantly below the target

---

### 📉 Efficiency by Machine

A dedicated chart shows the efficiency percentage of each machine.

This helps management compare machine performance across the entire production line.

---

### 📈 Cumulative Production Trend

The cumulative trend chart shows how production develops throughout the shift.

This helps answer questions such as:

- Is the line recovering after a slow start?
- Did production decrease during a specific period?
- Is the production gap becoming larger?

---

### 🏆 Top 5 Machines

The dashboard ranks the top five machines based on production output.

This provides quick visibility into the best-performing machines during the selected production period.

---

# 📱 Responsive Design

The application is designed to work on multiple screen sizes:

- 📱 Mobile phones
- 📲 Tablets
- 💻 Laptops
- 🖥️ Desktop computers

The responsive layout allows production data to be entered directly from the shop floor while managers can use larger displays for monitoring.

---

# 🗂️ Project Structure

```text
hourly-main/
│
├── index.html              # Main operator production entry page
├── app.js                  # Production logic and calculations
├── style.css               # Main application styling
│
├── dashboard.html          # Manager Dashboard page
├── dashboard.js            # Dashboard logic and charts
├── dashboard.css           # Dashboard styling
├── manager-dashboard.css   # Additional manager dashboard styling
│
├── firebase-init.js        # Firebase initialization
├── firebase-readonly.js    # Firebase read-only / synchronization logic
│
├── assets/
│   └── logo.jpeg           # Application/company logo
│
└── README.md               # Project documentation
```

---

# 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| **HTML5** | Application structure |
| **CSS3** | Responsive industrial interface design |
| **JavaScript** | Application logic and calculations |
| **Firebase** | Real-time data storage and synchronization |
| **Chart.js** | Production charts and visualizations |
| **Google Fonts** | Typography and dashboard styling |

The application is built primarily with **Vanilla JavaScript**, keeping the project lightweight and easy to maintain.

---

# ▶️ How to Run the Project

## Option 1 — Open Locally

Download or clone the project and open it using a local web server.

For example, with VS Code:

1. Open the project folder.
2. Install the **Live Server** extension.
3. Right-click `index.html`.
4. Select **Open with Live Server**.

> Firebase functionality requires the Firebase configuration to be correctly configured.

---

## Option 2 — Deploy Online

The project can be deployed to a static hosting service such as:

- GitHub Pages
- Netlify
- Firebase Hosting

Once deployed, operators and managers can access the application from any supported web browser.

---

# 🔐 Recommended Future Improvements

The project can be extended with additional features such as:

- 👤 User authentication and role-based access
- 🔒 Separate permissions for operators and managers
- 📅 Historical daily, weekly, and monthly reports
- 📥 Excel and PDF export
- 📊 Shift comparison dashboard
- ⚙️ Machine configuration page
- 🔔 Automatic alerts when machines fall below target
- ⏰ Downtime duration tracking
- 🧮 Detailed OEE calculation
- 📱 Improved PWA installation support
- 🌍 Multi-language support

---

# 🎯 Benefits

### ⚡ Faster Reaction Time
Production issues can be identified during the shift instead of waiting for an end-of-shift report.

### 📝 Less Paperwork
Manual production sheets can be replaced with digital records.

### 👁️ Real-Time Visibility
Managers can monitor production without physically visiting every machine.

### 📊 Better Decision Making
Production decisions can be based on live data, targets, and performance trends.

### ☁️ Shared Information
Operators and managers use the same synchronized source of production information.

---

# 👨‍💻 Developed By

**Omar Ben Haddouch**

Developed for the **Machining / SW CNC Production Line Department** at **CITIC Dicastal**.

---

⭐ If you find this project useful, feel free to improve it, add new production features, and adapt it to other manufacturing lines.
