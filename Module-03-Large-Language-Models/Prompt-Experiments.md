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

