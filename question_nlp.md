### 1. Regular expression questions: 1) what's the difference between r'[\w]+' and r'\w+'? 2) what if I want to find the pattern including brackets '[]'?
Answer blabla
### 2. Open function in python, what's the difference between 'r' and 'rb' mode?
This depends a little bit on what version of Python you're using. In Python 3, its a different (and more consistent) story: in text mode ('r'), Python will parse the file according to the text encoding you give it (or, if you don't give one, a platform-dependent default), and read() will give you a str. In binary ('rb') mode, Python does not assume that the file contains things that can reasonably be parsed as characters, and read() gives you a bytes object.

Also, in Python 3, the universal newlines (the translating between '\n' and platform-specific newline conventions so you don't have to care about them) is available for text-mode files on any platform, not just Windows.

**_From documentation:_**

On Windows, 'b' appended to the mode opens the file in binary mode, so there are also modes like 'rb', 'wb', and 'r+b'. Python on Windows makes a distinction between text and binary files; the end-of-line characters in text files are automatically altered slightly when data is read or written. This behind-the-scenes modification to file data is fine for ASCII text files, but it’ll corrupt binary data like that in JPEG or EXE files. Be very careful to use binary mode when reading and writing such files. On Unix, it doesn’t hurt to append a 'b' to the mode, so you can use it platform-independently for all binary files.
### 3. When we use Spacy to tokenize strings, notice the following difference:
```python
nlp = spacy.load('en_core_web_sm') # 'en_core_web_lg'/'en_core_web_md' are for large/medium size models
mystring = 'abcdefg'
nlp(mystring)
nlp(u'abcdefg') # use 'u' if directly put the string in nlp function
```
### 4. The difference between part-of-speech and dependency tags.
https://stackoverflow.com/questions/40288323/what-do-spacys-part-of-speech-and-dependency-tags-mean
### 5. The difference between stemming and lemmatization.
Stemming usually refers to a crude heuristic process that chops off the ends of words in the hope of achieving this goal correctly most of the time, and often includes the removal of derivational affixes. Lemmatization usually refers to doing things properly with the use of a vocabulary and morphological analysis of words, normally aiming to remove inflectional endings only and to return the base or dictionary form of a word, which is known as the lemma . If confronted with the token saw, stemming might return just s, whereas lemmatization would attempt to return either see or saw depending on whether the use of the token was as a verb or a noun. The two may also differ in that stemming most commonly collapses derivationally related words, whereas lemmatization commonly only collapses the different inflectional forms of a lemma. Linguistic processing for stemming or lemmatization is often done by an additional plug-in component to the indexing process, and a number of such components exist, both commercial and open-source.

https://nlp.stanford.edu/IR-book/html/htmledition/stemming-and-lemmatization-1.html
