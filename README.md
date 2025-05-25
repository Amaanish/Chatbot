# EduBot: Intent-Based Chatbot using TensorFlow and NLTK

EduBot is a simple AI chatbot built with TensorFlow and Natural Language Toolkit (NLTK). It uses pattern matching, word tokenization, and deep learning to classify user inputs into predefined intents and provide appropriate responses.

##  Features

- Intent classification using a neural network (Keras + TensorFlow)
- Tokenization and lemmatization using NLTK
- Uses bag-of-words model for text representation
- Loads and responds from a JSON-based intent dataset
- Handles uncertain queries with fallback responses

---

##  Technologies Used

- Python
- TensorFlow / Keras
- NLTK
- NumPy
- Google Colab (for development)

---

## 📂 Project Structure

- `DB.json` – Intent dataset (tags, patterns, responses)
- `chatbot_model.h5` – Trained Keras model
- `words.pkl`, `classes.pkl`, `lemmatizer.pkl` – Saved preprocessing data
- Training & runtime scripts (as shown in this repo)

---

##  How It Works

1. **Data Preparation**:
   - Load patterns and tags from `DB.json`.
   - Tokenize and lemmatize patterns using NLTK.
   - Create bag-of-words vectors for each pattern.

2. **Model Training**:
   - Neural network with input from bag-of-words vectors.
   - Categorical output layer for intent classification.
   - Trained using SGD optimizer.

3. **Chatbot Loop**:
   - User input is processed into a BoW vector.
   - Prediction probabilities are generated.
   - The most likely intent is matched (if above confidence threshold).
   - A response is selected randomly from the intent’s responses.

---

## 📉 Caveats and Limitations

- **Static Intent Dataset**: Responses are based entirely on predefined patterns and responses. It does not understand free-form natural conversation or context.
- **No Memory/Context**: EduBot cannot track conversation history or handle follow-up questions based on prior messages.
- **Low Confidence Handling**: If the model is unsure (`< 60% confidence`), it uses fallback responses, but these may not always feel natural or helpful.
- **Vocabulary Limitations**: Only words in the training patterns are recognized. New words or synonyms may be ignored.
- **No Named Entity Recognition**: EduBot cannot extract dynamic data like dates, numbers, or names unless predefined.

---

##  Future Improvements

- Add context tracking to enable multi-turn conversations.
- Expand the JSON dataset with more intents and patterns.
- Implement spell check and synonym recognition.
- Integrate with a web frontend or API for broader usability.
- Replace bag-of-words with embedding-based models (e.g., Word2Vec or BERT).

---
