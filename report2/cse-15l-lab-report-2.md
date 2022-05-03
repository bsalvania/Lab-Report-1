# **CSE 15L Lab Report 2**

## Change 1: Infinite loop fix (Link with parenthesis inside)

* Code Change: ![Image](codeChangeOne.jpg)

* Link to test file for *failure-inducing input*: [link](https://github.com/bsalvania/markdown-parser/commit/98d2429e664e5a49cc3501ce27a87d8a6dc61c91)
    * The 4th link causes an infinite loop. This is because the method never reaches the end of the file as it gets the wrong index for the variables closeParen.

* Symptom: ![Image](symptomOne.jpg)

* The failure inducing input is a link with multiple parentheses inside it. The bug is that the method never stops running, because the index for the parentheses keeps switching back and forth. The symptom is an infinite loop, which eventually results in a OutOfMemoryError.


---
## Change 2: Differentiating between an image and a link

* Code Change: ![Image](codeChangeTwo.jpg)

* Link to test file for *failure-inducing input*: [link](https://github.com/TheJoeship/markdown-parser-fork/commit/ca97f28fa6755f1d48b519a208765e39ffd9a4f2 ) 
    * Links to a group member's repository

    * The problem is that the method thinks an image is a link and thus adds it to the array list of links. This is a problem because the array list should only contain links that the file has.
* Symptom: ![Image](symptomTwo.jpg)

* The failure-inducing input is an image that the file contains. The bug is that the method reads the image as a link, because the method is based on brackets and parentheses, which an image has. The symptom is that the image link is added to the array of links that is outputted at the end of the function.

---
## Change 3: Index Out Of Bounds fix (No link and brackets in .md file)

* Code Change: ![Image](codeChangeThree.jpg)

* Link to test file for *failure-inducing input*: [link](https://github.com/bsalvania/markdown-parser/commit/f405559bd7eeb5e0f402101995ec66bd2fbce98f)

    * Because there are no links, the index given to the method for some of its variables are -1 (in this case openParen and closeParen). This causes the *toReturn.add(markdown.substring(openParen + 1, closeParen));* code to throw an index out of bounds exception because it tries to access a string from 0 to -1, which isn't possible.

* Symptom: ![Image](symptomThree.jpg)

* The failure-inducing input is a file with no links and brackets. The bug is that because there are brackets and no parentheses, the variables for the parentheses are giving an index of -1. The method tries to get a string using the index -1, resulting in the symptom, a StringIndexOutOfBoundsException, appearing.

---
[Homepage](https://bsalvania.github.io/cse-15l-lab-reports/index.html)