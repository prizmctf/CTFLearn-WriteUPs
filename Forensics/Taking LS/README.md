### Taking LS from [CTFLearn.com](https://ctflearn.com/challenge/103)
#### First, we need to download the .zip file from the challenge.
#### After that, we can use unzip to extract the files:
```bash
unzip "The Flag.zip"
```
![image](https://user-images.githubusercontent.com/106492307/170985796-35a50646-5188-46fe-9cdf-c2ac6e522d89.png)

#### As we can see in the unzip output, there are hidden folders/files ( the ones starting with "." ). We can also see that there is a PDF file which contains the flag. 
#### However, we need to find out a password. Good thing is, we already know where to look:
![image](https://user-images.githubusercontent.com/106492307/170986381-8f555664-4085-4cf5-b441-3bf6521a9476.png)

#### Now we can "cd" into the folder and use "cat" to print the output of the password file:
```bash
cd .ThePassword/
cat ThePassword.txt
```
#### which results in the following:
![image](https://user-images.githubusercontent.com/106492307/170986836-5a00af47-2fe2-4c1a-b2eb-4c9aeb3d566a.png)

#### Now that we have the password, lets open the .pdf file and enter the password:
![image](https://user-images.githubusercontent.com/106492307/170985191-26880734-3cb5-4bae-a3b1-1d573c50f08b.png)

#### BINGO!!!
![image](https://user-images.githubusercontent.com/106492307/170987337-1ef06d77-a7b1-43fb-b891-60f38bdc69c6.png)


#### I hope you enjoyed reading through this!
#### Happy hacking <3
