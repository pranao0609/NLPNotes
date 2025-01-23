### Introduction to Natural Language Processing (NLP)

Natural Language Processing (NLP) is a subfield of artificial intelligence (AI) and linguistics that focuses on the interaction between computers and human languages. The goal of NLP is to enable machines to understand, interpret, and generate human language in a meaningful way.

#### Applications of NLP:
1. **Text Classification**: Spam filtering, sentiment analysis.
2. **Machine Translation**: Translating text from one language to another.
3. **Speech Recognition**: Converting spoken language into text.
4. **Named Entity Recognition (NER)**: Identifying entities like names, dates, and locations in text.
5. **Chatbots and Virtual Assistants**: Conversational AI (e.g., Alexa, Siri).
6. **Text Summarization**: Generating concise summaries from large documents.

---

### Tokenization

**Tokenization** is the process of breaking a piece of text into smaller units called tokens. Tokens can be:
1. **Words**: Splitting text into individual words.
   - Example: `"I love NLP"` → `["I", "love", "NLP"]`
2. **Subwords**: Splitting text into smaller parts, often used in models like BERT.
   - Example: `"unbelievable"` → `["un", "believable"]`
3. **Characters**: Splitting text into individual characters.
   - Example: `"cat"` → `["c", "a", "t"]`

Tokenization is a fundamental step in text preprocessing and depends on:
- The language being processed.
- The NLP task (e.g., classification, translation).

---

### Basic Terminology in NLP

1. **Corpus**: A large collection of text data used for training NLP models.
   - Example: News articles, books, or tweets.

2. **Vocabulary**: The set of all unique tokens in a corpus.

3. **Stop Words**: Commonly used words (e.g., "the," "is") that are often removed in text processing.

4. **Stemming**: Reducing a word to its root form by chopping off suffixes.
   - Example: `"playing"` → `"play"`

5. **Lemmatization**: Reducing a word to its dictionary base form, considering the context.
   - Example: `"better"` → `"good"`

6. **Bag of Words (BoW)**: A representation of text where each word is treated as a feature, ignoring grammar and word order.

7. **TF-IDF (Term Frequency-Inverse Document Frequency)**: A method to evaluate the importance of a word in a document relative to a corpus.

8. **N-grams**: Continuous sequences of n tokens.
   - Example: For `n=2`, `"I love NLP"` → `["I love", "love NLP"]`

9. **Embedding**: Representing words as vectors in a continuous vector space (e.g., Word2Vec, GloVe).

10. **Named Entity Recognition (NER)**: Identifying and classifying entities in text, such as names, dates, or locations.

---
