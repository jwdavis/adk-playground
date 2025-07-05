This is a very simple ADK agent demo.

The agent takes requests from the user and uses the built-in BigQuery tool to answer BigQuery-related questions.

## Setup Instructions

1. **Run the following bash commands**
   ```bash
   git clone https://github.com/jwdavis/adk-playground.git
   cd adk-playground
   python3 -m venv .venv
   source .venv/bin/activate
   pip install -r requirements.txt
   ```

2. **Generate a `.env` file** in the current directory with the following contents (replace the placeholders with appropriate values):
    ```bash
    cat <<EOF > .env
    GOOGLE_GENAI_USE_VERTEXAI=TRUE
    GOOGLE_CLOUD_PROJECT=[project-id]
    GOOGLE_CLOUD_LOCATION=[region]
    EOF
    ```

## Connect to the ADK Web UI

1. **Start the with ADK web UI**  
   ```bash
   adk web
   ```

2. **Open your web browser**  
   - Go to the URL provided in the terminal (usually http://localhost:8000).
     - Though if you are using Cloud Shell, you will use the preview mechanism after setting the port to `8000`).
   - Select the **bq-demo-agent** from the drop-down list.

## Demo the agent

1. Once the agent is running, you can test it with various BigQuery-related questions:

   - **List datasets in a project:**
     ```
     What datasets are available in project [project]?
     ```

   - **List tables in a dataset:**
     ```
     What tables are in the dataset [dataset]?
     ```

   - **Get table schema:**
     ```
     What is the schema of table [table]?
     ```

   - **Get table info:**
     ```
     How many rows are in table [table]?
     ```

   - **Get sample data:**
     ```
     When was this table last modified?
     ```

   - **Run a specific query:**
     ```
     Run this query on the last table we discussed: SELECT COUNT(*) as total_rows FROM [table]
     ```

   - **Complex analysis:**
     ```
     Write a query to find the most common values in column [column]. Run the query and show the results. Show me the query text as well.
     ```

    The agent will use BigQuery tools to execute these requests and provide you with results, query suggestions, and data analysis.

 2. **Show interesting context**
    1. Show one or more traces,  highlighting how long each call takes.
    2.  Show one or More events. Show the visual representation of the agent, calling a tool function along with the JSON payload being sent to the tool step through the steps of the event, showing the back-and-forth flow of information.