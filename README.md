# AI-SOC — Security Operations Center

## Overview

AI-SOC is an authentication security monitoring platform designed to detect suspicious login activity, assess potential threats, and provide real-time visibility into security events. It combines login monitoring, risk scoring, IP tracking, incident visualization, and administrative controls in a centralized dashboard.

The project demonstrates a software-based approach to security operations, helping administrators monitor access attempts, investigate suspicious behavior, and manage potential threats.

## Key Features

- **Login Monitoring:** Tracks successful and failed authentication attempts.
- **Risk-Based Threat Detection:** Evaluates suspicious login patterns and assigns risk scores.
- **Brute-Force Detection:** Identifies repeated failed login attempts and potentially malicious access patterns.
- **Real-Time Threat Dashboard:** Displays security statistics, incident activity, and threat information.
- **IP Monitoring:** Tracks IP addresses associated with login activity and potential threats.
- **Geolocation Visualization:** Displays available IP-based location information.
- **Blocked IP Management:** Provides controls to review blocked IP addresses and unblock them.
- **Incident Timeline:** Supports reviewing and replaying security event activity.
- **User Management:** Allows administrators to manage registered users.
- **Device Tracking:** Supports associating a primary device with a user account.
- **Email Alerts:** Supports email notifications when the required email configuration is provided.
- **Vulnerability Scanning Interface:** Includes a scanner interface for security-related checks.

## Technology Stack

### Frontend
- HTML5
- CSS3
- JavaScript

### Backend
- Node.js
- Express.js
- Socket.IO
- Axios
- Nodemailer
- CORS

### Security Monitoring
- Authentication event analysis
- Risk-score-based detection
- Suspicious login pattern monitoring
- IP-based tracking
- Automated blocking and alerting logic

## Project Structure

```text
ai-soc_NEW/
├── client/
│   ├── index.html
│   ├── admin.html
│   └── script.js
├── server/
│   ├── package.json
│   ├── package-lock.json
│   └── server.js
├── trail.c
└── README.md
```

The `client` directory contains the login interface, administrative dashboard, and frontend logic.

The `server` directory contains the Node.js backend, API endpoints, authentication handling, threat monitoring logic, and real-time communication services.

The C files and executable files included in the original archive are auxiliary files and are not part of the main Node.js application startup process.

## Installation and Setup

### Prerequisites

Install the following before running the application:

- Node.js
- npm
- A modern web browser

### Step 1: Clone the Repository

```bash
git clone <your-repository-url>
cd ai-soc_NEW
```

Replace `<your-repository-url>` with your actual GitHub repository URL.

### Step 2: Install Dependencies

Navigate to the server directory:

```bash
cd server
npm install
```

### Step 3: Start the Backend

Run the following command:

```bash
npm start
```

For development mode, use:

```bash
npm run dev
```

The backend uses port `5000` by default.

### Step 4: Open the Frontend

Open `client/index.html` in your browser to access the login interface.

Open `client/admin.html` to access the administrative dashboard.

Ensure the backend is running before using features that require API communication.

## Environment Configuration

The backend supports environment variables for configuration.

| Variable | Purpose |
|---|---|
| `PORT` | Backend port; defaults to `5000` |
| `CLIENT_ORIGIN` | Allowed frontend origin for CORS |
| `ALERT_EMAIL_USER` | Email account used for notifications |
| `ALERT_EMAIL_PASS` | Email application password |
| `ALERT_EMAIL_TO` | Destination for email alerts |
| `ALERT_SCORE` | Risk-score threshold for alerts |
| `BLOCK_SCORE` | Risk-score threshold for blocking |
| `ALERT_COOLDOWN_MS` | Minimum interval between alerts |
| `MAX_LOGS` | Maximum retained log count |

Configure environment variables according to your deployment requirements. Do not commit credentials or application passwords to GitHub.

## API Endpoints

The backend exposes the following API routes:

| Method | Endpoint | Purpose |
|---|---|---|
| GET | `/health` | Check backend health |
| GET | `/stats` | Retrieve security statistics |
| GET | `/blocked-ips` | Retrieve blocked IP information |
| POST | `/blocked-ips/:ip/unblock` | Unblock an IP address |
| POST | `/login` | Process a login attempt |
| GET | `/logs` | Retrieve security logs |
| GET | `/timeline` | Retrieve incident timeline information |
| GET | `/simulate` | Access the simulation endpoint |
| POST | `/scan` | Trigger the scanning endpoint |
| GET | `/users` | Retrieve user information |
| POST | `/users` | Create a user |
| DELETE | `/users/:username` | Delete a user |
| POST | `/users/:username/main-device` | Configure a user's primary device |

## How It Works

1. A user submits a login request through the frontend.
2. The backend processes the authentication request and records relevant security events.
3. Login patterns and access activity are evaluated using the configured risk-detection logic.
4. Suspicious activity can trigger alerts or IP-blocking actions according to the implemented rules.
5. Security events and statistics are made available to the administrative dashboard.
6. Administrators can review incident history, inspect blocked IPs, and manage users.
7. If email credentials are configured, supported alert events can generate email notifications.

## Security Considerations

AI-SOC is a project for learning, development, and security monitoring experimentation. Before using it in a production environment:

- Replace demonstration credentials with secure authentication.
- Hash passwords using a suitable password-hashing algorithm.
- Implement proper session management and authorization.
- Protect administrative endpoints against unauthorized access.
- Store security logs persistently and protect them from tampering.
- Validate and sanitize all incoming requests.
- Configure CORS for trusted origins only.
- Protect email credentials using environment variables or a secrets manager.
- Verify IP geolocation and threat intelligence results before taking enforcement actions.
- Test the detection rules against false positives and false negatives.

Risk scoring and suspicious-activity detection should not be considered proof of an attack. IP geolocation and VPN indicators can be inaccurate.

## Limitations

- Detection quality depends on the implemented rules and available event data.
- IP geolocation may be approximate or unavailable.
- Some monitoring features may require additional external services or configuration.
- The current implementation should undergo security testing before production deployment.

## Future Enhancements

- Integration with threat intelligence feeds.
- Machine-learning-based anomaly detection.
- Multi-factor authentication.
- Persistent database storage for users and security events.
- Advanced incident correlation and investigation.
- Role-based access control.
- Integration with SIEM platforms.
- Configurable alerting and automated incident response.

## Intended Use

AI-SOC is intended for educational purposes, cybersecurity experimentation, authentication monitoring, and demonstrating security operations workflows. Use it only on systems and networks you own or are authorized to test.

## License

Choose and add an appropriate open-source license before distributing this project.

## Author

Developed as a cybersecurity project exploring authentication monitoring, suspicious-activity detection, risk scoring, and security dashboard design.
