🤖 AI Omnichannel Customer Service Platform

An enterprise-ready, scalable AI communication engine designed to automate complex customer interactions. This platform bridges the gap between traditional CRM systems and generative AI, providing a seamless, multilingual (English & Tunisian Darija 🇹🇳) automated support experience across Web, WhatsApp, and Real-time Voice Calls.

🏗️ System Architecture & Design

Built with a Modular Monolith approach, the system prioritizes the Open/Closed Principle, ensuring the core business logic remains agnostic of the specific LLM provider or messaging channel.

<p align="center">

<img src="https://images2.imgbox.com/39/a4/0XvjR1kE_o.png" alt="System Architecture" width="100%" />

</p>

🔷 Architectural Decisions (Senior Focus)

Hybrid AI Strategy: Uses Ollama locally for cost-effective, low-latency NLU (Intent Detection) and Claude 3 for high-reasoning dialogue generation.

Event-Driven Ingress: Messaging hooks (WhatsApp/Messenger) and Voice streams are treated as generic "Events," allowing for easy extensibility to new channels.

Persistence Strategy: PostgreSQL utilizes JSONB for flexible AI metadata storage while maintaining ACID compliance for relational CRM data.

🌟 Key Features

🧠 Advanced AI Capabilities

Context-Aware Reasoning: Implements a sliding-window memory to maintain long-term conversation state.

Regional Localization: Native support for the Tunisian dialect (Darija), handling unique linguistic nuances that standard LLMs often miss.

Intent-Based Routing: Automatically classifies requests (e.g., Refund, Inquiry, Complaint) to trigger specific business workflows.

📞 Voice & Omnichannel Integration

Real-time Voice Calls: Process actual phone calls using a low-latency STT/TTS pipeline (Speech-to-Text -> LLM -> Text-to-Speech).

WhatsApp & Messenger: Unified dashboard for social messaging.

Barge-in Support: The AI can detect when a user interrupts during a voice call and stop speaking immediately.

📊 Enterprise Management

CRM Connectivity: Synchronizes with customer profiles to provide personalized service.

Analytics Dashboard: Real-time tracking of sentiment, resolution rates, and API latency.

⚙️ Backend Implementation

The Spring Boot core follows DDD (Domain-Driven Design) principles to keep the logic decoupled.

🔷 Strategic Design Patterns

Strategy Pattern: Hot-swap LLM providers (Claude vs. Ollama) based on cost or request complexity.

Adapter Pattern: Standardizes payloads from different providers (Twilio, Meta, Vapi) into a single internal messaging DTO.

Observer Pattern: Asynchronous logging and analytics to prevent blocking the main response thread.

Plaintext



src/main/java/com/platform/backend

├── 🏛️ config             # Security (JWT), CORS, and AI Bean Definitions

├── 🔌 controllers        # Versioned REST API (/api/v1)

├── 🧠 domain             # Business logic & Entities

│   ├── ai                # Prompt logic & Strategy Implementation

│   ├── voice             # WebSocket & Media Stream handling

│   └── chat              # Conversation state & Context management

🛠️ Tech Stack

ComponentTechnologyLanguageJava 17 (Records, Sealed Classes)FrameworkSpring Boot 3.x, Spring Security, Spring Data JPAAI ModelsClaude 3.5 Sonnet (Cloud), Ollama/Llama 3 (Local)DatabasePostgreSQL 15Real-timeWebSockets for Voice StreamingInfrastructureDocker, GitHub Actions (CI/CD)🚀 Getting Started

Prerequisites

JDK 17+

Docker & Docker Compose

Ollama (Running llama3 locally)

Setup & Run

Clone the repository

Bash



git clone https://github.com/yourusername/ai-customer-platform.gitcd ai-customer-platform

Environment Configuration

Update src/main/resources/application.yml with your Claude API Key.

Start Services

Bash



docker-compose up -d

mvn spring-boot:run

🤝 Contributing & Contact

Contributions are what make the open-source community an amazing place to learn and create.

I am always open to discussing system design, AI, or potential collaborations!

LinkedIn: YassineKalaiEzzar


Email: YassineKalaiEzzar@gmail.com
