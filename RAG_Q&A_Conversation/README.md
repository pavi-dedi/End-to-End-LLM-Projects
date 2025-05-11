A conversational RAG with PDF uploads and chat history. The user can upload their pdfs and ask questions. Also keeps conversation history. 


Improvements that can be added:

-Only reads one file now: fix it with this to enable multiple files. 

        documents = []
        for idx, uploaded_file in enumerate(uploaded_files):
            temppdf = f"./temp_{idx}.pdf"
            with open(temppdf, "wb") as file:
                file.write(uploaded_file.getvalue())

- also answers when questions unrealted to the pdfs are asked. add a similarity score threshold, so that documents fetched with low similarity scores will not be used, and the answers will be 
  strict to the pdfs
  