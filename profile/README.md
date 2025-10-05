# Netaudit: Network Audit Automation Tool

<p align="center">
  <img src="https://wwwin-github.cisco.com/raw/Netaudit/.github/master/profile/netaudit.png" alt="Netaudit Banner" />
</p>


Netaudit is a powerful Flask-based web application designed to streamline and automate network audit tasks, particularly crucial during network migrations and routine compliance checks. It helps network engineers and administrators validate configurations, check device states, and ensure network health with ease and efficiency.

---

## Table of Contents
- [About Netaudit](#about-netaudit)
- [Features](#features)
- [Screenshots](#screenshots)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Contributing](#contributing)
- [License](#license)

---

## About Netaudit

In complex network environments, especially during migrations, validating device configurations and operational states is a painstaking process. Netaudit simplifies this by providing a platform to define custom checks, run audits on demand or periodically, and visualize results. From simple image version checks to complex routing protocol state validations (like BGP or OSPF), Netaudit ensures that your network devices are compliant and functioning as expected.

The application offers two primary modes: a comprehensive **Dashboard** for ongoing monitoring and historical data, and a **Run Now** feature for immediate, post-migration validations.

---

## Features

Netaudit comes packed with features to facilitate robust network auditing:

### Core Functionality
- **Flexible Check Definitions:** Define custom audit checks using Python scripts.
- **LLM Integration for Check Generation:** Leverage Large Language Models to assist in generating new audit checks, speeding up development.
- **Device Management:** Add, edit, and manage network devices for auditing.
- **View Management:** Group multiple checks into logical "views" for easier organization and auditing.
- **Credential Management:** Securely store and manage credentials for accessing network devices.

### Dashboard Mode
- **Overview Summary:** Get a quick glance at the overall audit status of your network with charts and summary statistics.
- **Periodic Audits:** Designed for continuous monitoring, storing historical audit results.
- **Detailed Audit Results:** View pass/fail status for each check on individual devices or across entire views.
- **Action Tracking:** Mark actions taken on audit findings and add comments for compliance and follow-up.

### Run Now Mode
- **On-Demand Audits:** Perform quick, ad-hoc audits for specific devices and checks, ideal for post-migration validation.
- **Immediate Results:** View audit results instantly in a tabular format.
- **Export Capabilities:** Export audit reports to Excel for further analysis or record-keeping.

### Admin Panel
- **User Management:** Control user access and roles.
- **Comprehensive Management:** Centralized management for Devices, Views, Checks, Sessions (Credentials), and Users.

---

## Installation

To set up Netaudit locally, follow these steps:

1.  **Clone the repository:**
    ```bash
    git clone <repository_url>
    cd netaudit
    ```

2.  **Create a virtual environment and activate it:**
    ```bash
    python -m venv venv
    # On Linux/macOS
    source venv/bin/activate
    # On Windows
    venv\Scripts\activate
    ```

3.  **Install the required dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

4.  **Run the application:**
    Netaudit is a Flask application. You can run it using the Flask development server or a production-ready WSGI server like Gunicorn.

    **Using Flask Development Server (for development):**
    ```bash
    export FLASK_APP=wsgi.py # Or set FLASK_APP=wsgi.py in Windows CMD/PowerShell
    flask run
    ```
    The application will typically be available at `http://127.0.0.1:5000/`.

    **Using Gunicorn (for production):**
    ```bash
    gunicorn wsgi:app
    ```

---

## Usage

Netaudit is designed with a clear separation of concerns to manage network audits effectively.

### Dashboard
Upon logging in, the Dashboard provides an immediate overview of your network's audit posture. It displays charts summarizing device compliance (pass/fail), actions taken, and a timeline of device deployments. This is ideal for long-term monitoring and understanding trends. You can navigate to `Results` from the sidebar to view detailed historical audit data for devices and views, and utilize the "Follow Up" feature to log actions and comments on audit findings.

### Run Now
For immediate validation, such as after a network change or migration, use the "Run Now" feature.
1.  Navigate to `Run Now` in the sidebar.
2.  Enter the hostnames or IP addresses of the devices you wish to audit.
3.  Select the specific audit checks you want to run.
4.  Provide the necessary jump host and network credentials.
5.  Click "Run" to execute the audit and view instant results, or "View Report" to generate an exportable report. The results are displayed in a tabular format, and you have the option to export them to an Excel file.

### Manage (Admin Only)
The `Manage` section is accessible only to administrators and provides comprehensive control over the application's core components:
-   **Devices:** Add, modify, or remove network devices from the audit scope.
-   **Views:** Create and organize groups of checks. For example, a "LAN" view might include checks for BGP Neighbor Status and CoPP Profile Configuration.
-   **Checks:** Define and manage individual audit checks. This is where you can also use the LLM integration to generate new checks by describing your requirements.
-   **Sessions:** Manage the credentials used to access network devices (e.g., SSH credentials).
-   **Users:** Administer user accounts and permissions.

---

## Contributing

Contributions are welcome! Please feel free to fork the repository, make changes, and submit pull requests. For major changes, please open an issue first to discuss what you would like to change.

**Maintainer:** Sanjeev Krishna  
[sanjeekr@cisco.com](mailto:sanjeekr@cisco.com)

---

## License

This project is licensed under the **MIT License**.  
© 2024 Sanjeev Krishna. All rights reserved.

---