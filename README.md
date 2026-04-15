This project demonstrates a sophisticated LLM (Large Language Model) orchestration pattern. It uses a **Router-Task-Clarifier** architecture to efficiently handle user requests while maintaining state across turns using a local database.

## 🛠️ Key Features
- **Intelligent Routing:** A specialized LLM 'Router' determines if a query is Technical, Billing-related, or General.
- **Short-Term Memory:** Uses **SQLite** to persist the last N turns of a conversation, allowing for contextual follow-up questions.
- **Specialized Agents:** Separate prompt templates (Specialists) for different domains to ensure high-quality responses.
- **Defensive Parsing:** Robust JSON extraction logic to handle LLM formatting inconsistencies.

## 🏗️ Architecture
1. **Input Layer:** Receives user text.
2. **Memory Layer:** Fetches recent conversation history from SQLite.
3. **Decision Layer (Router):** Evaluates context + input to select the best execution path.
4. **Execution Layer:** Routes to `tech_task`, `billing_task`, or `clarifier_task`.
5. **Persistence Layer:** Saves the turn back to the database.

## 🚀 Getting Started
1. Open the notebook in Google Colab.
2. Add your `OPENAI_API_KEY` to Colab Secrets.
3. Run all cells to initialize the database and start the orchestrator.

## 🧰 Tech Stack
- Python
- OpenAI API
- SQLite
- Dataclasses & Typing
