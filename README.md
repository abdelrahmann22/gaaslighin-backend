# Gaaslightin Backend

**Gaaslightin Backend** is a powerful Node.js application designed to supercharge developer careers by leveraging AI to analyze code, generate professional content, and streamline job applications. It integrates seamlessly with GitHub to provide deep insights into your codebases and helps you showcase your work effectively.

## 🚀 Features

- **GitHub Integration**: Securely connect with GitHub using OAuth to access and manage your repositories.
- **AI-Powered Code Analysis**:
  - Automatically scans your repositories to identify the most logic-heavy and complex files.
  - Calculates a **Complexity Score (5.5 - 10)** for your projects using advanced AI models (GPT-4o-mini).
- **Automated Content Generation**:
  - Turns your actual code into engaging **LinkedIn posts**.
  - Highlights key architectural decisions and problem-solving patterns in your code.
- **Job Market Intelligence**:
  - **Job Scraper**: Extracts job postings from various URLs.
  - **AI Parser**: Converts raw job descriptions into structured data (Title, Company, Skills, etc.) using AI.
- **Resume Management**: Upload, manage, and link your resumes to job applications.
- **User Authentication**: Secure session-based authentication with Passport.js.

## 🛠 Tech Stack

- **Runtime**: [Node.js](https://nodejs.org/) & [TypeScript](https://www.typescriptlang.org/)
- **Framework**: [Express.js](https://expressjs.com/)
- **Database**: [MongoDB](https://www.mongodb.com/) with [Mongoose](https://mongoosejs.com/)
- **AI & LLMs**: [OpenAI](https://openai.com/) (GPT-4o-mini), Mistral AI
- **Authentication**: [Passport.js](https://www.passportjs.org/) (GitHub Strategy)
- **Web Scraping**: [Cheerio](https://cheerio.js.org/) & Axios

## 📦 Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/gaaslighin-backend.git
   cd gaaslighin-backend
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Configure Environment Variables**
   Create a `.env` file in the root directory and add the following based on `.env.example`:
   ```env
   PORT=8080
   
   # GitHub OAuth
   GITHUB_CLIENT_ID=your_github_client_id
   GITHUB_CLIENT_SECRET=your_github_client_secret
   
   # JWT Secrets (if used alongside session)
   ACCESS_TOKEN_SECRET=your_access_token_secret
   REFRESH_TOKEN_SECRET=your_refresh_token_secret
   
   # Database
   DATA_BASE_URL=mongodb://localhost:27017/gaaslightin
   
   # Session
   SESSION_SECRET=your_session_secret
   
   # AI Keys
   OPENAI_API_KEY=your_openai_api_key
   
   # App URLs
   BASE_URL=http://localhost:8080
   FRONTEND_URL=http://localhost:3000
   ```

4. **Start the Development Server**
   ```bash
   npm start
   ```
   *Note: `npm start` runs `nodemon src/index.ts`.*

## 🔌 API Endpoints

The API is prefixed with `/api/v0/`.

### Auth
- `GET /auth/github`: Login with GitHub.
- `GET /auth/github/callback`: GitHub OAuth callback.

### GitHub & Analysis
- `GET /github/repos`: Fetch all repositories for the logged-in user.
- `POST /github/:repo/complexity`: Calculate code complexity for a specific repository.
- `POST /github/:repo/create-post`: Generate a LinkedIn post from the repository's code.

### Jobs
- `GET /jobs`: Get all jobs.
- `POST /jobs`: Create a new job.
- `GET /jobs/:jobId/description`: Scrape and parse a job description from a URL.

### Resume
- `POST /resume`: Upload a resume link.
- `GET /resume`: Get all resumes.

## 🤝 Contributing

Contributions are welcome! Please fork the repository and submit a pull request for any enhancements or bug fixes.

## 📄 License

This project is licensed under the ISC License.
