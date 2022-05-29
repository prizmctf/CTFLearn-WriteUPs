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
stackarr = [0] #initialize a list with 0 

def dash():
    stackarr[len(stackarr)-1] -= 1  #decrease last element by 1

def plus():
    stackarr[len(stackarr)-1] += 1  #increase last element by 1

def arrowright():
    k = stackarr[0]     #save value of the first element
    for i in range (0, len(stackarr) -1):   #go through every element..
      stackarr[i] = stackarr[i + 1]     #..and shift the indices forward ( 2 => 1, 3 => 2, ... )
    stackarr[len(stackarr)-1] = k   #put the previously saved element in the last spot

def arrowleft():
    k = stackarr[len(stackarr)-1]   #save value of the last element
    for i in range(0, len(stackarr)):   #iterate again
      stackarr[len(stackarr)-i-1] = stackarr[len(stackarr)-i-2]     #and shift the indices backwards by reassigning the values. 3 => 4,..
    stackarr[0] = k     #prepend the last element to the list

def atsign():
    last = stackarr[len(stackarr)-1]    #save value of the last item
    stackarr[len(stackarr) - 1] = stackarr[len(stackarr) - 2]   #put the second last item in the last spot
    stackarr[len(stackarr) -2] = last   #and put the last item in the second last place

def dot():
    last = stackarr[len(stackarr) - 1]  #get the last value
    stackarr.append(last)   #and append it

def euro():
    tmpStr = ""     #init a temporary string
    for element in stackarr:    #go through the list
      tmpStr += chr(element)    #and append the ASCII character for the ordinal value to the string
    print(tmpStr)   #print the flag! (HOPEFULLY)
```
TO BE CONTINUED :)
