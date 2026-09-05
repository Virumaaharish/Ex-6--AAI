<H3>NAME: Virumaa Harish M</H3>
<H3>REGISTER NO: 212223230246</H3>
<H3>EX. NO.6</H3>
<H1 ALIGN =CENTER>Implementation of Semantic ANalysis</H1>
<h3>Aim:</h3>
To perform Parts of speech identification and Synonym using Natural Language Processing (NLP) techniques.
 
 
## <h3>Algorithm:</h3>

Step 1: Import the nltk library.<br>
Step 2: Download the 'punkt', 'wordnet', and 'averaged_perceptron_tagger' resources.<br>
Step 3:Accept user input for the text.<br>
Step 4:Tokenize the input text into words using the word_tokenize function.<br>
Step 5:Iterate through each word in the tokenized text.<br>
•	Perform part-of-speech tagging on the tokenized words using nltk.pos_tag.<br>
•	Print each word along with its corresponding part-of-speech tag.<br>
•	For each verb , iterate through its synsets (sets of synonyms) using wordnet.synsets(word).<br>
•	Extract synonyms and antonyms using lemma.name() and lemma.antonyms()[0].name() respectively.<br>
•	Print the unique sets of synonyms and antonyms.

## <H3>Program:</H3>

```python
import nltk

# Download required NLTK resources
nltk.download('punkt')
nltk.download('punkt_tab')
nltk.download('wordnet')
nltk.download('omw-1.4')
nltk.download('averaged_perceptron_tagger')
nltk.download('averaged_perceptron_tagger_eng')

from nltk.tokenize import word_tokenize
from nltk.corpus import wordnet

# Get input from user
sentence = input("Enter a sentence: ")

# Tokenize the sentence into words
words = word_tokenize(sentence)

# Identify the parts of speech for each word
pos_tags = nltk.pos_tag(words)

# Lists for synonyms and antonyms
synonyms = []
antonyms = []

# Identify synonyms and antonyms for each word
for word in words:
    for syn in wordnet.synsets(word):
        for lemma in syn.lemmas():

            synonyms.append(lemma.name())

            if lemma.antonyms():
                antonyms.append(lemma.antonyms()[0].name())

# Remove duplicates and print results
print("\nParts of Speech:")
print(pos_tags)

print("\nSynonyms:")
print(set(synonyms))

print("\nAntonyms:")
print(set(antonyms))
```

## <H3>Output</H3>
<img width="1647" height="171" alt="image" src="https://github.com/user-attachments/assets/69cc1043-7170-49b0-8018-f7ddb5148aa3" />



## <H3>Result:</H3>
Thus ,the program to perform the Parts of Speech identification and Synonymis executed sucessfully.
