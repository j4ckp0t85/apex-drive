# 🛡️ Privacy Policy

**Last Updated:** October 2026
**Project:** APEX DRIVE (Android Companion Application)

APEX DRIVE is built with a fundamental commitment to user privacy, data sovereignty, and security. We believe that your riding data belongs exclusively to you.

---

## 1. Zero Data Collection Policy (100% Offline)

* **No Remote Telemetry**: APEX DRIVE does **not** collect, track, log, aggregate, or transmit any personal information, device identifiers, riding patterns, or usage statistics to any remote server or third party.
* **No Internet Access**: The application does **not** request or use the `android.permission.INTERNET` permission in its Android Manifest. It is technically impossible for the application to communicate over the internet or send data off your device.
* **No Third-Party Trackers**: The application contains **zero** third-party analytics SDKs, advertising frameworks, crash reporting tracking libraries, or profiling tools.

---

## 2. Local-Only Data Storage

All data created or processed by APEX DRIVE remains strictly on your local device storage:

* **Ride Telemetry Logs (CSV Files)**: If ride recording is enabled, telemetry data (such as speed, cadence, motor wattage, rider power, battery status, sensor readings, and available phone GPS latitude/longitude) is streamed to a local `.csv` file. Missing GPS coordinates are recorded as `null`. Session files are also published to `Download/ApexDrive/Telemetry/` for user access and USB copying; exported or copied files include recorded coordinates.
* **Configuration Profiles (`.ini`) & App Settings**: Motor configuration files and custom preferences are stored locally in the application's private sandboxed storage (`SharedPreferences`).
* **Optional USB configuration inbox**: If you enable USB import, APEX DRIVE reads INI payloads and transfer manifests from the specific `Download/ApexDrive/Imports` folder you authorize through Android's system folder picker, and writes import-result acknowledgements there for the Windows companion. These shared files remain visible to you and a connected computer until you delete them. The applied profile and duplicate-prevention receipts remain in private preferences. No configuration or acknowledgement is uploaded. Only enable this for a trusted computer; disabling USB import releases the folder permission but does not delete shared files.
* **Data Ownership & Deletion**: You retain complete ownership over all generated data. You may inspect, export, backup, or permanently delete your ride logs and settings at any time by clearing app data or deleting the exported CSV files.

---

## 3. Permissions Explanation & Device Access

APEX DRIVE requests only the minimum permissions necessary to interact with your e-bike hardware via Bluetooth Low Energy (BLE) and provide live dashboard functionality:

| Permission | Purpose & Usage |
| :--- | :--- |
| **`BLUETOOTH_SCAN`** & **`BLUETOOTH_CONNECT`** | Required on Android 12+ to discover and establish a direct BLE communication link with your Varstrom EKD01 / TSDZ2 display. |
| **`ACCESS_FINE_LOCATION`** / **`ACCESS_COARSE_LOCATION`** | Used for BLE discovery where required by Android, GPS-assisted slope cross-validation, and GPS coordinates in local ride telemetry CSVs. **Coordinates are stored locally when ride recording is enabled and a recent GPS fix is available. They are included in user exports and USB copies; the app does not transmit them to a remote server.** |
| **`FOREGROUND_SERVICE`** & **`POST_NOTIFICATIONS`** | Required to display a persistent notification with live ride status (speed, assist mode, gradient) and prevent Android from terminating the BLE connection when the screen is turned off. |
| **`WAKE_LOCK`** & **`REQUEST_IGNORE_BATTERY_OPTIMIZATIONS`** | Ensures uninterrupted communication with the motor display and continuous Auto-Pilot operation while riding. |

USB configuration import uses a user-selected, persistable Storage Access Framework folder grant rather than an all-files storage permission. It runs while APEX DRIVE is visible, processes queued transfers on next resume, and does not introduce network or USB-debugging permissions.

---

## 4. Regulatory Compliance

### General Data Protection Regulation (GDPR - EU 2016/679)
Under the GDPR, APEX DRIVE qualifies as software practicing **Data Protection by Design and by Default** (Article 25). Because no personal data is collected, stored remotely, or processed by the developers, no data processing agreement or consent management platform is required.

### California Consumer Privacy Act (CCPA / CPRA)
APEX DRIVE does not collect, sell, share, or retain personal consumer information as defined under the California Consumer Privacy Act.

---

## 5. Contact & Support

For questions regarding this Privacy Policy, please open an issue in the official project repository or contact the author.
