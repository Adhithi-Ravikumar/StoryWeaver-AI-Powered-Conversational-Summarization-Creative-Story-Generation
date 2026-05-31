# StoryWeaver: AI-Powered Conversational Summarization & Creative Story Generation

Transform everyday conversations into engaging, mood-driven stories using state-of-the-art transformer models.

## Overview

StoryWeaver is an NLP application that converts chat conversations into creative short stories through a two-stage AI pipeline:

1. **Conversation Summarization** using a fine-tuned BART model.
2. **Story Generation** using FLAN-T5 with mood-specific prompting.

The system extracts the essence of multi-speaker dialogues and transforms them into coherent narratives across different genres such as:

- ❤️ Romance
- 🎭 Drama
- 😂 Comedy
- 🔍 Thriller
- ✨ Inspirational

Built with Hugging Face Transformers, PyTorch, and Gradio, StoryWeaver provides an interactive interface for real-time conversation-to-story transformation.

---

## Features

- Conversation summarization using fine-tuned BART
- Creative story generation using FLAN-T5
- Mood-based storytelling
- Multi-speaker dialogue processing
- Text cleaning and repetition reduction
- Emotion enhancement for generated stories
- Interactive Gradio web interface
- Real-time story generation

---

## System Architecture

```text
User Conversation
        │
        ▼
Data Preprocessing
        │
        ▼
Fine-Tuned BART
(Conversation Summarization)
        │
        ▼
Conversation Summary
        │
        ▼
FLAN-T5
(Mood-Based Story Generation)
        │
        ▼
Post Processing
(Repetition Removal + Emotion Enhancement)
        │
        ▼
Generated Story
        │
        ▼
Gradio Interface
```

---

## Dataset

The summarization model was fine-tuned on the **SAMSum Dataset**, a human-annotated dialogue summarization dataset containing messenger-style conversations and reference summaries.

### Dataset Statistics

- Training Dialogues: 14,732
- Human-written Summaries
- Multi-speaker conversational format

---

## Models Used

### 1. BART (Summarization)

**Model**

```text
facebook/bart-large-cnn
```

**Purpose**

- Dialogue summarization
- Context preservation
- Speaker relationship understanding

**Training Configuration**

- Fine-tuned on SAMSum dataset
- Beam Search = 4
- No Repeat N-Gram Size = 3
- Repetition Penalty = 1.5

---

### 2. FLAN-T5 (Story Generation)

**Model**

```text
google/flan-t5-large
```

**Purpose**

- Creative narrative generation
- Mood-controlled storytelling
- Context-aware text generation

**Generation Parameters**

- Temperature = 0.8
- Top-p = 0.9
- Beam Search = 3
- Repetition Penalty = 2.0

---

## Workflow

### Step 1: Input Conversation

```text
Emma: Are you free tomorrow?
Liam: Yes, let's visit the coffee shop.
Emma: The one where we had our first date?
Liam: Exactly!
```

### Step 2: Summarization

```text
Emma and Liam plan to revisit the coffee shop where they had their first date.
```

### Step 3: Story Generation (Romance)

```text
As the morning sunlight painted the streets gold, Emma smiled at Liam.
The little coffee shop held countless memories, including the day coffee
accidentally spilled across Liam's shirt on their first date...
```

---

## Performance

### Conversation Summarization Results

| Metric | Score |
|----------|----------|
| ROUGE-1 | 0.4894 |
| ROUGE-2 | 0.2491 |
| ROUGE-L | 0.4001 |
| ROUGE-Lsum | 0.4016 |

### Comparison with Baseline

| Model | ROUGE-1 | ROUGE-2 | ROUGE-L |
|--------|----------|----------|----------|
| BART-CNN Baseline | 43.5 | 21.0 | 40.2 |
| Fine-Tuned BART | 49.8 | 26.4 | 46.9 |

---

## Technologies Used

- Python
- PyTorch
- Hugging Face Transformers
- BART
- FLAN-T5
- Gradio
- CUDA (GPU Acceleration)
- Regular Expressions (Text Processing)

---

## Future Improvements

- GPT-4/Gemini-based story generation
- Multilingual conversation support
- Personalized storytelling
- Fine-grained emotion control
- Interactive story continuation
- Long-conversation memory handling
- Human evaluation metrics for creativity

---

## Research Contributions

- Novel dual-model pipeline combining summarization and creative generation
- Mood-adaptive narrative generation framework
- Integration of factual dialogue understanding with creative storytelling
- User-friendly deployment through Gradio
- Benchmark for conversation-to-story transformation tasks

---

## Authors

- Adhithi R
- Vishnusri P
- Keerthanah M.K.

---

---

## License

This project is intended for academic and research purposes. Feel free to modify and extend it for educational use.

---

## Acknowledgements

- Hugging Face Transformers
- PyTorch
- SAMSum Dataset
- Gradio
- BART Research Team
- FLAN-T5 Research Team
