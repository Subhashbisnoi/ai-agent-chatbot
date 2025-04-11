# LangGraph AI Agent  

## Overview  
LangGraph AI Agent is a chatbot application that allows users to interact with AI models from **Groq** and **OpenAI**. The system supports **web search capabilities** and integrates **FastAPI** for backend communication with LangChain-based AI agents.  

## Features  
- **Supports multiple AI models** (Groq & OpenAI)  
- **Web search integration** using Tavily API  
- **FastAPI backend** for handling AI agent requests  
- **Streamlit frontend** for user-friendly interaction  
- **Custom system prompts** to define agent behavior  

## Project Structure  
```
/langgraph-ai-agent
│── frontend.py          # Streamlit UI for user interaction
│── backend.py           # FastAPI server handling AI agent requests
│── ai_agent.py          # AI agent implementation using LangChain
│── requirements.txt     # Required dependencies
│── .env                 # API keys for OpenAI, Groq, and Tavily
│── README.md            # Project documentation
```


## Setup Instructions  

### 1. Install Dependencies  
Ensure you have Python 3.8+ installed. Clone the repository and install dependencies:  
```sh
pip install -r requirements.txt
```

### 2. Set Up Environment Variables  
Create a `.env` file and add the following API keys:  
```
GROQ_API_KEY=your_groq_api_key
TAVILY_API_KEY=your_tavily_api_key
OPENAI_API_KEY=your_openai_api_key
```

### 3. Run the Backend Server  
Start the FastAPI server:  
```sh
python backend.py
```
The API will be available at `http://127.0.0.1:9999/chat`.

### 4. Run the Frontend  
Launch the Streamlit UI:  
```sh
streamlit run frontend.py
```
This will open a web-based chatbot interface.

## Usage  
1. Choose an AI model provider (Groq or OpenAI).  
2. Select the specific model from the dropdown.  
3. Define a system prompt to customize chatbot behavior.  
4. Enable or disable web search as needed.  
5. Enter a user query and click **Ask Agent!**  

The response from the AI agent will be displayed on the UI.

## API Details  

### Endpoint: `/chat`  
- **Method:** `POST`  
- **Payload:**  
```json
{
  "model_name": "gpt-4o-mini",
  "model_provider": "OpenAI",
  "system_prompt": "You are a helpful AI assistant.",
  "messages": ["What is AI?"],
  "allow_search": false
}
```

- **Response Example:**  
```json
{
  "response": "AI stands for artificial intelligence..."
}
```

## Future Enhancements  
- Add support for more AI models  
- Improve frontend UI/UX  
- Enhance error handling and logging  

## License  
This project is licensed under the **MIT License**.
