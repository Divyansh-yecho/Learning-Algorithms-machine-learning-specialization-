🔤 Makemore with Context — Character-Level Neural Language Model

---

## 🧠 Overview

This project implements a character-level neural language model inspired by Andrej Karpathy’s *makemore*, where the goal is to generate realistic-looking names by learning patterns from a dataset of names. The model predicts the next character given a fixed-length context of previous characters, effectively learning the structure and distribution of sequences in the data :contentReference[oaicite:0]{index=0}.

The focus of this work is to understand how simple neural networks can model sequential data using embeddings and context windows.

---

## 🔬 Model Description

The model takes a fixed **context of 3 characters** and predicts the next character in the sequence. It consists of:

- **Embedding layer**: maps each character to a dense vector  
- **Hidden layer**: fully connected layer with nonlinearity (tanh)  
- **Output layer**: predicts probability distribution over all characters  

This forms a simple feedforward neural network trained to model sequence probabilities.

---

## ⚙️ Methodology

1. **Dataset Preparation**
   - Load a dataset of names  
   - Create character-to-index mappings  
   - Convert each word into (context → next character) pairs  

2. **Context Windowing**
   - Use a fixed block size of 3  
   - Slide over each word to create training samples  

3. **Train-Validation-Test Split**
   - 80% training  
   - 10% validation (dev)  
   - 10% test  

4. **Model Training**
   - Randomly initialize parameters  
   - Use cross-entropy loss  
   - Train with stochastic gradient descent  
   - Apply learning rate scheduling  

5. **Evaluation**
   - Compute loss on training and validation sets  
   - Analyze convergence behavior  

---

## 📊 Key Features

- 🔤 Character-level sequence modeling  
- 🧠 Learned embeddings for discrete tokens  
- 📉 Training loss visualization  
- 📈 Learning rate exploration  
- 🔍 Embedding space visualization  
- 🎲 Sampling new names from the trained model  

---

## 🛠️ Tools & Libraries Used

- Python  
- PyTorch  
- Matplotlib  
- NumPy  

---

## ⚡ How It Works

1. Encode characters into numerical indices  
2. Build context-target pairs using sliding windows  
3. Pass context through embedding layer  
4. Flatten and feed into neural network  
5. Compute logits and apply softmax  
6. Train using backpropagation  
7. Sample new sequences using learned probabilities  

---

## 🎲 Output

After training, the model can generate new names by:

- Starting with an empty context  
- Iteratively predicting the next character  
- Sampling from the probability distribution  
- Stopping when an end token is generated  

---

## 🧩 Learning Outcome

Through this project, I focused on:

- Understanding sequence modeling without recurrent networks  
- Learning how embeddings capture semantic structure  
- Implementing neural networks from scratch using PyTorch  
- Visualizing learned representations  
- Connecting probabilistic modeling with neural architectures  

---

## 🚀 Notes

This project is part of my broader effort to build a strong foundation in deep learning and sequence modeling, with an emphasis on understanding models at a low level rather than relying solely on high-level abstractions.
