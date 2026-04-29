# VTU AutoComplete

Automate your VTU online course progress with VTU AutoComplete — a robust Node.js tool with a modern web UI and CLI. This project helps you mark lectures as complete, track progress, and save time.

---

## 🚀 Features
- **Automated Lecture Completion:** Mark lectures as complete with a single click or command.
- **Web UI & CLI:** Use a friendly browser interface or command line.
- **Real-Time Progress:** Live updates as lectures are processed.
- **Retry & Error Handling:** Smart retries for failed lectures.
- **Optional Redis Stats:** Track usage and analytics (optional).

---

## 🛠️ Setup

### Prerequisites
- [Git](https://git-scm.com/downloads)
- [Node.js 18+](https://nodejs.org/)

### Installation
1. **Clone the repository:**
   ```bash
   git clone https://github.com/pranavv1210/vtu-course-automation.git
   cd vtu-course-automation
   ```
2. **Install dependencies:**
   ```bash
   npm install
   ```
3. **Configure environment:**
   - Copy `.env.example` to `.env` and fill in your VTU credentials and course slug:
     ```env
     VTU_EMAIL=your-email@domain.com
     VTU_PASSWORD=yourpassword
     VTU_COURSE_SLUG=1-social-networks
     ```

---

## 🌐 Usage

### Web UI (Recommended)
1. Start the server:
   ```bash
   npm run serve
   ```
2. Open [http://localhost:3000](http://localhost:3000) in your browser.
3. Enter your credentials and course slug, then start automation.

### CLI
1. Ensure `.env` is configured with your credentials and course slug.
2. Run:
   ```bash
   npm start
   ```

### Dev Mode (Auto-reload)
```bash
npm run dev
```

---

## 🏗️ Project Structure
```
automation.js         # Core automation logic
server.js             # Express server and job queue
index.js              # CLI entry point
lib/redis.js          # Redis integration (optional)
frontend/index.html   # Web UI
public/index.html     # Static fallback
package.json          # Project metadata
stats.json            # Local stats cache
```

---

## ⚙️ Configuration

| Variable           | Description                        |
|--------------------|------------------------------------|
| VTU_EMAIL          | VTU account email (CLI only)        |
| VTU_PASSWORD       | VTU account password (CLI only)     |
| VTU_COURSE_SLUG    | Course slug (e.g. 1-social-networks)|
| VTU_BATCH_SIZE     | Lectures processed in parallel      |
| VTU_MAX_ATTEMPTS   | Max attempts per lecture            |
| PORT               | Server port (default: 3000)         |
| KV_REST_API_URL    | Upstash Redis URL (optional)        |
| KV_REST_API_TOKEN  | Upstash Redis token (optional)      |

---

## 🧹 Cleaning Up Unused Files
- Only the following files/folders are required for VTU AutoComplete to function:
  - automation.js
  - server.js
  - index.js
  - lib/redis.js
  - frontend/index.html
  - public/index.html
  - package.json
  - package-lock.json
  - .env / .env.example
  - stats.json (optional)
  - .gitignore
- Remove any other files not listed above unless you have custom scripts or data.

---

## 🩺 Troubleshooting
- **Login failed:** Check your VTU credentials.
- **Course not found:** Verify the course slug from the VTU URL.
- **Lectures stuck:** Try reducing `VTU_BATCH_SIZE` or increasing `VTU_MAX_ATTEMPTS`.
- **Port in use:** Change the `PORT` variable in `.env`.

---

## 🔒 Security
- Never commit your `.env` file (already in `.gitignore`).
- Credentials are only used in memory and never stored.

---

## 👨‍💻 Author
[Pranav](https://github.com/pranavv1210)

---

## 🤝 Contributing
PRs and issues are welcome!

---

## 📄 License
MIT © Pranav
