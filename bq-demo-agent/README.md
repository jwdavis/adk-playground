This is a very simple ADK agent demo.

The agent takes requests from the user and uses the built-in BigQuery tool to answer BigQuery-related questions.

## Setup Instructions

1. **Create a virtual environment**  
   ```bash
   python3 -m venv venv
   ```

2. **Activate the virtual environment**  
   - On Linux/Mac:
     ```bash
     source venv/bin/activate
     ```
   - On Windows:
     ```cmd
     venv\Scripts\activate
     ```

3. **Install google-adk**  
   ```bash
   pip install google-adk
   ```

## Running the Agent

4. **Start the agent with ADK web**  
   ```bash
   adk web
   ```

5. **Open your web browser**  
   - Go to the URL provided in the terminal (usually http://localhost:8000).
   - Select the **bq-demo-agent** from the drop-down list.

## Test Queries

Once the agent is running, you can test it with various BigQuery-related questions:

- **List datasets in a project:**
  ```
  What datasets are available in project [your-project-id]?
  ```

- **List tables in a dataset:**
  ```
  What tables are in the dataset [dataset-name]?
  ```

- **Get table schema:**
  ```
  What is the schema of table [table-name]?
  ```

- **Get table info:**
  ```
  How many rows are in table [table-name]?
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
  Write a query to find the most common values in column [column-name]. Run the query and show the results. Show me the query text as well.
  ```

The agent will use BigQuery tools to execute these requests and provide you with results, query suggestions, and data analysis.

 ## Show interesting context

 1. Show one or more traces,  highlighting how long each call takes.
 2.  Show one or More events. Show the visual representation of the agent, calling a tool function along with the JSON payload being sent to the tool step through the steps of the event, showing the back-and-forth flow of information.