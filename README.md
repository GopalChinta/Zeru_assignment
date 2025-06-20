//// FILE: package.json
{
  "name": "eigenlayer-restake-api",
  "version": "1.0.0",
  "main": "app.js",
  "type": "module",
  "scripts": {
    "start": "node app.js"
  },
  "dependencies": {
    "axios": "^1.6.7",
    "express": "^4.18.2",
    "graphql-request": "^6.1.0",
    "dotenv": "^16.3.1"
  }
}

//// FILE: README.md
# 🛠️ EigenLayer Restaking Info API

This project is a Node.js backend service that fetches and exposes **restaking data** from **EigenLayer** using **The Graph Protocol**. It provides clean REST API endpoints for:

- ✅ User restaking info
- ✅ Validator metadata (including slash history and status)

> 🗖 Submission-Ready: Includes `.env` setup, GraphQL integration, and demo endpoints tested via Postman.

---

## 🔍 Features

- Fetches data from **The Graph subgraph** for EigenLayer
- REST API built using **Express.js**
- GraphQL queries executed using **graphql-request**
- Environment variables managed using **dotenv**
- Clean modular structure with routing and services separated

---

## 📆 Technologies Used

| Tech         | Purpose                    |
|--------------|----------------------------|
| Node.js      | Backend runtime            |
| Express.js   | REST API framework         |
| GraphQL      | Data queries via The Graph |
| graphql-request | Lightweight GraphQL client |
| dotenv       | Load `.env` variables      |

---

## 📁 Folder Structure

```
eigenlayer-restake-api/
├── api/                  # Express routes
│   ├── users.js
│   └── validators.js
├── services/             # GraphQL query logic
│   ├── graphqlClient.js
│   └── eigenQueries.js
├── utils/                # Response formatters
│   └── formatters.js
├── .env                  # Environment config (GraphQL endpoint)
├── app.js                # Entry point
├── package.json          # Dependencies & scripts
```

---

## 🔧 Setup Instructions

### 1. Clone the Repository
```bash
git clone https://github.com/GopalChinta/Zeru_assignment
cd eigenlayer-restake-api
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Create `.env` File
Create a `.env` file in the root folder with:

```
PORT=3000
GRAPH_ENDPOINT=https://api.thegraph.com/subgraphs/id/68g9WSC4QTUJmMpuSbgLNENrcYha4mPmXhWGCoupM7kB
```

### 4. Run the Server
```bash
npm start
```

Expected output:
```
📅 Server running on http://localhost:3000
```

---

## 📡 API Endpoints

### `GET /api/restaking/users`
Returns list of users who restaked stETH:
```json
[
  {
    "userAddress": "0xabc...",
    "amountRestaked": "100.0",
    "targetAVSOperator": "0xdef..."
  }
]
```

### `GET /api/restaking/validators`
Returns validator metadata:
```json
[
  {
    "operatorAddress": "0x123...",
    "totalDelegated": "5000",
    "validatorStatus": "active",
    "slashHistory": [
      {
        "timestamp": "2025-01-01T10:00:00Z",
        "amount": "25.0",
        "reason": "downtime"
      }
    ]
  }
]
```

---

## 🎥 Demo

> 📹 [Watch Demo Video on Google Drive](https://drive.google.com/...)  
(Uploaded and set to “Anyone with the link can view”)

---

## 🧠 Notes

- No database is required (data comes directly from on-chain subgraph)
- Easily extendable for caching or frontend consumption
- Developed for an assignment on EigenLayer integration

---

## 📄 License

MIT License. Use freely for educational or portfolio purposes.

---

### 👨‍💻 Built by GopalChinta

