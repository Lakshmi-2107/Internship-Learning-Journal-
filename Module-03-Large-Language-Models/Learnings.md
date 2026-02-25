# 📚 Week 3 – Session 1 Learnings
## Advanced LLM Systems & Intelligent Applications

This session expanded my understanding of how modern AI systems actually function beyond simple prompting.

---

#  Key Learnings

##  Understanding LLM Foundations

I learned that LLMs:

- Are prediction engines
- Use transformers
- Process tokens
- Have context limits

They do not "understand" like humans.

---

##  Importance of Token Efficiency

I now understand:

- Why shorter prompts save money
- How input + output tokens affect cost
- Why structured prompts are efficient

---

##  Embeddings & Similarity Search

This was a major concept.

I learned:

- Embeddings convert data into vectors
- Similar meaning → closer vectors
- Enables semantic search
- Works beyond keywords

This is powerful for building smart search systems.

---

##  Retrieval Augmented Generation (RAG)

RAG solves hallucination issues.

Instead of trusting the model blindly:

- Retrieve documents
- Feed real data
- Generate grounded answers

This improves reliability.

---

##  Hybrid Search Systems

Combining:

- Keyword matching
- Vector similarity

gives both accuracy and contextual intelligence.

This is more powerful than either method alone.

---

##  Vision Models

I learned LLMs can:

- Analyze images
- Process videos
- Extract information from visuals

This expands AI beyond text-only tasks.

---

##  Structured Output & Schemas

Using schemas ensures:

- Consistent responses
- Clean JSON output
- Easier integration with apps

This is critical for production systems.

---

##  Function Calling & Agents

I understood how LLMs:

- Trigger functions
- Use tools
- Automate workflows

This moves from chatbots to intelligent systems.

---

##  Evaluation & Testing

AI systems must be tested.

Learned:

- Create prompt test cases
- Compare models
- Check cost and speed
- Use regression testing

Testing is essential for scalable AI applications.

---

#  Overall Growth

Before this session:

 I saw LLMs as simple chat tools  

After this session:

 I understand how to build structured, reliable AI systems  

Now I see how AI integrates into real-world applications.

---


# Session 2 Learnings  
## Practical Embeddings & RAG Systems

This session strengthened my understanding of how embeddings and retrieval systems power modern AI applications.

---

# What I Learned

##  Embeddings as Meaning Representation

I learned that embeddings:

- Convert text into vectors
- Capture semantic meaning
- Enable similarity comparison

They are foundational for AI search systems.

---

##  Cosine Similarity

I now understand:

- How similarity is calculated
- Why normalization matters
- How related concepts score higher

Mathematics supports semantic intelligence.

---

##  Multimodal Search

AI can compare:

- Text with images
- Image with image
- Text with text

This expands search capabilities beyond words.

---

##  Chunking Strategy

Large documents must be:

- Split into manageable parts
- Indexed separately
- Stored with unique IDs

Chunking makes RAG scalable.

---

##  RAG Workflow

Instead of asking GPT blindly:

- Retrieve relevant context
- Pass only useful data
- Generate grounded answers

This improves reliability and reduces cost.

---

##  Efficient API Usage

I learned:

- How to store embeddings once
- Avoid recomputing
- Reduce token usage
- Improve speed

Efficiency is key in real projects.

---

##  Deployment Awareness

Real-world systems require:

- Public repositories
- Correct URLs
- Valid tokens
- Environment configuration

Debugging skills are essential.

---

#  Growth Reflection

Before this session:

 I only knew basic embedding concepts.

After this session:

 I can implement a full RAG pipeline with chunking and retrieval.

This session connected theory with real implementation.

---
#  Session 4 

---

##  Understanding Word Embeddings

In this session, I clearly understood how words are converted into numerical vectors.

I generated embeddings for:
- cat
- dog
- cheetah
- rat

After comparing them using cosine similarity, I observed:

- Cat and cheetah had the highest similarity.
- Cat and dog also showed high similarity.
- Rat had lower similarity compared to the other animals.

This helped me understand that embeddings truly capture semantic meaning mathematically.

---

##  Applying Cosine Similarity

I learned how cosine similarity measures the angle between vectors instead of physical distance.

Now I understand:
- Higher cosine similarity → more related meanings
- Lower cosine similarity → less related words

This concept is very important for semantic search and recommendation systems.

---

##  Making API Calls Using httpx

I implemented API calls using the httpx library.

I practiced:
- Sending POST requests
- Passing headers (Authorization, Content-Type)
- Sending JSON body
- Parsing API responses

This helped me understand how AI models are integrated into applications.

---

##  Building a Chatbot with Memory

I built a chatbot that maintains conversation history.

By passing:
- user messages
- assistant responses

in a structured list format, the model was able to remember previous context.

This helped me understand how conversational AI works internally.

---

##  Base64 Encoding and Decoding

I implemented practical Base64 encoding and decoding.

Process I performed:
1. Converted image into Base64 string.
2. Sent Base64 text to the API.
3. Decoded Base64 back into image format.

Now I understand how images are transmitted through APIs since APIs work with text data.

---

##  Function Calling with Images

One of the most important learnings was using function calling with images.

I:
- Converted product image into Base64
- Sent it to the model
- Defined a function schema
- Received structured JSON output

The model extracted:
- product_name
- manufactured_date
- expiry_date

This showed me how AI can return structured machine-readable data instead of normal text.

This is useful in:
- Product scanning systems
- Invoice data extraction
- Automated workflows

---

##  Overall Understanding

This session helped me connect:

- Vector mathematics
- API communication
- Chat-based AI systems
- Image processing
- Structured data extraction

It strengthened my practical understanding of how modern AI applications are built.

---
## Learnings Completed!!🎉