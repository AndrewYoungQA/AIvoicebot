# AI Voice Bot

AI Voice Bot is a tool that simulates realistic customer service interactions. It pairs a Virtual Customer with a Virtual Agent, enabling the testing and analysis of conversational quality. The Virtual Customer interacts naturally to resolve issues, while the system logs the entire conversation for compliance and quality assurance.

This application integrates with **Twilio** for call handling and **OpenAI** for real-time conversational AI. Key features include persona emulation, dynamic feedback, and detailed conversation logging.

---

## Table of Contents
1. [Getting Started](#getting-started)
2. [How it Works](#how-it-works)
3. [Developing](#developing)
   - [Prerequisites](#prerequisites)
   - [Testing](#testing)
4. [Contributing](#contributing)
5. [Documentation](#documentation)
6. [Licensing](#licensing)

---

## Getting Started

1. Install project dependencies using `yarn`.
2. Configure your `.env` file with the necessary API keys and credentials. Example .env:
   ```Dotenv
   TWILIO_ACCOUNT_SID=XXXXXXXXXXXXXXX
   TWILIO_AUTH_TOKEN=XXXXXXXXXXXXXXX
   TWILIO_PHONE_NUMBER=XXXXXXXXXXXXXXX

   AZURE_OPENAI_API_KEY=XXXXXXXXXXXXXXX
   AZURE_OPENAI_ENDPOINT=XXXXXXXXXXXXXXX
   AZURE_OPENAI_DEPLOYMENT_NAME=XXXXXXXXXXXXXXX
   AZURE_OPENAI_API_VERSION=XXXXXXXXXXXXXXX

   NUMBER_TO_CALL=XXXXXXXXXXXXXXX

   SERVER_URL=XXXXXXXXXXXXXXX
   ```
3. Install and configure ngrok to tunnel requests to your local server.

---

## How it Works

The AI Voice Bot integrates:

- **Twilio**: Handles calls and streams audio data in real time.
- **OpenAI Realtime API**: Provides AI-driven responses for the Virtual Customer.
- **Persona Simulation**: Customizes virtual customers with detailed personas, including culture, personality, and issues.
- **Conversation Logging**: Captures all interactions and metadata for later analysis.

### Workflow
1. **Call Handling**: Twilio streams audio data to the server.
2. **Persona Simulation**: A Virtual Customer persona is dynamically created.
3. **AI Integration**: OpenAI generates responses in real time.
4. **Logging and Analysis**: Conversations are logged and analyzed using the `conversationAnalyzer` module.

---

## Developing

### Prerequisites
- **Node.js** (v18+)
- **Yarn**
- **ngrok**: Download and authenticate (see [Getting Started](#getting-started)).
- Twilio credentials:
  - `TWILIO_ACCOUNT_SID`
  - `TWILIO_AUTH_TOKEN`
  - `TWILIO_PHONE_NUMBER`
- Azure OpenAI API:
   - `AZURE_OPENAI_API_KEY`
   - `AZURE_OPENAI_ENDPOINT`
   - `AZURE_OPENAI_DEPLOYMENT_NAME`
   - `AZURE_OPENAI_API_VERSION`

---

### Testing

1. Start the ngrok tunnel:

   "ngrok http 3000"

2. Update the `SERVER_URL` environment variable with the forwarding URL created when starting the ngrok tunnel

3. Start the server:

   `node src/server.js`

4. Start a call by sending a GET request to the `/start-call` endpoint setting the `numberToCall` query as the number you would like to call.

5. Generate logs by simulating conversations.

6. Analyze logs using:

   "python main.py"

---

## Contributing

1. Create a new branch for your feature:

   "git checkout -b feature/your-feature-name"

2. Make changes and test locally.

3. Commit changes:

   "git commit -m 'Added feature: description'"

4. Push the branch and create a pull request.

---

## Documentation

For further details, see the [QA Cresta Virtual Customer Documentation](https://brinkshome.atlassian.net/wiki/spaces/~74277865/pages/3793420301/QA+Cresta+Virtual+Customer).

For further details, see the [High Level - Test Plan for Virtual Agent](https://brinkshome.atlassian.net/wiki/spaces/~74277865/pages/3864199169/High+Level+-+Test+Plan+for+Virtual+Agent).

---

## Licensing

This project is private: Brinks Legal Statement.
