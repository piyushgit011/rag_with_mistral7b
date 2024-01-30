# Retrieval-Augmented Generation (RAG) chatbot using open-source tools and AWS services, such as LangChain, Hugging Face(Mistral 7b), FAISS, Amazon SageMaker, and Amazon TextTract.


We begin by working with PDF files in the Energy domain. Our first step involves leveraging Amazon TextTract to extract valuable information from these PDFs. Following the extraction, we break down the text into smaller, more manageable chunks. These chunks are then enriched using a Hugging Face feature extraction model before being organized and stored within a FAISS index for efficient retrieval.

To ensure a seamless workflow, we employ LangChain to orchestrate the entire process. With LangChain as our backbone, we query a Mistral Large Language Model (LLM) deployed on Amazon SageMaker. These queries include semantically relevant context retrieved from our FAISS index, enabling our chatbot to provide accurate and context-aware responses.


- LangChain: https://www.langchain.com/
- FAISS: https://github.com/facebookresearch/f...
- Embedding leaderboard: https://huggingface.co/spaces/mteb/le...
- Embedding model: https://huggingface.co/BAAI/bge-small...
- LLM: https://huggingface.co/mistralai/Mist...

![image](https://github.com/piyushgit011/rag_with_mistral7b/assets/96625965/ab2f5ead-ff25-4a9d-b1df-278a5e7f599d)
