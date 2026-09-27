# 💰 Expense Tracker MCP Server

An **MCP (Model Context Protocol) server** built with **FastMCP** that allows AI assistants such as Claude Desktop to manage and analyze personal expenses through MCP tools.

The server provides tools for adding expenses, retrieving expenses, and generating expense summaries.

---

## 🚀 Features

- ➕ Add new expenses
- 📋 List stored expenses
- 📊 Summarize expenses for a date range
- 🗂️ Access expense categories through an MCP resource
- 💾 Store expense data using SQLite
- 🤖 Integrate with MCP-compatible AI clients
- 🔐 Supports OAuth-protected remote MCP deployment
- 🔌 Can be connected through an MCP proxy

---

## 🏗️ Architecture

```text
                    ┌──────────────────────┐
                    │     Claude Desktop   │
                    └──────────┬───────────┘
                               │
                               │ MCP
                               ▼
                    ┌──────────────────────┐
                    │   Nikhil MCP Proxy   │
                    └──────────┬───────────┘
                               │
                               │ OAuth
                               ▼
              ┌────────────────────────────────┐
              │   Expense Tracker MCP Server   │
              │        FastMCP / Python        │
              └───────────────┬────────────────┘
                              │
                              ▼
                       ┌─────────────┐
                       │   SQLite    │
                       │ expenses.db │
                       └─────────────┘