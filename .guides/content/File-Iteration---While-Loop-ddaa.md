----------

## Readline vs. Readlines

The `readlines` method reads all of the lines at once and returns them in a list. There is another method called `readline`. The `readline` method returns only one line from the text file. Python automatically keeps track of which lines have been read, and which have not.

```python
import os

path = "student_folder/text"

with open(os.path.join(path, "read_practice.txt"), "r") as read_file:
    print(read_file.readline())
```

{try it}(python3 code/files/while-iteration.py 1)

|||challenge
## What happens if you:
* Change `readline()` to `readlines()`?
* Change the code to look like this:
```python
import os

path = "student_folder/text"

with open(os.path.join(path, "read_practice.txt"), "r") as read_file:
    print(read_file.readline(), end="")
    print(read_file.readline(), end="")
```

|||

{try it}(python3 code/files/while-iteration.py 2)

## While Loop

While loops can also iterate over a text file. Remember, while loops require a stop condition to keep it from becoming an infinite loop. Each text file ends with an empty string (`""`). That is how Python knows it has reached the end of a file. So a while loop should each line of the text file until it reaches the empty string. Because of this, iterating over a text with a while loop will use `readline` instead of `readlines`. It is important to read the first line of the text file **before** starting the while loop. And, read the next line of the text file **inside** the while loop as well.

![Reading a File with a While Loop](.guides/images/while-loop-read-file.png)

```python
import os

path = "student_folder/text"

with open(os.path.join(path, "read_practice.txt"), "r") as read_file:
    line = read_file.readline()
    while line != "":
        print(line)
        line = read_file.readline()
```

{try it}(python3 code/files/while-iteration.py 3)

|||challenge
## What happens if you:
* Chage the first `line = read_file.readline()` to `readlines()`?
* Remove the first `line = read_file.readline()`?
* Put back the first `line = read_file.readline()` and remove the second one?


|||

{try it}(python3 code/files/while-iteration.py 4)

{Check It!|assessment}(fill-in-the-blanks-547217630)
