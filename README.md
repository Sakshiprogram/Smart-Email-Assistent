# Smart Email Assistant

Smart Email Assistant is an AI-powered application that generates quick, professional, and customizable email replies. It uses a **Spring Boot backend**, the **Google Gemini API**, a **React frontend**, and a **Chrome extension** integrated with Gmail.

## Features

- Generate AI-powered email replies using Google Gemini
- Choose different reply tones, such as professional, friendly, formal, or casual
- Edit generated responses before sending
- React-based web interface
- Chrome extension integration with Gmail
- Spring Boot REST API backend

## Tech Stack

| Layer | Technology |
|---|---|
| Backend | Java, Spring Boot |
| AI Integration | Google Gemini API |
| Frontend | React |
| Browser Integration | Chrome Extension |
| Build Tool | Maven |
| API Communication | REST API |

## Project Structure

```text
Smart-Email-Assistent/
├── email-writer-sb/       # Spring Boot backend
├── email-writer-react/    # React frontend
├── email-writer-ext/      # Chrome extension for Gmail
├── helloWorld-ext/        # Basic Chrome extension example
└── .idea/                 # IDE configuration files
```

## How It Works

1. Open an email in Gmail.
2. Use the Chrome extension to select a reply tone.
3. The extension sends the email content to the Spring Boot backend.
4. The backend calls the Google Gemini API.
5. Gemini generates a suitable reply.
6. Review, edit, and use the generated response.

## Backend Setup

### Prerequisites

- Java 17 or later
- Maven
- Google Gemini API key

### Steps

Navigate to the backend directory:

```bash
cd email-writer-sb
```

Configure your Gemini API key in `application.properties`:

```properties
gemini.api.key=${GEMINI_API_KEY}
```

Set the `GEMINI_API_KEY` environment variable to your actual API key.

Run the backend:

```bash
mvn spring-boot:run
```

The backend will typically run at:

```text
http://localhost:8080
```

## Frontend Setup

### Prerequisites

- Node.js
- npm

### Steps

Navigate to the React frontend directory:

```bash
cd email-writer-react
```

Install dependencies and start the development server:

```bash
npm install
npm run dev
```

Open the local URL displayed in the terminal.

## Chrome Extension Setup

1. Open Google Chrome and navigate to `chrome://extensions/`.
2. Enable **Developer mode**.
3. Click **Load unpacked**.
4. Select the `email-writer-ext` directory.
5. Open Gmail and use the extension when replying to an email.

## API Endpoint

### Generate Email Reply

**Endpoint:**

```http
POST /api/email/generate
```

**Example request:**

```json
{
  "emailContent": "Hi, can you please share the project update?",
  "tone": "professional"
}
```

**Example response:**

```json
{
  "generatedReply": "Hello, thank you for reaching out. I will share the project update shortly."
}
```

*The request and response above illustrate the expected API format. Confirm the exact field names against your backend implementation.*

## Security

- Never commit or expose your Gemini API key.
- Store API keys in environment variables or local configuration files excluded from version control.
- Avoid sharing sensitive email content with external AI services without appropriate authorization.

Example configuration:

```properties
gemini.api.key=${GEMINI_API_KEY}
```

## Author

Created by [Sakshiprogram](https://github.com/Sakshiprogram)
