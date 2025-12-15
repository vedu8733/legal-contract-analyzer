# 🧾 Legal Contract Analyzer (AI + Neo4j)

An **AI-powered legal contract analysis system** that reads contract PDFs, extracts key clauses, identifies risks, and stores **explainable legal insights** in a **Neo4j Knowledge Graph**.

This project demonstrates how **Large Language Models (LLMs)** and **Graph Databases** can be combined to build **transparent and scalable legal intelligence systems**.

---

## 🚀 Key Features

- 📄 Works on **any legal contract PDF** (no fixed format)
- 🤖 AI-based clause extraction and risk classification
- 🧠 Explains **why** a clause is risky (Explainable AI)
- 🕸️ Stores structured knowledge in **Neo4j graph database**
- 📂 Supports **multiple contracts** (batch processing)
- 🧾 Prints human-readable summaries in terminal
- 🔍 Enables graph-based querying and analysis

---

## 🛠️ Tech Stack

| Component | Technology |
|---------|------------|
| Programming Language | Python |
| LLM (Free) | Groq – LLaMA 3.1 |
| Graph Database | Neo4j |
| PDF Text Extraction | PyMuPDF |
| Environment Management | python-dotenv |
| Interface | Jupyter Notebook |

---

## 📂 Project Structure

legal-contract-analyzer/
│
├─ Legal_Contract_Analyzer.ipynb # Main notebook
├─ README.md
├─ .gitignore
└─ contracts/ # Input contract PDFs
├─ contract_1.pdf
├─ contract_2.pdf


---

## ⚙️ Setup Instructions

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/vedu8733/legal-contract-analyzer.git
cd legal-contract-analyzer


python -m venv venv
venv\Scripts\activate

pip install pymupdf neo4j groq python-dotenv jupyter

Setup Environment Variables

Create a .env file (do NOT upload to GitHub):

GROQ_API_KEY=your_groq_api_key
NEO4J_URI=neo4j://localhost:7687
NEO4J_USERNAME=neo4j
NEO4J_PASSWORD=your_neo4j_password

```

5️⃣ Start Neo4j

Open Neo4j Desktop

Create & start a Local DBMS

Ensure database neo4j is RUNNING

6️⃣ Run the Project

Open Legal_Contract_Analyzer.ipynb

Place PDFs inside the contracts/ folder

Run all cells

AI-generated summaries will be printed in the terminal

Structured data will be stored in Neo4j

🧠 Knowledge Graph Model
(:Contract)
   ├─[:IS_PARTY_TO]─(:Organization)
   ├─[:HAS_DATE]───(:ImportantDate)
   ├─[:HAS_CLAUSE]─(:Clause)
                         ├─[:HAS_RISK]─────────(:Risk)
                         ├─[:HAS_REASON]───────(:RiskReason)
                         ├─[:HAS_OBLIGATION]───(:Obligation)
                         ├─[:HAS_LIABILITY]────(:Liability)
                         └─[:HAS_AI_SUMMARY]───(:AISummary)

🔍 Example Neo4j Queries
View all contracts
MATCH (c:Contract)
RETURN c.title;

Find high-risk clauses
MATCH (cl:Clause)-[:HAS_RISK]->(r:Risk)
WHERE r.level = "HIGH"
RETURN cl.name, r.level;

Why is a clause risky?
MATCH (cl:Clause)-[:HAS_REASON]->(rr)
RETURN cl.name, rr.text;

🎓 Use Cases

Legal contract review automation

Risk identification & compliance analysis

Explainable AI in legal technology

AI + Graph Database learning project

Final-year / internship project
