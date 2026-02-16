# 📘 Week 3 – Session 1
## Module 3 – Advanced API Interaction & LLM Systems

This session introduced advanced concepts for working with Large Language Models (LLMs), embeddings, vector databases, retrieval systems, vision models, and structured prompt design. The focus was on building intelligent applications using APIs efficiently and safely.

---

#  1. Introduction to Module 3

Module 3 focuses on:

- Interacting with specialized APIs
- Generating text using LLMs
- Processing structured and unstructured data
- Building intelligent retrieval systems

The goal is to move from simple API usage to building smart AI-powered applications.

---

#  2. API Keys & Proxy Usage

To access models, an API key is required.

Important points:

- Obtain API key from aipipe.org
- Keep keys secure
- Never expose keys publicly
- Use environment variables

Common mistakes:

- Hardcoding keys
- Using wrong proxy endpoints
- Exceeding rate limits

---

#  3. How Large Language Models Work

LLMs are:

- Not conscious
- Not intelligent like humans
- Mathematical prediction systems

They are built using:

- Transformer architecture
- Neural networks
- Massive training datasets

---

#  4. Tokens & Processing

Text is divided into smaller units called tokens.

Important:

- Tokens ≠ words
- Billing depends on token usage
- Input + Output tokens both count

Example:
"Hello world" → broken into smaller token pieces.

Efficient prompts reduce cost.

---

#  5. Self-Attention Mechanism

Self-attention helps models:

- Understand relationships between words
- Identify context
- Assign importance dynamically

It allows the model to connect distant words in a sentence.

---

#  6. Context Limitations

LLMs have limited memory per request.

Limitations:

- Cannot remember everything forever
- Context window size matters
- Long inputs may get truncated

This leads to the need for external retrieval systems.

---

#  7. Embeddings

Embeddings convert:

- Text
- Images
- Audio

into numerical vectors.

Purpose:

- Measure similarity
- Compare content
- Cluster related information

Multimodal embeddings allow:

- Image + text comparison
- Cross-modal search

---

#  8. Topic Modeling

Using embeddings, we can:

- Group similar documents
- Detect themes
- Cluster related content

Unlike keyword search, embeddings understand meaning.

---

#  9. Vector Databases

Vector databases store embeddings.

They allow:

- Fast similarity search
- Nearest neighbor retrieval
- Context matching

Used in AI applications for:

- Search engines
- Recommendation systems
- RAG systems

---

#  10. Retrieval Augmented Generation (RAG)

RAG improves LLM responses by:

1. Retrieving relevant documents
2. Feeding them into the model
3. Generating grounded answers

Benefits:

- Reduces hallucination
- Improves accuracy
- Uses external knowledge

---

#  11. Hybrid RAG

Hybrid RAG combines:

- Keyword search
- Vector similarity search

This ensures:

- Precision (exact matches)
- Contextual relevance

Tools like Typesense support hybrid retrieval.

---

#  12. Base64 Encoding

Binary data cannot be directly processed by LLMs.

Base64 converts:

- Images
- Audio
- Files

into text format.

Why needed?

- API compatibility
- Text-based transmission

---

# 13. Vision Models

Vision-capable LLMs can:

- Analyze images
- Extract text
- Identify objects
- Process video frames

Applications:

- Security monitoring
- Workplace safety
- Exam proctoring
- Surveillance analysis

Videos are processed frame-by-frame.

---

#  14. Prompt Engineering

Prompt structure directly affects output quality.

Best practices:

- Be clear and specific
- Define output format
- Use JSON or XML structure
- Provide examples
- Document results

Well-designed prompts reduce errors and cost.

---

#  15. Sentiment Analysis

LLMs can classify text into:

- Positive
- Negative
- Neutral

Applications:

- Market sentiment
- Election analysis
- Social media tracking
- Brand monitoring

---

#  16. Text Extraction

LLMs can convert unstructured text into structured JSON.

Example:

Input:
"John bought 3 items for $50"

Output:
{
  "name": "John",
  "items": 3,
  "amount": 50
}

This enables automation and database storage.

---

#  17. Schemas

Schemas define structured outputs.

Benefits:

- Consistency
- Easy integration
- Reliable automation
- Reduced ambiguity

Schemas guide the model’s response format.

---

#  18. Function Calling in Applications

LLMs can call predefined functions.

Example:

User: "Book a flight"
LLM → calls booking function

This allows:

- Intelligent automation
- Real-time actions
- Smart assistants

---

#  19. Agents & Tools

Agents use:

- Tools
- APIs
- Functions

to complete tasks.

They can:

- Decide which tool to use
- Chain multiple actions
- Execute workflows

Agents enable advanced AI systems.

---

#  20. LLM Evaluation & Testing

Testing ensures:

- Accuracy
- Cost efficiency
- Speed
- Stability

Tools like prompt-based testing frameworks allow:

- YAML-based test cases
- Assertions
- Regression testing
- Model comparison

Evaluation prevents silent failures.

---

#  Session 2  
## Embeddings, Multimodal Systems & RAG Implementation

This session focused on implementing embeddings, multimodal embeddings, vector databases, chunking strategies, and Retrieval-Augmented Generation (RAG). The emphasis was practical, demonstrating how these concepts are applied in Project 1.

---

#  1. Overview of Session

This session covered:

- Embeddings
- Multimodal embeddings
- Vector databases
- Chunking techniques
- Retrieval-Augmented Generation (RAG)
- Deployment troubleshooting

The session was code-heavy and implementation-focused.

---

#  2. Understanding Embeddings

Embeddings are numerical vector representations of data.

They:

- Represent text in multi-dimensional space
- Capture semantic meaning
- Enable similarity comparison

Embeddings are generally:

- Cheaper than chat-based models
- Faster for similarity tasks

---

#  3. Sentence Transformers

Local embedding models can be used.

Process:

- Download model
- Generate vector representation
- Produce fixed-size vectors (e.g., 364 dimensions)

This avoids API costs but requires local compute.

---

#  4. OpenAI Embeddings API

Embeddings can also be generated via API.

Model example:
- `text-embedding-3-small`

Workflow:

1. Send text to embedding endpoint
2. Receive vector output
3. Store vector for similarity search

HTTP libraries like `httpx` are used to send requests.

---

#  5. Cosine Similarity

Cosine similarity measures how similar two vectors are.

Formula idea:

- Compute dot product
- Normalize values
- Output between 0 and 1

Higher value → more similar.

Example:

- "apple and orange" vs "apple and lightning"
- Similar fruits → higher score
- Unrelated terms → lower score

This enables semantic comparison.

---

#  6. Managing API Keys

API keys should be stored securely.

Methods:

Temporary:
```
export API_KEY=your_key
```

Permanent:
- Add to `.bashrc`

This ensures availability across sessions.

---

#  7. Multimodal Embeddings

Multimodal embeddings map:

- Text
- Images

into the same vector space.

This allows:

- Comparing images with text
- Matching content across formats
- Cross-modal similarity search

---

#  8. Using Nomic AI

Nomic AI provides multimodal embedding APIs.

Steps:

1. Create account
2. Generate API key
3. Send image/text
4. Receive embedding vector

Practical Example:

- "cat" image vs "cat" text → high similarity
- "cat" image vs "box" text → low similarity

Useful for:

- Image tagging
- Visual search
- Project 1 discourse Q&A

---

#  9. Vector Databases

Vector databases store embeddings efficiently.

Purpose:

- Fast similarity retrieval
- Nearest-neighbor search
- Scalable embedding storage

Used in:

- Search systems
- Recommendation engines
- RAG pipelines

---

#  10. Chunking Large Documents

LLMs have token limits.

Solution: Chunking

Chunking involves:

- Splitting large documents
- Keeping chunks under token limits
- Assigning unique IDs

Example:

- Clone documentation repository
- Split markdown files
- Create 4096-token chunks
- Generate embeddings per chunk

This prepares data for retrieval.

---

#  11. Retrieval-Augmented Generation (RAG)

RAG workflow:

1. User asks question
2. Generate embedding of question
3. Compare with stored chunk embeddings
4. Retrieve Top-K relevant chunks
5. Send chunks + question to GPT
6. Generate contextual response

Top-K example:

- Retrieve top 5 similar chunks

Benefits:

- Reduces hallucination
- Improves accuracy
- Cost-efficient (reuse embeddings)

---

#  12. Example – Asking a Question

Query:
"What is TypeScript?"

Process:

- Compute query embedding
- Find similar documentation chunks
- Pass relevant chunks to GPT
- Generate detailed answer

Only relevant context is sent to model.

---

#  13. Deployment Troubleshooting

Common issues:

- Repository not public
- Incorrect deployment URL
- Expired API tokens
- Authentication errors

Important:

- Verify environment variables
- Check public access
- Complete time-sensitive questions last

---

#  14. Project 1 Relevance

This session is critical for Project 1:

- Embedding storage
- Chunk-based retrieval
- Multimodal comparison
- RAG implementation
- Efficient API usage

---
