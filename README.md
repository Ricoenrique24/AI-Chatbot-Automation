# 🤖 AI Sales Automation Agent

![Project Status](https://img.shields.io/badge/Status-Completed-success)
![Tech Stack](https://img.shields.io/badge/n8n-Automation-ff6f61)
![AI](https://img.shields.io/badge/Gemini-GPT--4o-blue)
![Integration](https://img.shields.io/badge/Meta-Pixel-blue)

> **An intelligent, autonomous sales agent designed to revolutionize customer interaction workflows. Orchestrated with n8n and powered by Gemini, this system automates the journey from initial inquiry to order closing.**

---

## 🚀 Project Overview

In the high-volume retail and beauty industry, response time is currency. This project was developed to solve the bottleneck of manual customer service. By deploying a custom **AI Sales Agent**, we transitioned from reactive human responses to proactive, instant, and conversion-focused automation.

This system doesn't just "chat"; it understands context, handles objections, tracks user behavior via Meta Pixel, and guides potential customers toward a purchase decision, acting as a 24/7 top-tier sales representative.

## 💡 Key Features

* **🧠 Context-Aware Conversations:** Utilizes Gemini's LLM to understand customer intent, sentiment, and context, delivering human-like responses rather than rigid templates.
* **⚡ End-to-End Automation:** Handles the entire lifecycle: Greeting → Product Education → FAQ Handling → Order Closing.
* **📊 Data-Driven Tracking:** Integrated with **Meta Pixel (Conversions API)** to track user interactions and optimize marketing ad performance based on chat outcomes.
* **🔄 Human Handoff Protocol:** Intelligently detects complex issues that require human intervention and seamlessly transfers the chat to a live agent.
* **📂 CRM Integration:** Automatically logs customer data and order details into Google Sheets/Database for real-time record keeping.

## 🛠️ Tech Stack

* **Orchestration:** [n8n](https://n8n.io/) (Workflow Automation)
* **Brain (LLM):** Gemini API (Gemini / GPT-3.5 Turbo)
* **Analytics:** Meta Pixel & Conversions API
* **Database/Storage:** Google Sheets / PostgreSQL
* **Communication Channel:** WhatsApp Business API (via vendor integration)

## 📈 Impact & Results

Implemented in a real-world scenario (Beauty & Cosmetic Industry), this system delivered measurable business impact:

* **🚀 80% Increase in Human Efficiency:** Sales agents no longer answer repetitive queries, focusing only on high-value closing and complex issues.
* **⏱️ < 5 Seconds Response Time:** Eliminated wait times for customers, significantly improving User Experience (UX).
* **24/7 Availability:** Captured leads and inquiries outside of standard business hours.

## 🧩 Workflow Architecture
This system follows a logic-based flow to ensure accuracy and efficiency. It combines rule-based filtering with AI reasoning.

```mermaid
graph TD
    A[Customer Message] -->|Webhook| B(n8n Workflow)
    B --> C{AI Classification: Intent?}
    C -- Complex/Complaint --> D[🚨 Handoff to Human Agent]
    C -- Sales/Inquiry --> E[🔍 Retrieve Knowledge Base (RAG)]
    E --> F[🤖 Gemini Processing (Gemini)]
    F --> G[📝 Generate Personalized Response]
    G --> H[📲 Send to Customer (WhatsApp)]
    G --> I[💾 Log Interaction to Google Sheets]
    I --> J[🎯 Fire Meta Pixel Event]
```

## 💻 How It Works (The Logic)

The automation pipeline consists of 5 distinct stages:

1.  **Ingestion (Webhook):**
    * The system listens for incoming messages from the WhatsApp Business API via a Webhook trigger in n8n.

2.  **Intent Classification (The Brain):**
    * An AI node analyzes the incoming text to determine the customer's intent (e.g., "Asking Price", "Complaint", "Product Consultation", or "Ready to Buy").
    * *Safety Mechanism:* If the intent is flagged as "Complaint" or "Unknown", the system automatically routes the chat to a human agent to prevent frustration.

3.  **Retrieval Augmented Generation (RAG):**
    * If the query is about a product, the system queries the database (Google Sheets/PostgreSQL) to fetch the latest pricing, stock status, and product details. This ensures the AI never hallucinates prices.

4.  **Response Generation:**
    * Gemini (Gemini) constructs a natural, persuasive, and brand-aligned response using the retrieved data and the conversation history (context).

5.  **Action & Analytics:**
    * The response is sent back to the user.
    * Data is logged to the CRM.
    * **Meta Pixel Event** is fired (e.g., `Lead`, `Contact`) to feed the marketing algorithm with high-quality conversion data.

---

## 📷 Preview / Screenshots

> *Visual representation of the automation flow.*

### n8n Workflow Overview
![n8n Workflow](https://via.placeholder.com/800x400?text=Snapshot+of+Complete+n8n+Workflow)

### Chat Interaction Example
| User Query | AI Response |
| :--- | :--- |
| *"Kak, rekomendasi serum buat kulit berminyak dong?"* | *"Halo Kak! Untuk kulit berminyak, aku sangat sarankan **Serum X** karena mengandung Niacinamide yang bisa kontrol minyak. Kebetulan lagi ada promo diskon 20% hari ini loh. Mau aku bantu cek stoknya? 😊"* |

---

## 📬 Contact

Designed and developed by **Mochammad Enrique Lazuardi Ramadany**.

If you are interested in implementing similar AI automation solutions or discussing backend engineering, feel free to reach out.

* **LinkedIn:** [linkedin.com/in/merico](https://www.linkedin.com/in/merico)
* **Email:** mochammadenrique.25@gmail.com
* **GitHub:** [github.com/Ricoenrique24](https://github.com/Ricoenrique24)

---
*© 2025 Mochammad Enrique Lazuardi Ramadany. All Rights Reserved.*
