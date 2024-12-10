README for sql-agent-plotter

sql-agent-plotter

A versatile AI-powered tool for SQL query generation, analysis, and visualization.

This project leverages advanced AI capabilities, powered by Ollama and LLMs like Llama, to simplify working with relational data. It integrates SQL generation, result interpretation, and dynamic plotting into a single, seamless workflow.

Features
	•	SQL Query Generation: Automatically generate SQL queries from natural language inputs using advanced AI models.
	•	Result Interpretation: Analyze and summarize SQL query results in a human-readable format with the context of the executed query.
	•	Dynamic Plotting: Automatically generate insightful plots based on query results with dynamic axis selection powered by Ollama.
	•	LLM Integration: Uses Ollama for intelligent axis selection, result summarization, and context-aware query processing.

Getting Started

Prerequisites
	1.	Python 3.8+
	2.	Install required libraries:

pip install sqlite3 pandas matplotlib requests


	3.	Access to the Ollama API and an active API endpoint.

Installation

Clone the repository:

git clone https://github.com/your-username/sql-agent-plotter.git
cd sql-agent-plotter

Usage
	1.	Initialize the SQL Agent:

from sql_agent_plotter import SQLCoderQueryGenerator

query_generator = SQLCoderQueryGenerator(
    db_path="path_to_your_database.db",
    model="llama-3.2",
    api_endpoint="http://api.ollama.ai"
)


	2.	Generate a Plot:

sql_query = "SELECT make_model, AVG(price) AS avg_price FROM cars GROUP BY make_model;"
results = [
    {"make_model": "Toyota Prius", "avg_price": 25000},
    {"make_model": "Honda Civic", "avg_price": 22000}
]

x_axis, y_axis = query_generator.suggest_plot_axes(results, sql_query)
plot_path = query_generator.plot_results(results, sql_query, x_axis=x_axis, y_axis=y_axis)
print(f"Plot saved at: {plot_path}")


	3.	Interpret Results:

summary = query_generator.interpret_result(results, sql_query)
print(summary)

License

This project is licensed under the MIT License.

Acknowledgments
	•	Ollama API: Used for advanced AI-driven suggestions and summarization.
	•	Matplotlib: For data visualization.
	•	SQLite3: For database interactions.

Feel free to enhance, extend, or modify this project to suit your needs. Contributions are welcome! 🚀