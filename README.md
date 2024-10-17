<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
</head>
<body>

<h1>Project Overview</h1>

<p>This repository contains a Python-based tool for dynamically benchmarking multiple medical data APIs and intelligently selecting the most optimal API based on response time, data quality, and error rate. The system is designed to streamline and optimize the process of querying medical APIs for information related to drugs, symptoms, and diseases.</p>

<h2>Features</h2>
<ul>
    <li><strong>API Benchmarking:</strong> The script sends requests to multiple medical APIs and measures their performance.</li>
    <li><strong>Smart API Selection:</strong> Automatically selects the best-performing API based on response time, data quality, and error rate.</li>
    <li><strong>Dynamic Query Handling:</strong> Takes a user-provided query (e.g., drug, symptom, or disease) and directs it to the most optimal API.</li>
    <li><strong>Error Handling:</strong> Gracefully handles network failures and API errors by calculating and incorporating error rates in the selection process.</li>
</ul>

<h2>APIs Used</h2>
<ul>
    <li><strong>Tavily API:</strong> For querying symptoms related to a specific medical term.</li>
    <li><strong>SerpAPI:</strong> Searches symptoms from general web sources.</li>
    <li><strong>OpenFDA API:</strong> Fetches drug-related event data from the FDA.</li>
</ul>

<h2>Installation</h2>

<ol>
    <li>Clone this repository to your local machine:
        <pre><code>git clone https://github.com/udayasriyedida/medical-api-benchmark.git</code></pre>
    </li>
    <li>Navigate to the project directory:
        <pre><code>cd medical-api-benchmark</code></pre>
    </li>
    <li>Install the required Python packages:
        <pre><code>pip install -r requirements.txt</code></pre>
        <p>The script requires the following Python libraries:</p>
        <ul>
            <li>requests</li>
            <li>pandas</li>
            <li>matplotlib</li>
        </ul>
    </li>
</ol>

<h2>Usage</h2>

<ol>
    <li>Open the script file (<code>api_benchmark.py</code>).</li>
    <li>Customize the API keys and URLs within the script by adding your personal API keys for the Tavily, SerpAPI, and OpenFDA APIs. Replace the placeholder keys in the <code>api_endpoints</code> dictionary.</li>
    <li>Run the script:
        <pre><code>python api_benchmark.py</code></pre>
    </li>
    <li>The script will:
        <ul>
            <li>Benchmark all the listed APIs based on response time, data quality, and error rate.</li>
            <li>Select the best-performing API.</li>
            <li>Call the selected API to fetch data for the provided query.</li>
        </ul>
    </li>
</ol>

<h2>Example</h2>

<pre><code># User input for the query (e.g., disease, symptom, or drug name)
query = "COVID-19"

# Example of expected output:
# The system will print a table showing each API's performance metrics:
#   API         | Response Time (s) | Data Quality | Error Rate
#   -------------------------------------------------------------
#   Tavily      | 0.45              | 4            | 0
#   SerpAPI     | 0.68              | 6            | 0
#   OpenFDA     | 1.23              | 3            | 0
#
# Based on the output, the script will select the API with the best combination of low response time, high data quality, and zero errors.
</code></pre>

<h2>Customization</h2>

<p>You can customize the script in several ways:</p>
<ul>
    <li><strong>Add more APIs:</strong> Simply extend the <code>api_endpoints</code> dictionary with new API URLs and modify the <code>benchmark_api</code> function to handle their responses.</li>
    <li><strong>Adjust performance criteria:</strong> You can tweak how APIs are ranked by modifying the <code>best_api</code> selection logic in the script. For example, you might weigh data quality more heavily than response time depending on your use case.</li>
</ul>

<h2>Error Handling</h2>

<p>The script has built-in error handling. If an API request fails (e.g., due to network issues or a bad API key), the API is assigned a higher error rate, and it will not be selected as the best API.</p>

<h2>Contributing</h2>

<p>Contributions are welcome! If you find a bug or have an idea for an enhancement, feel free to open an issue or submit a pull request.</p>

<ol>
    <li>Fork the repository</li>
    <li>Create your feature branch (<code>git checkout -b feature/YourFeature</code>)</li>
    <li>Commit your changes (<code>git commit -m 'Add some feature'</code>)</li>
    <li>Push to the branch (<code>git push origin feature/YourFeature</code>)</li>
    <li>Open a pull request</li>
</ol>

<h2>License</h2>

<p>This project is licensed under the MIT License – see the <a href="LICENSE">LICENSE</a> file for details.</p>

<h2>Acknowledgments</h2>

<ul>
    <li>APIs used: <a href="https://api.tavily.com/">Tavily API</a>, <a href="https://serpapi.com/">SerpAPI</a>, <a href="https://open.fda.gov/">OpenFDA API</a></li>
</ul>

</body>
</html>

