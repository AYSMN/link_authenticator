# 🛡️ Link Forensics & Threat Intelligence

Detect phishing, malware, and scam links before you click. This browser extension provides real-time URL scanning and threat intelligence to keep your browsing safe.

## ✨ Features

- **Real-time Scanning**: Scan any URL manually via the extension popup.
- **Context Menu Integration**: Right-click any link on a web page to "Scan this link for threats".
- **Advanced Intel**: View destination URLs, server locations, domain age, and vendor scan ratios.
- **Threat Verdicts**: Clear "SECURE" or "THREAT DETECTED" indicators based on VirusTotal intelligence.
- **URL Unrolling**: Automatically follows redirects to find the final destination of a shortened link.

## 🚀 Getting Started

### 1. Prerequisites
- **Google Chrome** (or any Chromium-based browser).

### 2. Backend Setup
The backend handles the actual scanning logic and communicates with Threat Intelligence APIs.

### 3. Extension Installation
1. Open Chrome and go to `chrome://extensions/`.
2. Enable **Developer mode** (top right toggle).
3. Click **Load unpacked**.
4. Select the `extension` folder from this repository.

## 🛠️ Architecture

The project is split into two main components:

- **Frontend (Extension)**:
  - `popup.html/js`: The user interface for manual scans.
  - `background.js`: A service worker that handles network requests and context menu actions.
  - `manifest.json`: Configuration and permissions (V3).
- **Backend (Server)**:
  - `app.py`: A Flask server that performs URL unrolling and queries VirusTotal.
  - `requirements.txt`: Python dependencies.

## 🔒 Permissions Used
- `contextMenus`: To add the right-click scan option.
- `activeTab`: To access the link URL from the current page.
- `scripting`: To show alert notifications on the web page.
- `host_permissions`: Specifically `http://127.0.0.1:5000/*` to communicate with your local backend.

## 📄 License
This project is open-source and available under the MIT License.
