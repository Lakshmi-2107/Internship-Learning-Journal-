# 🧪 Week 3 – Prompt Experiments
## Structured Prompt Engineering & Testing

This file documents prompt experiments and observations.

---

#  Experiment 1 – Simple Prompt

Prompt:
Explain transformers in simple words.

Observation:
- Output was general
- Not structured
- Lacked depth

Lesson:
Unstructured prompts give broad answers.

---

#  Experiment 2 – Structured JSON Prompt

Prompt:
Explain transformers in simple words.
Return output in JSON format with:
{
  "definition": "",
  "key_components": [],
  "real_world_use": ""
}

Observation:
- Structured output
- Easy to parse
- More organized

Lesson:
Specifying format improves clarity.

---

#  Experiment 3 – Schema-Based Extraction

Input:
"Ravi purchased 5 books costing 200 rupees."

Prompt:
Extract structured data in JSON.

Output:
{
  "name": "Ravi",
  "items": 5,
  "amount": 200
}

Lesson:
LLMs are powerful for information extraction.

---

#  Experiment 4 – Sentiment Analysis

Prompt:
Classify sentiment as Positive, Negative or Neutral.

Text:
"I love this product."

Observation:
Consistent and fast classification.

Lesson:
LLMs work well for classification tasks.

---

#  Experiment 5 – RAG Concept Simulation

Prompt:
Answer based only on provided context.

Observation:
Grounded answers are more reliable.

Lesson:
Providing context reduces hallucination.

---

#  Experiment 6 – Cost Efficiency Test

Compared:

1. Long descriptive prompt
2. Short structured prompt

Result:
Short structured prompts used fewer tokens.

Lesson:
Prompt optimization reduces cost.

---

#  Experiment 7 – Vision Model Test

Prompt:
Describe what is happening in this image.

Observation:
- Object detection
- Scene description
- Context inference

Lesson:
Vision models expand AI capabilities significantly.

---

#  Conclusion

From these experiments, I learned:

- Prompt clarity matters
- Format improves consistency
- Structured outputs are powerful
- Context improves reliability
- Evaluation is necessary

---

 Session 2 Prompt Experiments
## Embeddings, RAG & Retrieval Testing Log

This document records practical prompt experiments performed while implementing embeddings and Retrieval-Augmented Generation (RAG).

The goal was to analyze how different prompt structures and retrieval strategies affect output quality, cost, and reliability.

---

#  Experiment 1 – Direct Question (No Retrieval)

Prompt:
"What is TypeScript?"

Method:
- Directly asked GPT without providing documentation context.

Observation:
- Answer was correct but generic.
- Not based on specific documentation.
- Risk of hallucination if question becomes technical.

Conclusion:
Direct prompting works for common knowledge but lacks grounding.

---

#  Experiment 2 – Context-Based Prompt (Manual Context)

Prompt:
"Answer the question using only the context below:
[Documentation text here]
Question: What is TypeScript?"

Observation:
- Response was more accurate.
- Referenced documentation.
- Reduced hallucination.

Conclusion:
Providing context improves factual reliability.

---

#  Experiment 3 – RAG with Top-5 Retrieval

Process:
1. Convert user query to embedding.
2. Retrieve Top-5 most similar chunks.
3. Pass retrieved chunks + question to GPT.

Observation:
- Answer was detailed.
- Referenced correct documentation sections.
- More technically precise.

Conclusion:
RAG significantly improves contextual accuracy.

---

#  Experiment 4 – Changing Top-K Value

Tested:

- Top-3 retrieval
- Top-5 retrieval
- Top-10 retrieval

Observation:

Top-3:
- Faster
- Sometimes missed details

Top-5:
- Balanced
- Good coverage

Top-10:
- More context
- Higher token cost
- Slightly slower

Conclusion:
Top-5 gave the best balance between cost and completeness.

---

#  Experiment 5 – Long Query vs Short Query

Short Query:
"What is TypeScript?"

Long Query:
"Explain TypeScript including features, purpose, and usage in web development."

Observation:
- Long query produced more detailed output.
- Increased token usage.
- Higher cost.

Conclusion:
Query clarity improves response depth but increases token consumption.

---

#  Experiment 6 – Similarity Threshold Testing

Tested cosine similarity scores between:

- "apple and orange"
- "apple and lightning"

Observation:
- Fruit comparison gave higher similarity.
- Unrelated terms gave lower score.

Conclusion:
Cosine similarity correctly reflects conceptual closeness.

---

#  Experiment 7 – Multimodal Similarity

Compared:

- "cat" image embedding with "cat" text embedding
- "cat" image embedding with "box" text embedding

Observation:
- High similarity for matching concepts.
- Low similarity for unrelated concepts.

Conclusion:
Multimodal embeddings allow cross-format comparison effectively.

---

#  Experiment 8 – Chunk Size Impact

Tested:

- Large chunk size (~4000 tokens)
- Medium chunk size (~1500 tokens)
- Small chunk size (~500 tokens)

Observation:

Large:
- Fewer chunks
- Broader context
- Slightly less precision

Medium:
- Balanced precision
- Good retrieval quality

Small:
- Highly precise
- Sometimes fragmented meaning

Conclusion:
Medium-sized chunks worked best for documentation retrieval.

---

#  Experiment 9 – Structured Output Format

Prompt:
"Answer in JSON format with:
{
  "definition": "",
  "key_features": [],
  "examples": []
}"

Observation:
- Clean structured output
- Easier to parse programmatically
- Reduced ambiguity

Conclusion:
Structured prompts improve integration into applications.

---

#  Experiment 10 – Token Cost Awareness

Compared:

- Sending full documentation to GPT
- Using RAG with selective retrieval

Observation:
- Full documentation → High token cost
- RAG → Lower cost + faster response

Conclusion:
RAG is significantly more cost-efficient for large documents.

---

#  Overall Insights

From these experiments, I learned:

- Retrieval improves reliability
- Cosine similarity powers semantic search
- Chunk size affects precision
- Top-K must be balanced
- Structured prompts enhance usability
- RAG reduces hallucination and cost
- Multimodal embeddings expand application scope

---


