# 📊 PulseCheck Dashboard

A beautiful, real-time uptime monitoring dashboard for tracking website availability, response times, and performance history. This frontend connects to the public PulseCheck API.

**Live Demo:** [https://pulse-checker-eta.vercel.app/](https://pulse-checker-eta.vercel.app/)

---

## ✨ Features

- **📈 Real-time Monitoring** - Track uptime and response times for all your websites.
- **🟢 Status Indicators** - Visual status badges (Online/Offline/Pending).
- **⚡ Instant Checks** - Manually trigger checks or rely on automated cron jobs.
- **📊 History Tracking** - View detailed check history for each monitor.
- **🔐 Secure Token Storage** - Tokens stored in browser localStorage.
- **🎨 Dark Theme** - Modern dark interface optimized for monitoring.
- **📱 Responsive Design** - Works on desktop, tablet, and mobile devices.

---

## 🚀 Quick Deploy

### Deploy to Vercel (Recommended)

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/logicnestxvoidlure/pulse-checker)

Or deploy manually:

```bash
git clone https://github.com/logicnestxvoidlure/pulse-checker
cd pulse-checker/frontend
vercel --prod
```

### Manual Deployment

Upload these three files to any static hosting service:

```text
index.html    # Main dashboard
styles.css    # Dark theme styles
app.js        # Full JavaScript application
```

---

## 🔧 Configuration

### Default API

The dashboard uses the following backend API:

```text
https://pulse-checkerapi.onrender.com
```

### Using Your Own API

To connect a different API backend:

1. Open `app.js`.
2. Find the API configuration:

   ```javascript
   const API = "https://pulse-checkerapi.onrender.com";
   ```

3. Replace the URL with your own backend API URL.

### Using the Vercel Proxy (Optional)

If you use the Vercel proxy to avoid CORS issues:

1. Open `api/proxy.js`.
2. Set the backend URL:

   ```javascript
   const API_URL = "https://pulse-checkerapi.onrender.com";
   ```

3. Ensure the proxy forwards requests to the correct backend endpoints.

---

## 📁 Project Structure

```text
frontend/
├── index.html          # Main HTML page
├── styles.css          # Dark theme styles
├── app.js              # Full JavaScript application
└── api/
    └── proxy.js        # Optional Vercel API proxy
```

---

## 🛠️ Technologies Used

- **HTML5** - Semantic markup
- **CSS3** - Dark theme with CSS variables
- **JavaScript (ES6+)** - Vanilla JavaScript, no dependencies
- **Vercel** - Frontend deployment and optional proxy
- **LocalStorage** - Browser-side token storage

---

## 🔐 Security

- **Tokens:** Stored in browser localStorage.
- **API Keys:** Keep private API credentials on the server; never embed secrets in client-side code.
- **CORS:** The backend must allow requests from the frontend's origin.
- **CSRF:** Use appropriate token validation for write operations.

---

## 📡 API Endpoints

| Endpoint | Method | Description |
|---|---|---|
| `/api/monitors.php` | GET | List all monitors |
| `/api/monitors.php` | POST | Create a new monitor |
| `/api/monitors.php` | DELETE | Delete a monitor |
| `/api/check.php` | POST | Check a monitor |
| `/api/history.php` | GET | Retrieve check history |

Write operations require the `X-PulseCheck-Token` header.

*Note: These endpoint paths and authentication requirements are based on the existing project documentation. Verify them against the current backend implementation.*

---

## 🎨 Dashboard Preview

```text
┌──────────────────────────────────────────────────────────┐
│ ● PulseCheck                         API Status           │
│                                                          │
│ UPTIME MONITORING                                        │
│ Know when your site goes down.                           │
│                                                          │
│ ┌──────────────────────────────────────────────────────┐ │
│ │ New monitor                                           │ │
│ │ Website URL                                           │ │
│ │ [https://example.com]                                 │ │
│ │ [Add monitor →]                                       │ │
│ └──────────────────────────────────────────────────────┘ │
│                                                          │
│ ┌────────────┐ ┌────────────┐ ┌────────────┐ ┌─────────┐ │
│ │ Total      │ │ Online     │ │ Offline    │ │ Avg.    │ │
│ │ Monitors   │ │ Monitors   │ │ Monitors   │ │ Response│ │
│ └────────────┘ └────────────┘ └────────────┘ └─────────┘ │
│                                                          │
│ YOUR MONITORS                                [Refresh]   │
│                                                          │
│ ● google.com                Online          45 ms        │
│   [History] [Check] [Delete]                             │
│                                                          │
│ ● example.com               Offline         —            │
│   [History] [Check] [Delete]                             │
└──────────────────────────────────────────────────────────┘
```

---

## 🔧 Troubleshooting

### CORS Errors

If the frontend cannot communicate with your API, configure the backend to allow requests from your deployed frontend.

For a PHP backend, an example configuration is:

```php
header('Access-Control-Allow-Origin: https://pulse-checker-eta.vercel.app');
header('Access-Control-Allow-Methods: GET, POST, DELETE, OPTIONS');
header('Access-Control-Allow-Headers: Content-Type, X-PulseCheck-Token');
```

Handle `OPTIONS` preflight requests where required. Avoid allowing every origin in production unless it is appropriate for your security model.

### API Unavailable

- Verify the API URL in `app.js` or `api/proxy.js`.
- Check whether the backend is running.
- Open the API base URL to check its response.
- Check backend logs for errors.

### Monitors Always Show "Pending"

- Verify that the backend's scheduled checks or cron job are running.
- Manually trigger a check.
- Check backend logs and the API response for errors.

---

## 🔗 Links

- **Live Demo:** https://pulse-checker-eta.vercel.app/
- **Backend API:** https://pulse-checkerapi.onrender.com
- **Repository:** https://github.com/logicnestxvoidlure/pulse-checker
- **API Documentation:** https://pulse-checker-eta.vercel.app/apidocs.html

---

## 📝 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## 🙏 Credits

- **PulseCheck API** - Backend monitoring service by [logicnestxvoidlure](https://github.com/logicnestxvoidlure).
- **Vercel** - Frontend hosting platform.
- **Render** - Backend hosting platform.

---

*Built for reliable uptime monitoring.*

**Star ⭐ the repository if you find it useful!**
