This is a simple Streamlit app that uses LangChain, Groq API, and Gemma-7B-IT model to summarize content from a YouTube video or a public website URL in about 300 words.

🔧 Features
-Enter any valid YouTube or website URL.
-Automatically detects and loads content using:
        YoutubeLoader for YouTube videos
        UnstructuredURLLoader for web pages
        Uses Groq-hosted LLMs (e.g., gemma-7b-it) for fast, high-quality summarization.
-User-friendly Streamlit interface.

Configuration
-You must enter your Groq API key in the sidebar to use the summarization model.
-Supported Groq models include gemma-7b-it and others available through your Groq account.

Notes
-Ensure the URL is publicly accessible and well-formatted.
-The app currently outputs a ~300-word summary of the content.
-The app supports basic error handling for invalid inputs and model issues.