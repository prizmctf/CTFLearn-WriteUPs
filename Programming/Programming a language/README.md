# Programming a language from [CTFlearn.com](https://ctflearn.com/challenge/1050)

#### This challenge wasn't particularly difficult, but a few lines to code.

### 1. Transferring the rules from the challenge into Python3
#### First off, i had to define functions for the actions ( + - . < > @ ) from the challenge:

 > "-" decreases stack's last element's value by 1,
 > "+" increases stack's last element's value by 1,
 > ">" puts first element at the end of the stack and shifts every other down,
 > "<" puts last element at the beginning of the stack and shifts every other up,
 > "@" exchanges last 2 elements,
 > "." duplicates stack's last element and puts it at the end of the stack,
 > "€" prints out every stack's element's value in ASCII (from the first to the last element)
#### which resulted in the following functions:

```python
def dash():
    stackarr[len(stackarr)-1] -= 1

def plus():
    stackarr[len(stackarr)-1] += 1

def arrowright():
    k = stackarr[0]
    for i in range (0, len(stackarr) -1):
      stackarr[i] = stackarr[i + 1]
    stackarr[len(stackarr)-1] = k

def arrowleft():
    k = stackarr[len(stackarr)-1]
    for i in range(0, len(stackarr)):
      stackarr[len(stackarr)-i-1] = stackarr[len(stackarr)-i-2]
    stackarr[0] = k
def atsign():
    last = stackarr[len(stackarr)-1]
    stackarr[len(stackarr) - 1] = stackarr[len(stackarr) - 2]
    stackarr[len(stackarr) -2] = last

def dot():
    last = stackarr[len(stackarr) - 1]
    stackarr.append(last)

def euro():
    tmpStr = ""
    for element in stackarr:
      tmpStr += chr(element)
    print(tmpStr)
```
TO BE CONTINUED :)
