🤖 AI-Powered Omnichannel Customer Service Platform

An enterprise-grade, scalable AI communication engine. This platform bridges the gap between traditional CRM systems and generative AI, providing a seamless, multilingual (English & Tunisian Darija 🇹🇳) automated support experience across WhatsApp, Messenger, and Web.

🏗️ System Architecture & Design

As a junior engineer focused on Scalable Systems, I built this project with a "Production-First" mindset, prioritizing decoupling and the Open/Closed Principle.

🔷 High-Level Infrastructure

The system follows a distributed architecture pattern where the Spring Boot core acts as the orchestrator between the entry gateways and the AI inference engines.

🔷 AI Orchestration Pipeline

Instead of simple API calls, this project implements a Chain-of-Thought pipeline:

NLU Layer (Ollama): Localized intent detection and entity extraction (e.g., identifying a "Refund" intent in Tunisian Darija).

Context Management: Retrieving RAG-based data or conversation history from PostgreSQL.

Inference Layer (Claude 3): Generating high-fidelity, empathetic responses based on the enriched context.

🔷 Backend Layered Architecture (SOLID Focus)

The codebase is structured into cohesive modules to ensure maintainability:

Controller Layer: RESTful entry points with centralized Exception Handling.

Service Layer: Business logic implementation.

AI Strategy Layer: An abstraction layer allowing the platform to hot-swap between Claude, OpenAI, or local Llama models without breaking the core service.

Persistence Layer: Spring Data JPA with optimized query indexing for conversation logs.

🌟 Key Features

🧠 Hybrid AI Strategy: Uses Ollama locally for cost-effective NLU and Claude for complex dialogue reasoning.

🌍 Regional Localization: Native support for the Tunisian dialect (Darija), handling unique linguistic nuances.

💬 Omnichannel Sink: A unified message processing interface that treats WhatsApp, Messenger, and Web hooks as generic "Events."

📊 Real-time Analytics: Tracks sentiment analysis, response latency, and resolution rates.

🛠️ Tech Stack & Engineering Decisions

ComponentTechnologyWhy?RuntimeJava 17Records, Sealed Classes, and enhanced performance.FrameworkSpring Boot 3.xIndustry standard for robust, production-ready microservices.SecuritySpring Security + JWTStateless authentication for scalable API consumption.DatabasePostgreSQLRelational integrity for complex CRM mapping.AI ModelsClaude 3 & OllamaBalancing high-end reasoning with local, private NLU processing.📡 API Design Snippet

The platform follows a standardized RESTful maturity level:

POST /api/v1/messages

JSON



{

  "senderId": "user_123",

  "channel": "WHATSAPP",

  "content": "Asslema, nheb naaref mwaid el khedma",

  "metadata": { "language": "ar-TN" }

}

🚀 Getting Started

Prerequisites

JDK 17 or higher

Docker & Docker Compose

Ollama (Running llama3 or mistral locally)

Installation

Clone the Repo

Bash



git clone https://github.com/yourusername/ai-customer-service.git

Environment Setup

Configure your application.yml with Anthropic API keys and DB credentials.

Spin up Services

Bash



docker-compose up -d

mvn spring-boot:run

🗺️ Roadmap & Future Vision

[ ] Multi-tenant SaaS Architecture: Allow multiple businesses to manage their own AI bots on one instance.

[ ] Human-in-the-loop (HITL): Seamlessly hand off complex queries to a live human agent.

[ ] Voice Integration: Real-time STT/TTS for phone-based AI support.

🤝 Contact & Contribution

I am always open to discussing system design, AI, or potential collaborations!

LinkedIn: YassineKalaiEzzar


Email: YassineKalaiEzzar@gmail.com
