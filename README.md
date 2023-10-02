

# Chatbot with OpenAI and Google Search

This project demonstrates how to build a chatbot using the OpenAI GPT-3 model and integrate it with Google Search Results. The chatbot can answer questions and provide descriptions based on user queries.

## Prerequisites

Before running the code, make sure you have the following installed:

- Python 3.x
- Pip (Python package manager)

## Installation

Use the following commands to install the required Python packages:

```bash
pip install langchain
pip install openai
pip install google-search-results
```

## Usage

1. Set your OpenAI API key and Google Search API key:

   ```python
   my_open_key = "please enter OpenAI key"
   os.environ['SERPAPI_API_KEY'] = "your_google_api_key"
   ```

2. Initialize the OpenAI and Google Search agents:

   ```python
   from langchain.llms import OpenAI
   from langchain.agents import AgentType, load_tools, initialize_agent

   myllm = OpenAI(temperature=0, openai_api_key=my_open_key)

   mytools = load_tools(tool_names=["serpapi"])
   my_google_chain = initialize_agent(
       tools=mytools,
       llm=myllm,
       agent=AgentType.ZERO_SHOT_REACT_DESCRIPTION,
       verbose=True
   )
   ```

3. Run the chatbot:

   ```python
   x = input("Please enter your question: ")
   my_google_chain.run(x)
   ```

## Configuration

- `temperature`: You can adjust the temperature parameter when initializing the OpenAI model for different levels of creativity in responses.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- [OpenAI](https://openai.com) for the GPT-3 model.
- [Google Search Results API](https://serpapi.com/) for search results.

## Contributing

Contributions are welcome! If you have any suggestions or improvements, please open an issue or create a pull request.
---

Please replace `"please enter OpenAI key"` and `"your_google_api_key"` with your actual API keys in the code and update the contact email address. Additionally, consider adding more details about the project, such as usage examples and advanced configurations, if applicable.
