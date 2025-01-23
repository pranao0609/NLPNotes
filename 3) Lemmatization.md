### **Lemmatization in NLP**

**Lemmatization** reduces a word to its base or dictionary form, known as the lemma. Unlike stemming, it considers the word's context and grammar (part of speech) to produce linguistically accurate results.

#### Key Difference Between Stemming and Lemmatization
- **Stemming**: Heuristic-based and may produce non-words (e.g., `studies` → `studi`).
- **Lemmatization**: Context-aware and outputs actual dictionary words (e.g., `studies` → `study`).

---

### **Lemmatization Using NLTK**

#### 1. **WordNet Lemmatizer**

The **WordNet Lemmatizer** is based on the WordNet lexical database. It requires specifying the part of speech (POS) to improve accuracy. The default POS is **noun** if none is provided.

##### Basic Example:
```python
from nltk.stem import WordNetLemmatizer

# Initialize WordNet Lemmatizer
lemmatizer = WordNetLemmatizer()

# Example words
words = ["running", "flies", "better", "studies"]

# Lemmatize without POS
lemmas = [lemmatizer.lemmatize(word) for word in words]
print(lemmas)  # Output: ['running', 'fly', 'better', 'study']
```

---

#### 2. **Lemmatization with POS Tags**

Specifying the part of speech improves the output:
- **POS options**: 
  - `n` for noun
  - `v` for verb
  - `a` for adjective
  - `r` for adverb

```python
# Lemmatize with POS
print(lemmatizer.lemmatize("running", pos="v"))  # Output: 'run'
print(lemmatizer.lemmatize("better", pos="a"))  # Output: 'good'
print(lemmatizer.lemmatize("flies", pos="n"))   # Output: 'fly'
```

---

#### 3. **Combining Lemmatization with POS Tagging**

To fully utilize lemmatization, integrate it with POS tagging using **NLTK's POS tagger**:
```python
import nltk
from nltk.stem import WordNetLemmatizer
from nltk.corpus import wordnet

# Download necessary resources
nltk.download('punkt')
nltk.download('averaged_perceptron_tagger')
nltk.download('wordnet')

# Initialize Lemmatizer
lemmatizer = WordNetLemmatizer()

# Function to convert NLTK POS tags to WordNet POS tags
def get_wordnet_pos(tag):
    if tag.startswith('J'):
        return wordnet.ADJ
    elif tag.startswith('V'):
        return wordnet.VERB
    elif tag.startswith('N'):
        return wordnet.NOUN
    elif tag.startswith('R'):
        return wordnet.ADV
    else:
        return None

# Example text
text = "The striped bats are flying swiftly in the skies"

# Tokenize and POS tag
tokens = nltk.word_tokenize(text)
pos_tags = nltk.pos_tag(tokens)

# Lemmatize with POS tagging
lemmas = []
for token, tag in pos_tags:
    wn_tag = get_wordnet_pos(tag)  # Convert POS tag
    if wn_tag:
        lemmas.append(lemmatizer.lemmatize(token, pos=wn_tag))
    else:
        lemmas.append(lemmatizer.lemmatize(token))  # Default to noun

print("Original:", tokens)
print("Lemmatized:", lemmas)
```

**Output:**
```
Original: ['The', 'striped', 'bats', 'are', 'flying', 'swiftly', 'in', 'the', 'skies']
Lemmatized: ['The', 'striped', 'bat', 'be', 'fly', 'swiftly', 'in', 'the', 'sky']
```

---

### WordNet Lemmatizer Advantages
1. **Context-Aware**: Adjusts based on POS, yielding accurate results.
2. **Dictionary-Based**: Produces valid words.
3. **Language Support**: Works for English; external tools are needed for other languages.
