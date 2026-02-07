# RAG-Tutorials

# RAG---Retrieval-Augmented-Generation

# Data ingestion
1. Install Dpendencies
```python
pip install langchain langchain-community pypdf python-docx pandas
```

2. Load TXT Files
```python
from langchain_community.document_loaders import TextLoader

loader = TextLoader("data/sample.txt", encoding="utf-8")
docs = loader.load()
print(docs)
print(docs[0].page_content)
```

3. Load PDF files
```python
from langchain_community.document_loaders import PyPDFLoader
# Use pymupdf for better output
loader = PyPDFLoader("data/sample.pdf")
docs = loader.load()

print(len(docs))           # number of pages
print(docs[0].page_content)
```

4. Load Word file
```python
from langchain_community.document_loaders import Docx2txtLoader

loader = Docx2txtLoader("data/sample.docx")
docs = loader.load()

print(docs[0].page_content)
```

5. Load CSV Files
```python
from langchain_community.document_loaders import CSVLoader

loader = CSVLoader(file_path="data/sample.csv")
docs = loader.load()

print(docs[0].page_content)
```

6. Load Directory Folder
```python
from langchain_community.document_loaders import DirectoryLoader, PyPDFLoader

loader = DirectoryLoader(
    "data/",
    glob="**/*.pdf",
    loader_cls=PyPDFLoader
)

docs = loader.load()
print(len(docs))
```
