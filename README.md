# Gemini Chatbot (LangChain + Streamlit)

A small conversational chatbot built with **LangChain** and **Streamlit**. It keeps conversation memory across turns and calls Google's Gemini model through `langchain-google-genai`. You paste your own API key into the sidebar; nothing is stored.

## How it works

- `ChatGoogleGenerativeAI` is the LLM.
- `ConversationBufferMemory` + `ConversationChain` give the bot multi-turn memory.
- Streamlit's `session_state` holds the chat history, and `st.chat_message` / `st.chat_input` render the UI.

## Run it

```bash
python -m venv .venv && source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r requirements.txt
streamlit run app.py
```

Then choose **Gemini-Pro** in the dropdown and enter a [Google AI Studio](https://aistudio.google.com/) API key in the sidebar.

## Known limitations

This is a 2023-era exploration project and I've left it as a snapshot rather than rewriting it:

- Only the Gemini option works. The other models in the dropdown are placeholders ("coming soon").
- The code targets the legacy LangChain 0.1 API, so versions are pinned in `requirements.txt`. The dependencies import cleanly together, but I haven't re-tested a live Gemini call recently.
- The hard-coded `gemini-pro` model name may be retired; if so, change the `model=` argument in `app.py` to a current Gemini model.

## License

MIT, see [LICENSE](LICENSE).
