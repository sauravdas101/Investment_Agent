# Multi-Agent Financial Research Analyst 📈
An autonomous AI agentic pipeline built with LangGraph and Gemini 2.0 Flash that performs deep-dive research on both public and private companies. This project demonstrates advanced LLM patterns including conditional routing, parallel state management, and automated report generation.

# Overview
Traditional investment research requires manually checking financial statements, analyst targets, and recent news. This agent automates that "first hour" of research in under 30 seconds.

Key Features
Autonomous Routing: The agent detects if a company is public or private.

Public Path: Aggregates Income Statements, Balance Sheets, Analyst Price Targets (Mean/High/Low), and News Sentiment.

Private Path: Gracefully degrades to focus solely on news sentiment and narrative analysis when financial data is unavailable.

Multi-Agent Architecture: Specialized nodes handle specific data domains (Fundamentals, Quant, Sentiment) to reduce LLM hallucinations.

State-Aware Design: Uses LangGraph to manage data flow and maintain a persistent research state.

Professional Output: Automatically generates a formatted PDF Research Report.

# 🏗️ Architecture
The system uses a directed acyclic graph (DAG) to manage the research workflow:

The Router: Inspects the ticker/entity name via yfinance.

Fundamental Agent: Extracts revenue growth, debt-to-equity, and operating margins.

Quant Agent: Fetches real-time price targets and recommendation keys (Buy/Hold/Sell).

Sentiment Agent: Scrapes recent headlines and performs NLP sentiment analysis.

Lead Analyst: Synthesizes all data points into a coherent investment thesis.

# 🛠️ Tech Stack
Orchestration: LangGraph

LLM: Google Gemini 2.0 Flash

Data Sources: Yahoo Finance API (yfinance)

Environment: Google Colab / Python 3.12

PDF Generation: fpdf

# 🚦 How to Run
## Clone the Repository:
```bash
#!/bin/bash

git clone https://github.com/sauravdas101/Investment_Agent.git
cd Investment_agent
```
## Install Dependencies:
```bash
#!/bin/bash

pip install -U langgraph langchain-google-genai yfinance fpdf
```
## Set Up API Key:

Obtain a free API Key from Google AI Studio.

Add it to your environment variables as GOOGLE_API_KEY.

## Execute:

Run the notebook or script. Input a ticker like NVDA for a full public report or OpenAI for a private narrative analysis.
# 📊 Sample Output
The agent produces a professional Investment Research Report (PDF) including:
