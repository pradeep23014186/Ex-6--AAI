<H3>NAME : G Pradeep Kumar</H3>
<H3>REGISTER NO : 212223230150</H3>
<H3>EX. NO.6</H3>
<H3>DATE: 24/05/2025</H3>
<H1 ALIGN=CENTER>Implementation of Semantic Analysis</H1>

## Aim:
To perform Parts of speech identification and Synonym using Natural Language Processing (NLP) techniques.
## Algorithm:
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
## Program:
```
import nltk
nltk.download('punkt')
nltk.download('wordnet')
nltk.download('averaged_perceptron_tagger')
nltk.download('omw-1.4')  # This line fixes your error

from nltk.tokenize import word_tokenize
from nltk.corpus import wordnet

sentence = "Happiness depends upon ourselves"

words = word_tokenize(sentence)
pos_tags = nltk.pos_tag(words)

for word, tag in pos_tags:
    print(f"{word} : {tag}")

synonyms = set()
antonyms = set()

for word in words:
    for syn in wordnet.synsets(word):
        for lemma in syn.lemmas():
            synonyms.add(lemma.name())
            if lemma.antonyms():
                antonyms.add(lemma.antonyms()[0].name())

print("\nSynonyms:", synonyms)
print("Antonyms:", antonyms)
```

## Output:
![image](https://github.com/user-attachments/assets/6bef7668-3794-4f20-9b5f-c123a0b277a5)


## Result:
Thus ,the program to perform the Parts of Speech identification and Synonymis executed sucessfully.
