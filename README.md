# AI-Engineer-Level-1
Technical Assessment

 Tool / Library                                Purpose                                     
 --------------------------------------------  ------------------------------------------- 
 **Python 3.8+**                               Programming language                        
 **FAISS**                                     Fast similarity search (vector DB)          
 **Sentence Transformers**                     To embed Bangla/English text into vectors   
 **paraphrase-multilingual-MiniLM-L12-v2**     Embedding model supporting Bangla & English 
 **Pickle**                                    Saving/loading original chunks              
 **NumPy**                                     Vector math & array processing              
 **PyMuPDF (fitz)**                            For extracting text from PDF         

 --------------------------------------------  ------------------------------------------- 

1.Text Extraction Method :
Library Used: PyMuPDF (fitz)
Why: It preserves formatting well and handles Bangla text better than some alternatives.
Challenges: Minor issues with line breaks and some inconsistent spacing across pages.

2.Chunking Strategy:
Strategy: Paragraph-based chunking
Why it Works: Paragraphs are semantically coherent units and retain context better than sentence or character-based chunks. This improves the quality of the matching when a query is made.

3.Embedding Model
Model Used: paraphrase-multilingual-MiniLM-L12-v2 from HuggingFace
Why Chosen: It supports Bangla and provides high-quality multilingual sentence embeddings, which is essential for semantic understanding.
Strength: Captures contextual meaning beyond individual words (semantic embedding).

4.Similarity Search and Retrieval:
Tool Used: FAISS (Facebook AI Similarity Search)
Comparison Method: Cosine similarity (via FAISS index)
Why This Setup: FAISS provides efficient and fast similarity search on high-dimensional vectors, making it ideal for real-time question answering systems.

6.Meaningful Comparisons:
Ensuring Relevance: Both the user query and document chunks are embedded using the same model, which ensures they're in the same vector space.
Handling Vague Queries: If the query lacks detail, the system might return less relevant results. This can be improved by:
Asking clarifying questions, Using larger or better-prepared chunks, Incorporating a reranking step using a language model.

7.Result Relevance and Future Improvements:
Current Result Quality: Generally relevant due to meaningful chunking and semantic embeddings.
Possible Improvements:
Better chunking (e.g., combining short paragraphs)
Using larger and more powerful models like bge-m3 or Instructor.
Expanding the document database.

