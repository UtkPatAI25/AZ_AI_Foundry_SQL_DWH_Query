# Use Azure AI Foundry to generate and query SQL Server Data Warehouse

This project is an AI-powered SQL assistant that enables users to query a SQL Data Warehouse using natural language. It leverages Azure OpenAI, LangChain, and Gradio to generate and explain SQL queries, returning results and explanations in a user-friendly web interface.

## Features

- **Natural Language to SQL:** Converts user questions into SQL, executes them, and explains the results.
- **Azure OpenAI Integration:** Uses Azure-hosted LLMs for robust natural language understanding and generation.
- **Automatic Query Correction:** Detects query errors and attempts to fix them automatically.
- **Interactive Web UI:** Built with Gradio for easy local or remote use.
- **Customizable for Your Schema:** Reads schema metadata for accurate query generation.

---

## Quick Start

### 1. Clone the Repository

```bash
git clone https://github.com/UtkPatAI25/AZ_AI_Foundry_SQL_DWH_Query.git
cd AZ_AI_Foundry_SQL_DWH_Query
```

---

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```
<sub>If `requirements.txt` is missing, install manually: `pip install langchain langchain-openai sqlalchemy pandas gradio python-dotenv`</sub>

---

### 3. Configure Environment Variables

Create a `.env` file in the project root with the following contents:

```
py-connectionString=YOUR_SQL_CONNECTION_STRING
AZURE_OPENAI_DEPLOYMENT_NAME=YOUR_DEPLOYMENT_NAME
AZURE_OPENAI_ENDPOINT=YOUR_OPENAI_ENDPOINT
AZURE_OPENAI_API_KEY=YOUR_API_KEY
AZURE_OPENAI_API_VERSION=2024-02-15-preview
```

---

### 4. Prepare Your Database

Ensure your SQL database contains a table named `schema_metadata` with the following columns:

- `table_schema`
- `table_name`
- `column_name`
- `data_type`
- `description`

This allows the assistant to understand your database schema.

---

### 5. Run the Application

You can run the notebook in Jupyter or convert it to a Python script:

**Using Jupyter:**
```bash
jupyter notebook AzAIFo_OpenAI_SQL.ipynb
```
**Or, as a script:**
```bash
jupyter nbconvert --to script AzAIFo_OpenAI_SQL.ipynb
python AzAIFo_OpenAI_SQL.py
```

---

### 6. Access the Web Interface

After launch, access the Gradio web UI at:  
[http://127.0.0.1:7865](http://127.0.0.1:7865)

---

## How to Create an Azure AI Foundry Project and Deployment

### 1. Create an Azure OpenAI Resource

- Go to the [Azure Portal](https://portal.azure.com/).
- Click **Create a resource** > search “Azure OpenAI” > **Create**.
- Fill in Subscription, Resource group, Region, and Name.
- Click **Review + create**, then **Create**.

### 2. Deploy a Model

- Go to your Azure OpenAI resource.
- In the left menu, select **Deployments** > **+ Create**.
- Choose a model (e.g., `gpt-4`, `gpt-3.5-turbo`).
- Enter a **deployment name** (save this for your `.env`).
- Click **Create**.

### 3. Obtain Endpoint and API Key

- In your OpenAI resource, select **Keys and Endpoint**.
- Copy the **Endpoint** (for `.env` as `AZURE_OPENAI_ENDPOINT`).
- Copy a **Key** (for `.env` as `AZURE_OPENAI_API_KEY`).

### 4. (Optional) Use Azure AI Studio/Foundry

- Visit [Azure AI Studio](https://ai.azure.com/).
- Create a new project and workspace.
- Link your OpenAI deployment in the project’s settings.
- Use the “Deploy” section for API endpoint configuration if needed.

### 5. Configure Your Application

- Update your `.env` with the deployment name, endpoint, and API key.

---

## Usage

1. Enter a question about your SQL database in natural language.
2. See the generated SQL query and the AI’s answer.
3. Review and adjust the schema or prompts as needed for your environment.

---

## License

MIT License

---

**Need help?** Open an issue or discussion on GitHub!

---

> *Ready to copy & use. Update placeholder values in `.env` before running.*
