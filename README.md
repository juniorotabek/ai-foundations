````markdown
# AI Foundations

A hands-on repository for building my understanding of machine learning and modern AI from first principles.

The goal of this repository is not simply to use pretrained models or AI frameworks, but to understand the concepts underneath them well enough to implement, experiment with, debug, and explain them.

I am working progressively from:

**Math → Classical ML → Neural Networks → PyTorch → Computer Vision → Transformers → LLMs → Fine-tuning → Evaluation → Research-style experimentation**

---

## Why This Repository Exists

I have already worked with LLMs, multimodal models, local inference, AI agents, structured extraction, and production AI systems.

However, much of that work has been done at a relatively high abstraction level using existing models and AI-assisted development tools.

This repository is intended to close that gap.

My objectives are to:

- understand the mathematics behind machine learning
- implement important algorithms from scratch
- understand backpropagation rather than treating it as a black box
- become comfortable with PyTorch and model training
- understand Transformer and LLM architectures
- learn how fine-tuning and parameter-efficient training work
- evaluate models scientifically instead of relying on subjective output quality
- develop the skills required for applied AI and AI research engineering

---

## Learning Rule

For exercises in this repository, AI tools are primarily used as:

- tutors
- code reviewers
- debugging assistants
- sources of explanations

They should **not** write the core implementation before I have attempted it myself.

The standard I am aiming for is:

> If I cannot explain why the code works, I do not consider the topic learned.

For every major topic I should eventually be able to:

1. Explain the concept.
2. Implement a simplified version.
3. Debug it.
4. Experiment with it.
5. Explain the results.
6. Answer "why?" questions about the implementation.

---

# Roadmap

## Phase 1 — Mathematical & ML Foundations

### Week 1 — Linear Algebra, Derivatives & Linear Regression

Topics:

- scalars
- vectors
- matrices
- shapes and dimensions
- dot products
- matrix multiplication
- functions
- derivatives
- gradients
- mean squared error
- gradient descent
- learning rate

Project:

`01_linear_regression/`

Implement linear regression from scratch using NumPy.

Target example:

```text
y = 3x + 7 + noise
````

The model should learn approximately:

```text
w ≈ 3
b ≈ 7
```

No scikit-learn or PyTorch model implementation.

---

### Week 2 — Probability, Statistics & Generalization

Topics:

* mean
* median
* variance
* standard deviation
* probability
* conditional probability
* distributions
* train / validation / test splits
* residuals
* underfitting
* overfitting
* generalization

Extend the linear regression project with:

* train/test split
* training loss
* test loss
* learning curves
* visualization

---

### Week 3 — Classification & Logistic Regression

Topics:

* binary classification
* sigmoid
* probabilities
* thresholds
* binary cross entropy
* confusion matrix
* true positives
* false positives
* true negatives
* false negatives
* accuracy
* precision
* recall
* F1 score

Project:

`02_logistic_regression/`

Implement logistic regression from scratch using NumPy.

---

### Week 4 — Neural Networks

Topics:

* neurons
* weights
* biases
* linear layers
* activation functions
* ReLU
* sigmoid
* softmax
* logits
* hidden layers
* cross entropy

Project:

`03_neural_network_numpy/`

Build the forward pass of a small neural network using only NumPy.

Example:

```text
Input
  ↓
Linear
  ↓
ReLU
  ↓
Linear
  ↓
Softmax
```

---

### Week 5 — Backpropagation

Topics:

* chain rule
* computational graphs
* forward propagation
* backward propagation
* gradients through linear layers
* gradients through activation functions
* parameter updates

Extend the NumPy neural network with:

```text
forward()
loss()
backward()
update()
```

Train the network without automatic differentiation.

---

# Phase 2 — Deep Learning with PyTorch

## Week 6 — PyTorch Fundamentals

Topics:

* tensors
* devices
* dtypes
* autograd
* `nn.Module`
* `nn.Linear`
* optimizers
* loss functions
* `Dataset`
* `DataLoader`
* training loops
* evaluation loops

Project:

`04_pytorch_mlp/`

Rebuild the previous neural network using PyTorch.

Train an MLP on MNIST or Fashion-MNIST.

---

## Week 7 — Optimization & Experimentation

Topics:

* gradient descent
* SGD
* mini-batch SGD
* momentum
* Adam
* AdamW
* learning rate
* batch size
* weight decay
* dropout
* regularization

Run controlled experiments comparing different training configurations.

Example:

| Experiment | Optimizer | LR  | Batch Size | Validation Accuracy |
| ---------- | --------- | --- | ---------- | ------------------- |
| A          | Adam      | ... | ...        | ...                 |
| B          | SGD       | ... | ...        | ...                 |
| C          | AdamW     | ... | ...        | ...                 |

The goal is not only to obtain a good result, but to explain **why the result changed**.

---

## Week 8 — Computer Vision Foundations

Topics:

* image tensors
* channels
* convolution
* kernels
* stride
* padding
* feature maps
* pooling
* receptive fields
* CNN architecture

Project:

`05_cnn/`

Train a small CNN on CIFAR-10 and compare it with a fully connected neural network.

---

# Phase 3 — Transformers

## Week 9 — Embeddings & Attention

Topics:

* tokenization
* token IDs
* embeddings
* vector similarity
* cosine similarity
* attention intuition
* Query
* Key
* Value

Project:

`06_attention/`

Implement scaled dot-product attention.

---

## Week 10 — Self-Attention

Topics:

* Q, K and V projections
* attention scores
* scaling by √d
* softmax
* causal masking
* multi-head attention

Implement a self-attention module and track tensor dimensions through the entire operation.

---

## Week 11 — Transformer Architecture

Topics:

* residual connections
* normalization
* feed-forward networks
* Transformer blocks
* stacking Transformer layers
* causal language modeling
* next-token prediction

Project:

`07_transformer_from_scratch/`

Build and train a small autoregressive language model.

The goal is not model quality.

The goal is to understand the architecture.

---

## Week 12 — Modern LLM Architecture

Topics:

* BPE and subword tokenization
* RoPE
* RMSNorm
* SwiGLU
* multi-head attention
* multi-query attention
* grouped-query attention
* KV cache
* prefill
* decoding
* context length

Study the architecture of a modern open-weight LLM and inspect its configuration.

---

# Phase 4 — Working With LLMs

## Week 13 — Hugging Face & Inference

Topics:

* `AutoTokenizer`
* `AutoModel`
* `AutoModelForCausalLM`
* logits
* next-token probabilities
* greedy decoding
* temperature
* top-k sampling
* top-p sampling

Project:

`08_llm_inference/`

Implement a simple text-generation loop without relying entirely on `.generate()`.

---

## Week 14 — Fine-Tuning

Topics:

* pretraining
* supervised fine-tuning
* instruction tuning
* full fine-tuning
* LoRA
* QLoRA
* rank
* alpha
* target modules
* quantization

Project:

`09_lora_finetuning/`

Fine-tune a small language model for a structured-output task.

---

## Week 15 — Model Evaluation

Topics:

* evaluation datasets
* baselines
* exact match
* field-level accuracy
* precision
* recall
* latency
* error analysis
* reproducibility

Project:

`10_model_evaluation/`

Compare:

```text
Base model
vs.
Prompted model
vs.
Fine-tuned model
```

using a fixed evaluation set.

---

## Week 16 — Research-Style Experiment

Turn one practical AI problem into a measurable research question.

Example:

> Does access to conversation history improve structured information extraction compared with processing only the most recent message?

Possible conditions:

```text
A — latest message only
B — last 3 messages
C — complete conversation
D — complete conversation + image
```

Measure the results and write a short research-style report containing:

* problem
* hypothesis
* dataset
* methodology
* baselines
* results
* error analysis
* limitations
* conclusion

Project:

`11_research_experiment/`

---

# Repository Structure

```text
ai-foundations/
│
├── README.md
├── notes/
│   ├── week-01/
│   ├── week-02/
│   └── ...
│
├── 01_linear_regression/
├── 02_logistic_regression/
├── 03_neural_network_numpy/
├── 04_pytorch_mlp/
├── 05_cnn/
├── 06_attention/
├── 07_transformer_from_scratch/
├── 08_llm_inference/
├── 09_lora_finetuning/
├── 10_model_evaluation/
└── 11_research_experiment/
```

The structure may evolve as my understanding improves.

---

# Daily Notes

For each learning session I keep short notes answering:

```text
What did I learn?

What still does not make sense?

What did I implement myself?

What did AI help me with?
```

This helps distinguish between:

> "I saw this concept."

and:

> "I understand this concept."

---

# Progress

| Phase                    | Status         |
| ------------------------ | -------------- |
| Mathematical Foundations | 🟡 In Progress |
| Classical ML             | ⬜ Not Started  |
| Neural Networks          | ⬜ Not Started  |
| PyTorch                  | ⬜ Not Started  |
| Computer Vision          | ⬜ Not Started  |
| Attention                | ⬜ Not Started  |
| Transformers             | ⬜ Not Started  |
| Modern LLMs              | ⬜ Not Started  |
| Fine-Tuning              | ⬜ Not Started  |
| Evaluation               | ⬜ Not Started  |
| Research Experiment      | ⬜ Not Started  |

---

# Main Tools

As the repository progresses, I expect to use:

```text
Python
NumPy
Matplotlib
PyTorch
Hugging Face Transformers
Datasets
PEFT
llama.cpp / local inference tools
```

Tools are introduced only when the underlying concepts have been studied.

---

# Long-Term Goal

The long-term goal is to develop the foundation required to work confidently in:

* Applied AI
* Machine Learning Engineering
* AI Research Engineering
* LLM systems
* Multimodal AI
* Agentic AI
* Efficient local AI inference

The focus is not on completing tutorials.

The focus is on developing enough understanding to:

> build, measure, debug, modify, and explain AI systems independently.

````
