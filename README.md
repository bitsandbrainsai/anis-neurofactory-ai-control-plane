<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>ANIS – Personal AI Factory Controller</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
</head>
<body>

<h1>🏷️ Project Title</h1>
<h2>ANIS – Personal AI Factory Controller</h2>

<hr/>

<h1>🧾 Executive Summary</h1>
<p>
ANIS (Autonomous Neural Intelligence Supervisor) is an enterprise-grade Personal AI Factory Controller
designed to orchestrate complex data ingestion, transformation, analysis, and reporting workflows
through a single, intent-driven interface. The system combines Custom GPT Actions, n8n workflow
orchestration, Google Workspace automation, and a serverless OCR microservice to deliver a
fully automated, auditable, scalable, and production-ready AI data pipeline.
</p>
<p>
ANIS is intentionally engineered as a <strong>control plane</strong>, not a monolithic processor.
It delegates execution to specialized agents (Ingest, Clean, Analyze, Report) while enforcing
strict contracts, schemas, logging, and observability across the entire data lifecycle.
</p>

<hr/>

<h1>📑 Table of Contents</h1>
<ol>
  <li>Project Overview</li>
  <li>System Philosophy & Design Principles</li>
  <li>Objectives & Goals</li>
  <li>Acceptance Criteria</li>
  <li>Prerequisites</li>
  <li>Installation & Setup</li>
  <li>API Documentation</li>
  <li>Custom GPT Configuration</li>
  <li>UI / Frontend Architecture</li>
  <li>Status Codes</li>
  <li>Features</li>
  <li>Tech Stack & Architecture</li>
  <li>Workflow & Implementation</li>
  <li>Agent Responsibilities</li>
  <li>Data Lake Design</li>
  <li>Testing & Validation</li>
  <li>Validation Summary</li>
  <li>Verification Tools</li>
  <li>Troubleshooting</li>
  <li>Security & Secrets</li>
  <li>Deployment</li>
  <li>Quick-Start Cheat Sheet</li>
  <li>Usage Notes</li>
  <li>Performance & Optimization</li>
  <li>Enhancements</li>
  <li>Maintenance & Future Work</li>
  <li>Key Achievements</li>
  <li>High-Level Architecture</li>
  <li>Folder Structure</li>
  <li>How to Demonstrate Live</li>
  <li>Summary, Closure & Compliance</li>
</ol>

<hr/>

<h1>🧩 Project Overview</h1>
<p>
ANIS provides a unified command interface that allows users (human or system) to trigger
complex automation pipelines using a single structured JSON command. The platform abstracts
away workflow complexity while preserving transparency, traceability, and governance.
</p>
<p>
Core capabilities include:
</p>
<ul>
  <li>Automated Gmail attachment ingestion</li>
  <li>RAW → CLEAN → GOLD data lake transitions</li>
  <li>OCR-based PDF text extraction</li>
  <li>Structured normalization of CSV, XLS, JSON, TXT</li>
  <li>AI-driven analysis and KPI generation</li>
  <li>Daily scheduled execution via cron</li>
</ul>

<hr/>

<h1>🧠 System Philosophy & Design Principles</h1>
<ul>
  <li><strong>Single Responsibility Agents</strong> – Each agent performs exactly one domain function</li>
  <li><strong>Contract-First Design</strong> – All interactions validated via schemas</li>
  <li><strong>Auditability by Default</strong> – Every action logged</li>
  <li><strong>Stateless Execution</strong> – Workflows remain restart-safe</li>
  <li><strong>Enterprise Observability</strong> – Logs, metrics, and artifacts persisted</li>
</ul>

<hr/>

<h1>🎯 Objectives & Goals</h1>
<ul>
  <li>Enable non-technical operators to run advanced AI workflows</li>
  <li>Minimize human intervention while preserving control</li>
  <li>Ensure deterministic and repeatable executions</li>
  <li>Provide enterprise-ready documentation and structure</li>
</ul>

<hr/>

<h1>✅ Acceptance Criteria</h1>
<table border="1">
<tr>
<th>Category</th><th>Requirement</th>
</tr>
<tr>
<td>Execution</td><td>Exactly one agent per request</td>
</tr>
<tr>
<td>Logging</td><td>All actions recorded in EVENT_LOG</td>
</tr>
<tr>
<td>Data</td><td>Strict RAW → CLEAN → GOLD lifecycle</td>
</tr>
<tr>
<td>Security</td><td>No secrets committed to repository</td>
</tr>
</table>

<hr/>

<h1>💻 Prerequisites</h1>
<ul>
  <li>Node.js ≥ 18</li>
  <li>n8n ≥ 1.x (self-hosted or cloud)</li>
  <li>Google Workspace (Gmail, Drive, Sheets)</li>
  <li>OpenAI API access</li>
  <li>Vercel account for OCR microservice</li>
</ul>

<hr/>

<h1>⚙️ Installation & Setup</h1>
<ol>
  <li>Clone the repository</li>
  <li>Create environment variables from <code>.env.example</code></li>
  <li>Install serverless dependencies</li>
  <li>Import n8n workflows (agents, interactive, scheduled)</li>
  <li>Configure Google OAuth credentials</li>
  <li>Deploy OCR service on Vercel</li>
</ol>

<hr/>

<h1>🔗 API Documentation</h1>
<p><strong>Endpoint:</strong> <code>POST /webhook/anis</code></p>
<p><strong>Purpose:</strong> Dispatches commands to ANIS Hub</p>

<pre>
{
  "agent": "ingest | clean | analyze | report",
  "source": {
    "gmailQuery": "has:attachment",
    "days": 7
  },
  "options": {
    "attachmentsOnly": true,
    "fileTypes": ["pdf","csv","xlsx"]
  },
  "return": "summary | kpis | log | files"
}
</pre>

<hr/>

<h1>🧠 Custom GPT Configuration</h1>
<ul>
  <li>Strict instruction-based role definition</li>
  <li>Conversation starters for guided execution</li>
  <li>OpenAPI schema enforcement</li>
  <li>Single-action execution constraint</li>
</ul>

<hr/>

<h1>🖥️ UI / Frontend: Pages, Components, State Flow</h1>
<ul>
  <li>Interface: OpenAI Custom GPT UI</li>
  <li>State: Stateless request → response cycle</li>
  <li>Network: HTTPS webhook calls</li>
  <li>Styling: Managed by platform UI</li>
</ul>

<hr/>

<h1>🔢 Status Codes</h1>
<table border="1">
<tr>
<th>Code</th><th>Meaning</th>
</tr>
<tr><td>200</td><td>Success</td></tr>
<tr><td>400</td><td>Invalid payload</td></tr>
<tr><td>401</td><td>Unauthorized</td></tr>
<tr><td>500</td><td>Execution failure</td></tr>
</table>

<hr/>

<h1>🚀 Features</h1>
<ul>
  <li>Intent-based automation</li>
  <li>Multi-format file processing</li>
  <li>OCR-powered extraction</li>
  <li>Scheduled and interactive workflows</li>
  <li>Enterprise-grade logging</li>
</ul>

<hr/>

<h1>🧱 Tech Stack & Architecture</h1>
<table border="1">
<tr>
<th>Layer</th><th>Technology</th>
</tr>
<tr><td>Control Plane</td><td>Custom GPT</td></tr>
<tr><td>Orchestration</td><td>n8n</td></tr>
<tr><td>Storage</td><td>Google Drive</td></tr>
<tr><td>Metadata</td><td>Google Sheets</td></tr>
<tr><td>OCR</td><td>Vercel Serverless</td></tr>
</table>

<pre>
[ User / System ]
        |
        v
[ Custom GPT ]
        |
        v
[ n8n Webhook ]
        |
+--------+--------+--------+--------+
| Ingest | Clean  | Analyze| Report |
        |
[ Data Lake (Drive + Sheets) ]
</pre>

<hr/>

<h1>🛠️ Workflow & Implementation</h1>
<ol>
  <li>Request validated against OpenAPI schema</li>
  <li>ANIS determines target agent</li>
  <li>Agent workflow executes in n8n</li>
  <li>Files processed and stored</li>
  <li>Logs and outputs returned</li>
</ol>

<hr/>

<h1>🧪 Testing & Validation</h1>
<table border="1">
<tr>
<th>ID</th><th>Area</th><th>Command</th><th>Expected Output</th><th>Explanation</th>
</tr>
<tr>
<td>T01</td><td>Ingest</td><td>POST /webhook/anis</td><td>RAW files created</td><td>Gmail ingestion</td>
</tr>
<tr>
<td>T02</td><td>Clean</td><td>Agent clean</td><td>CLEAN files created</td><td>Normalization</td>
</tr>
</table>

<hr/>

<h1>🔒 Security & Secrets</h1>
<ul>
  <li>Secrets stored in <code>.env</code></li>
  <li>OAuth credentials isolated</li>
  <li>Webhook endpoints protected</li>
</ul>

<hr/>

<h1>☁️ Deployment (Vercel)</h1>
<ul>
  <li>Serverless OCR deployment</li>
  <li>Environment isolation</li>
  <li>Stateless execution model</li>
</ul>

<hr/>

<h1>⚡ Quick-Start Cheat Sheet</h1>
<pre>
git clone repo
cp .env.example .env
npm install
n8n start
</pre>

<hr/>

<h1>🗂️ Folder Structure (Tree)</h1>
<pre>
diagrams/
gpt/
schemas/
screenshots/
workflows/
  agents/
  interactive/
  scheduled/
serverless/
</pre>

<hr/>

<h1>🧭 How to Demonstrate Live (Exact Commands)</h1>
<pre>
POST /webhook/anis
{
  "agent": "ingest"
}
</pre>

<hr/>

<h1>💡 Summary, Closure & Compliance</h1>
<p>
ANIS demonstrates a mature, enterprise-level automation architecture that bridges AI,
workflow orchestration, and data governance. The system is compliant with modern
automation standards, extensible by design, and suitable for real-world production use.
</p>

</body>
</html>
