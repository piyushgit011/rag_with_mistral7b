# Retrieval-Augmented Generation (RAG) chatbot using open-source tools and AWS services, such as LangChain, Hugging Face(Mistral 7b), FAISS, Amazon SageMaker, and Amazon TextTract.


We are working with PDF files in the Energy domain. Our first step involves leveraging Amazon TextTract to extract valuable information from these PDFs. Following the extraction, we break down the text into smaller, more manageable chunks. These chunks are then enriched using a Hugging Face feature extraction model before being organized and stored within a FAISS index for efficient retrieval.

To ensure a seamless workflow, we employ LangChain to orchestrate the entire process. With LangChain as our backbone, we query a Mistral Large Language Model (LLM) deployed on Amazon SageMaker. These queries include semantically relevant context retrieved from our FAISS index, enabling our chatbot to provide accurate and context-aware responses.

## Retrieval-Augmented Generation Architecture
![image](https://github.com/piyushgit011/rag_with_mistral7b/assets/96625965/ab2f5ead-ff25-4a9d-b1df-278a5e7f599d)

## 1.Deploy LLM on SageMaker
   - we have deployed mistarl 7b on aws sagemaker using the instance ml.g5.2xlarge as an endpoint.
    
## 2.Configure LLM in LangChain
   - we have made a class ContentHandler() which is handling all the prompts imput , output and the parameters we are going to inference on the endpoint.
    
## 3.Zero-shot example
   - example prompt used to inference on a sample question to test the llm endpoint is working properly.

## 4.RAG example with PDF files
   - now, importing the text_splitter,embeddings, vectorstores, document_loaders and chains for retrieval of the information from the embeddings.
   - then, i have uploaded all the pdfs in the s3 bucket.

## 5.Analyze documents with Amazon Textract and split them in chunks
   - now, using AmazonTextractPDFLoader and RecursiveCharacterTextSplitter we will split the texts and load into chunks.

## 6.Embed document chunks and store them in FAISS
   - now using a opensource pre trained embedding model to make the embeddings of the chunks and store it in the name "faiss_index".

## 7.Shortcut : load existing embedding database
   - load the stored faiss_index using FAISS.load_local

## 8.Configure RAG chain
   - now, retrieve all the embeddings.
   - using RetrievalQA we will use the embeddings to query and using the template for our custom prompt.
## 9.Ask our question again
   - now, you can ask different questions from the pdf files.
## 10.Delete endpoint and model
   - After using it successfully i have deleted the endpoint on the aws sagemaker.




- LangChain: https://www.langchain.com/
- FAISS: https://github.com/facebookresearch/f...
- Embedding leaderboard: https://huggingface.co/spaces/mteb/le...
- Embedding model: https://huggingface.co/BAAI/bge-small...
- LLM: https://huggingface.co/mistralai/Mist...
