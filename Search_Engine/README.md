This is an interactive chatbot web app built using Streamlit and LangChain, powered by the Groq API and the Llama3-8b-8192 model. The chatbot can search across multiple sources including Wikipedia, arXiv, and the web via DuckDuckGo to provide factual, sourced answers to your queries.


🚀 Features
 -Chat interface built using Streamlit
 -Integrates multiple search tools:
    Wikipedia
    arXiv (academic papers)
    DuckDuckGo (web search)

-Agent type 
        This Uses LangChain's Zero-Shot ReAct agent*****: LLM attitude is "I should think, then act."  Likely use tools
        If CHAT_ZERO_SHOT_REACT_DESCRIPTION was used : another agent type : LLM attitude is "I’ll chat, but I can look things up if I need." Tools used only if needed 
        Custom agent with filter/router  :  LLM attitude is "Only use tools when asked or unsure."  Will use tools only when truly needed

-Powered by Groq Llama3 for high-speed inference
-Session memory via st.session_state
-Live agent reasoning visualization via StreamlitCallbackHandler: allows real-time feedback on the agent's thoughts/actions.
-The app does not persist chat history across sessions (stateless). Although st.session_state is used to maintain chat history within a single active session (i.e., while the app is open), that history is not stored permanently in a database or file

***** This may lean into tools even when not required 

🛠️ How to Get an LLM That Doesn’t Overuse Tools
✅ Option 1: Don’t use an agent
Just call the LLM directly:

python
Copy
Edit
response = llm.invoke("What is 2 + 8?")
No tools involved. Fast, direct answer.

✅ Option 2: Use a custom logic router
Write your own logic:

python
Copy
Edit
if is_simple_question(user_input):
    answer = llm.invoke(user_input)
else:
    answer = agent.run(user_input)
✅ Option 3: Change the agent prompt
Modify the ReAct prompt to say something like:

"Only use tools if you're unsure. If the question is simple or well-known, answer directly."
LangChain lets you customize the prompt used by the agent.