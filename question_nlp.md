### 1. regular expression questions: 1) what's the difference between r'[\w]+' and r'\w+'? 2) what if I want to find the pattern including brackets '[]'?
Answer blabla
### 2. open function in python, what's the difference between 'r' and 'rb' mode?
This depends a little bit on what version of Python you're using. In Python 3, its a different (and more consistent) story: in text mode ('r'), Python will parse the file according to the text encoding you give it (or, if you don't give one, a platform-dependent default), and read() will give you a str. In binary ('rb') mode, Python does not assume that the file contains things that can reasonably be parsed as characters, and read() gives you a bytes object.

Also, in Python 3, the universal newlines (the translating between '\n' and platform-specific newline conventions so you don't have to care about them) is available for text-mode files on any platform, not just Windows.

From documentation:

On Windows, 'b' appended to the mode opens the file in binary mode, so there are also modes like 'rb', 'wb', and 'r+b'. Python on Windows makes a distinction between text and binary files; the end-of-line characters in text files are automatically altered slightly when data is read or written. This behind-the-scenes modification to file data is fine for ASCII text files, but it’ll corrupt binary data like that in JPEG or EXE files. Be very careful to use binary mode when reading and writing such files. On Unix, it doesn’t hurt to append a 'b' to the mode, so you can use it platform-independently for all binary files.
