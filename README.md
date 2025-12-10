# CYBER NINJA 🥷

**Your Digital Security Sentinel**

A comprehensive web security analysis tool designed to provide rapid and objective assessment of website security posture. CYBER NINJA scans URLs to identify potential risks, vulnerabilities, and misconfigurations, helping users stay ahead of digital threats.

![CYBER NINJA Banner](./CyberLogo.jpg)

---

## 📋 Table of Contents

- [Overview](#-Overview)
- [Why CYBER NINJA?](#why-cyber-ninja)
- [Target Audience](#target-audience)
- [Features](#features)
- [Security Checks](#security-checks)
- [Scoring System](#scoring-system)
- [Technical Stack](#technical-stack)
- [Installation & Setup](#installation--setup)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Limitations](#limitations)
- [Future Improvements](#future-improvements)
- [License](#license)

---

## 🎯Overview

CYBER NINJA is a web-based security scanner that analyzes websites for common security vulnerabilities and misconfigurations. It performs 15+ automated security checks and provides a comprehensive security score (0-100) based on industry best practices and OWASP guidelines.

The tool is designed to be:

- **Fast**: Scans complete in 5-10 seconds
- **Comprehensive**: Covers major security headers, cookies, content analysis, and server information
- **User-Friendly**: Clean interface with color-coded results
- **Educational**: Helps users understand web security concepts

---

## 🤔 Why CYBER NINJA?

This project was built to:

1. **Deepen Web Security Knowledge**: Understand real-world security vulnerabilities and how to detect them
2. **Identify Vulnerabilities**: Provide a practical tool to discover common security misconfigurations
3. **Educational Purpose**: Learn about OWASP Top 10 and security best practices through hands-on implementation
4. **Security Awareness**: Help developers and website owners understand their security posture

Web security is critical in today's digital landscape. Many websites lack basic security measures, making them vulnerable to attacks like:

- Clickjacking
- Cross-Site Scripting (XSS)
- Man-in-the-Middle (MITM) attacks
- Information disclosure
- CSRF attacks

CYBER NINJA makes it easy to identify these issues in seconds.

---

## 👥 Target Audience

CYBER NINJA is designed for:

- **Web Developers**: Who want to verify security configurations before deployment
- **Security Enthusiasts**: Learning about web security and vulnerability assessment
- **Website Owners**: Who need a quick security health check
- **Students**: Studying cybersecurity and web application security
- **Penetration Testers**: Looking for a quick reconnaissance tool

---

## ✨ Features

### Core Functionality

- ✅ **Real-time Security Scanning**: Analyze any publicly accessible website
- ✅ **15+ Security Checks**: Comprehensive coverage of common vulnerabilities
- ✅ **Security Score (0-100)**: Objective rating based on findings
- ✅ **Color-Coded Results**:
  - 🟢 Green (80-100): Excellent security
  - 🟡 Yellow (60-79): Moderate security
  - 🔴 Red (0-59): Poor security
- ✅ **Detailed Reports**: Breakdown of issues, warnings, and recommendations
- ✅ **Responsive Design**: Works on desktop, tablet, and mobile devices

### Advanced Analysis

- 🔍 Security Headers Analysis
- 🍪 Cookie Security Assessment
- 📄 HTML Content Inspection
- 🖥️ Server Information Detection
- ⚠️ Mixed Content Detection
- 🛡️ CSRF Protection Check

---

## 🔐 Security Checks

CYBER NINJA performs the following security checks:

### 1. **HTTPS Detection**

- Verifies if the website uses encrypted HTTPS connection
- Critical for protecting data in transit

### 2. **Security Headers**

| Header                               | Purpose                       | Risk if Missing |
| ------------------------------------ | ----------------------------- | --------------- |
| **Content-Security-Policy (CSP)**    | Prevents XSS attacks          | High            |
| **Strict-Transport-Security (HSTS)** | Forces HTTPS connections      | High            |
| **X-Frame-Options**                  | Prevents clickjacking         | Medium          |
| **X-Content-Type-Options**           | Prevents MIME sniffing        | Medium          |
| **Referrer-Policy**                  | Controls referrer information | Low             |
| **Permissions-Policy**               | Controls browser features     | Low             |

### 3. **Cookie Security**

- **Secure Flag**: Ensures cookies only sent over HTTPS
- **HttpOnly Flag**: Prevents JavaScript access to cookies
- **SameSite Attribute**: Protects against CSRF attacks

### 4. **Content Analysis**

- **Inline Scripts**: Counts potentially dangerous inline JavaScript
- **External Scripts**: Tracks third-party script dependencies
- **Forms Detection**: Identifies forms that may need CSRF protection
- **Mixed Content**: Detects HTTP resources loaded on HTTPS pages

### 5. **Server Information Leakage**

- **Server Header**: Checks if server software version is exposed
- **X-Powered-By**: Detects technology stack disclosure

### 6. **CSRF Protection**

- Scans forms for CSRF tokens
- Identifies forms without protection

---

## 📊 Scoring System

The security score is calculated using the following formula:

```javascript
Score = 100 - (Critical Issues × 15) - (Warnings × 5)
```

### Score Categories:

| Score Range | Rating       | Description                                 |
| ----------- | ------------ | ------------------------------------------- |
| **80-100**  | 🟢 Excellent | Strong security posture                     |
| **60-79**   | 🟡 Good      | Moderate security, some improvements needed |
| **40-59**   | 🟠 Fair      | Significant security gaps                   |
| **0-39**    | 🔴 Poor      | Critical security issues present            |

### Issue Types:

**Critical Issues** (-15 points each):

- Missing Content-Security-Policy
- Missing HSTS header (on HTTPS sites)
- Missing X-Frame-Options (Clickjacking risk)
- Missing X-Content-Type-Options
- Forms without CSRF protection

**Warnings** (-5 points each):

- Mixed content detected
- Inline scripts present
- Server header exposed
- X-Powered-By header exposed
- Cookies without Secure flag
- Cookies without HttpOnly flag
- Missing Referrer-Policy

### Example Calculation:

```
Website: example.com
- 2 Critical Issues (Missing CSP, Missing HSTS)
- 3 Warnings (Server exposed, No HttpOnly, Mixed content)

Score = 100 - (2 × 15) - (3 × 5)
      = 100 - 30 - 15
      = 55/100 (Fair Security)
```

---

## 🛠️ Technical Stack

### Frontend

- **React 19**: UI framework
- **Vite**: Build tool and dev server
- **Tailwind CSS**: Styling framework
- **JavaScript (ES6+)**: Programming language

### Backend

- **Node.js**: Runtime environment
- **Express.js**: Web framework
- **node-fetch**: HTTP client
- **Cheerio**: HTML parsing and analysis
- **CORS**: Cross-origin resource sharing

### Architecture

```
┌─────────────┐         ┌─────────────┐         ┌─────────────┐
│   Browser   │ ───────▶│   Express   │ ───────▶│   Target    │
│  (React UI) │  POST   │   Server    │  GET    │   Website   │
└─────────────┘         └─────────────┘         └─────────────┘
       │                       │
       │                       ▼
       │                 ┌──────────┐
       └────────────────▶│ Cheerio  │
            Response     │  Parser  │
                        └──────────┘
```

---


### Step 4: Access the Application

Open your browser and navigate to `[momenashraf5.github.io/Cyber-Ninja/](https://momenashraf5.github.io/Cyber-Ninja/)`

---

## 🚀 Usage

1. **Enter URL**: Type the full URL of the website you want to scan (e.g., `https://example.com`)
2. **Click Scan**: Press the "Scan" button to start the analysis
3. **Wait for Results**: Scanning typically takes 5-10 seconds
4. **Review Report**: Examine the security score, issues, warnings, and detailed findings

### Example Scan:

**Input:**

```
https://github.com
```

**Output:**

- Security Score: 85/100 (Excellent)
- HTTPS: ✓ Enabled
- Status: 200
- Issues: 0 Critical
- Warnings: 2 (Server header exposed, Inline scripts)

---

## ⚠️ Limitations

CYBER NINJA has the following limitations:

1. **Surface-Level Analysis**: Only checks publicly visible headers and HTML content
2. **No Authentication Testing**: Cannot test login systems or authenticated areas
3. **No Active Exploitation**: Does not attempt to exploit vulnerabilities
4. **Public Websites Only**: Cannot scan websites behind firewalls or authentication
5. **No Database Testing**: Cannot detect SQL injection or database vulnerabilities
6. **No JavaScript Execution**: Cannot analyze client-side security in SPAs
7. **Rate Limiting**: May be blocked by websites with strict rate limiting
8. **SSL/TLS Analysis**: Does not perform deep certificate or cipher analysis

### What CYBER NINJA Cannot Detect:

- ❌ SQL Injection vulnerabilities
- ❌ Authentication bypass issues
- ❌ Business logic flaws
- ❌ API security issues
- ❌ Server-side vulnerabilities (RCE, LFI, etc.)
- ❌ Advanced XSS attacks
- ❌ Real-time malware detection

---

## 🚧 Future Improvements

### Phase 1 (Short-term)

- [ ] Add SSL/TLS certificate analysis
- [ ] Implement scan history with local storage
- [ ] Export results to PDF
- [ ] Add more OWASP Top 10 checks
- [ ] Implement robots.txt and sitemap analysis

### Phase 2 (Medium-term)

- [ ] Database integration for storing scan results
- [ ] User accounts and authentication
- [ ] Scheduled automated scans
- [ ] Email notifications for security issues
- [ ] Comparison feature (before/after scans)

### Phase 3 (Long-term)

- [ ] Machine learning for anomaly detection
- [ ] Integration with threat intelligence feeds
- [ ] API for third-party integrations
- [ ] Mobile application
- [ ] Multi-language support

---

## 📚 References & Resources

- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- [OWASP Secure Headers Project](https://owasp.org/www-project-secure-headers/)
- [MDN Web Security](https://developer.mozilla.org/en-US/docs/Web/Security)
- [Content Security Policy Reference](https://content-security-policy.com/)

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 👨‍💻 Author

**[Moamen Ashraf]**

- GitHub: [MomenAshraf5](https://github.com/MomenAshraf5)
- Email: moamenashraf533@gmail.com
- LinkedIn: [MoamenAshraf](https://linkedin.com/in/momen-ashraf)

---

## 🙏 Acknowledgments

- OWASP Foundation for security guidelines
- React and Node.js communities
- All open-source contributors

---

**⚡ Built with passion for web security**

_Note: This tool is for educational and security assessment purposes only. Always obtain proper authorization before scanning websites you do not own._


