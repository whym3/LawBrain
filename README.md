# <img width="25" height="25" alt="Image" src="https://github.com/user-attachments/assets/a0051ef4-943b-4e65-804d-6ce6d5748e6a" /> Law Brain

An AI-powered legal assistant platform designed specifically for lawyers and legal professionals. Law Brain combines the power of large language models with specialized legal tools to streamline legal work, document drafting, and case analysis.

**website** -> www.thelawbrain.com  (Still in Progress)

## ChatUI
![Image](https://github.com/user-attachments/assets/27011a96-6471-4cee-b098-073132511f3f)

## Canvas (For Drafting Documents)
![Image](https://github.com/user-attachments/assets/de1d5579-9f9f-40c9-b0d1-7a02442565e5)

## 🌟 Features

### 💬 AI Chat Interface
- Chat with any Large Language Model (LLM) including GPT, Claude, and others
- **Offline support** using Ollama for privacy-sensitive legal work
- Customizable model selection based on your needs and preferences
- Secure, encrypted conversations for confidential legal discussions

### 📚 Knowledge Base
- Store and organize contracts, legal documents, and company documentation
- AI-powered document search and retrieval
- Question any document using natural language queries
- Secure document storage with access controls
- Support for various file formats (PDF, DOCX, TXT, etc.)

### 🤖 Specialized AI Agents
Pre-built and customizable AI agents for different legal specializations:
- **Criminal Lawyer Agent** - Criminal law procedures, case analysis, and defense strategies
- **Family Lawyer Agent** - Divorce, custody, adoption, and family law matters
- **Corporate Lawyer Agent** - Business law, compliance, and corporate governance
- **Contract Lawyer Agent** - Contract analysis, negotiation, and drafting
- **Immigration Lawyer Agent** - Visa applications, citizenship, and immigration law
- **Personal Injury Agent** - Tort law, insurance claims, and compensation cases

*All agents are fully customizable to match your practice area and preferences*

### 🎨 Canvas Interface
- **AI-powered document drafting** using natural language prompts
- Create contracts, agreements, legal briefs, and other legal documents
- Real-time collaborative editing
- Template library for common legal documents
- Version control and document history
- Export to various formats (PDF, DOCX, etc.)

## 🚀 Quick Start

### Prerequisites
- Docker and Docker Compose
- Node.js (v18 or higher)
- Yarn package manager

### 1. Chat UI Setup

Navigate to the chat interface directory and start the service:

```bash
cd chatui
docker compose up --build -d
```

The chat UI will be available at: **http://localhost:8080**

### 2. Canvas Interface Setup

#### Install Dependencies
```bash
cd canvas
yarn install
```

#### Build the Project
```bash
yarn build
```

#### Start Frontend (Web Interface)
```bash
cd apps/web
yarn dev
```
Frontend will be available at: **http://localhost:3000**

#### Start Backend (Agents Service)
```bash
cd apps/agents
yarn dev
```
Backend API will be available at: **http://localhost:54367**

## ⚙️ Configuration

### Environment Variables

Law Brain uses environment files to configure LLM providers and other settings. You can customize these based on your preferred language models:

#### Chat UI Configuration
Edit `chatui/.env` to configure your LLM providers:
```env
# OpenAI Configuration
OPENAI_API_KEY=your_openai_key
OPENAI_MODEL=gpt-4

# Anthropic Claude Configuration
ANTHROPIC_API_KEY=your_anthropic_key
ANTHROPIC_MODEL=claude-3-sonnet

# Ollama Configuration (for offline use)
OLLAMA_BASE_URL=http://localhost:11434
OLLAMA_MODEL=llama2

# Database Configuration
DATABASE_URL=your_database_url
```

#### Canvas Configuration
Edit `canvas/.env` for canvas-specific settings:
```env
# LLM Provider for Document Generation
LLM_PROVIDER=openai
API_KEY=your_api_key
MODEL_NAME=gpt-4

# Database for Document Storage
DATABASE_URL=your_database_url

# Authentication
JWT_SECRET=your_jwt_secret
```

### Supported LLM Providers
- **OpenAI** (GPT-3.5, GPT-4, GPT-4 Turbo)
- **Anthropic Claude** (Claude 3 Haiku, Sonnet, Opus)
- **Ollama** (Llama 2, Code Llama, Mistral, and other open-source models)
- **Google PaLM/Gemini**
- **Azure OpenAI**
- **Custom API endpoints**

## 📖 Usage Guide

### Using the Chat Interface
1. Access the chat UI at `localhost:8080`
2. Select your preferred LLM model
3. Choose a specialized legal agent or use general chat
4. Start asking legal questions or upload documents for analysis

### Using the Knowledge Base
1. Upload legal documents, contracts, or case files
2. Use natural language to search and query your documents
3. Get AI-powered insights and summaries
4. Cross-reference multiple documents for comprehensive analysis

### Using AI Agents
1. Select the appropriate legal specialist agent
2. Provide case details or legal questions
3. Get specialized advice and recommendations
4. Customize agent behavior and knowledge base

### Using the Canvas
1. Access the canvas at `localhost:3000`
2. Choose a document type or start from scratch
3. Use natural language prompts to generate content
4. Edit and refine documents with AI assistance
5. Export finished documents in your preferred format

## 🔒 Security & Privacy

- **Local deployment** ensures your legal data stays on your infrastructure
- **Offline LLM support** via Ollama for maximum privacy
- **Encrypted document storage** and secure API communications
- **Access controls** and user authentication
- **Audit logs** for compliance and tracking

### Contributing
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🆘 Support

For support, questions, or feature requests:
- Create an issue in the GitHub repository
- Check the documentation in the `/docs` folder
- Contact the development team

## 🚧 Roadmap

- [ ] Advanced legal citation analysis
- [ ] Integration with legal databases (Westlaw, LexisNexis)
- [ ] Mobile application
- [ ] Advanced workflow automation
- [ ] Multi-language support for international law
- [ ] Voice-to-text legal dictation
- [ ] Advanced security features (2FA, SSO)

---

*Law Brain - Empowering legal professionals with AI technology while maintaining the highest standards of privacy and security.*
