![image](https://user-images.githubusercontent.com/89421832/211408113-170a5e45-fddc-47ea-ba4e-1c324d392395.png)

## Contents <img src = "https://c.tenor.com/RkILblKtLTEAAAAd/ms-wake-up.gif" width = 32px> </h2>
* [Info / Topics](README.md)
* [Log - click here to see my progress](log.md)

### 
##### 

< Today's Progress: > 

Today I started Pico go the first one done for general skills I was able to set up kali linux with WSL and will be running that over the use of the Built in terminal so I can work on some hands on with kali while doing CTFS on Pico and building my tool set.

< Thoughts: >

I need to figure out how to get get the man python to work pn python 3 or find a older versure #noob! but progress will happen 

# Obedient cat
1. copy the url for the flag form  the main page
2. ran wget in ubuntu with the url to get the file in my Pico folder
3. use cat of flag file to reveal the flag

![](https://i.imgur.com/23UepdY.png)

==Complete==

---

# Python Wrangling
1. I started off using wget to retrieve the python file from the server 
2. I then had to install python into my Kali Linux WSL2

### will finish later

---

< Today's Progress: >
Today I installed Unbuntu on my WSL2 o start working on a tool box to run on ctfs that I can build on the fly if needed. I also watched a video to help fill the gap on what I was missing on the last CTF for python. I was able to figure it out after learning about `chmod`

< Thoughts: >
Need to work on maintaing my list of commands and tools to better help me when im stuck

# Python Wrangling part 2

3. not that I had the files on my system I found that the ende.py file was not executable so I had to use `chmod ende.py` to convert it to a file that can be run with the python command. 
4. I ran `python3 ende.py -d flag.txt.en` this ran the and used a password to run the flag file to decrypt it giving me the flag.
5. Had to watch a video on this was a bit of a mix up because I was un aware of chmod. I made a note on my journal to remember the command if I ever run into this again.

![](https://i.imgur.com/qwZav0d.png)

==Complete==

---
# Wave a flag
1. Started by using `wget` to retrieve  the file
2. Then ran `chmod +x warm` to make it into a executable
3. ran `./ warm` to run it
4.  ran `./warm -h` it gave me the flag
![](https://i.imgur.com/zK0WNHc.png)

==Complete==
 
---
# Nice netcat...
1. I started off by using command `nc mercury.picoctf.net 43239`
2.  after running the command I was given a string of text that I put into a decoder to give me the flag as seen in the pic below easy peezy.
![](https://i.imgur.com/VrYTU4g.png)

==Complete==

--- 

< Today's Progress: >
Woke up and ran a ctf at **6:30 am** to ge the brain moving before work

< Thoughts: >
Im starting to figure out the `chmod +x` and when to use `cat` alot more now without having to readup or watch videos as much which makes me realy happy the practice is paying off and its stick to memeory.

# Static ain't always noise
1. I started off with using `wget` on both the static and the bash script
2. I now had both files in the directory
3. I tried to use `cat` on both but just found code that was all scrambled
4. Ran `chmod +x` on the .sh file to make it a executable then ran it with `/ltdis.sh static` This popped up a list of stuff that was actually readable. I was able to scroll through and found the flag.
![](https://i.imgur.com/lIZY5no.png)

**Complete**

---

< Today's Progress: >
Today I didnt get much done  CTF wise but was able to get one in before bed 

< Thoughts: >
It will be a useful tool latter on to get around the system without having to type out full words

# Tab, Tab, Attack
1. started off by using wget on the file to get it in the sytem
2. Once it was there we unzipped it then had to install a program to help use auto tab in linux terminal
3. after that we spammed `cd` and tab till we got to the last file were we then ran cat to get the flag
![](https://i.imgur.com/EHr1O6P.png)

**Complete**

---

< Today's Progress: >
Today I got a CTF done at lunch at work and going to try and do another after work tonight to catch up a bit

< Thoughts: >
Today was fun with SSH more of a refresher but still pretty fun

# Magikarp Ground Mission
1. Downloaded SSH to Ubuntu WSL
2. Loaded instance
3. SSH into `ssh ctf-player@venus.picoctf.net -p 56061` using password `6d448c9c`
4. It listed 2 files that were 1 of something so I cat into each one
![](https://i.imgur.com/J2Y0Smy.png)
![](https://i.imgur.com/BVNbl16.png)
5. I realized I missed 2 of 3 so had to back track
6. `cd drop-in` brought me to the other directory to get the last part of the flag I missed
7. Had to cd to the root folder with `cd /`
8. then `cd ~`
9. then found the last part of the flag
![](https://i.imgur.com/JQtsPbe.png)
![](https://i.imgur.com/h9VaAxh.png)
9. used `exit` to close ssh
**Complete**

---
# Lets Warm Up
1. For this one I used https://www.rapidtables.com/convert/number/ascii-to-hex.html to solve the problem
2. I out in the hex decimal and translated it to get the answer.
3. [Imgur](https://i.imgur.com/FhcckSy.png)

**Complete**

---
# Warmed Up
1. This one was close to the one before I have to look online for a conversion tool I used https://www.rapidtables.com/convert/number/hex-to-decimal.html?x=0x3D
2. ![](https://i.imgur.com/RT9XzDI.png)

**Completed**

---
# 2 Warm 
1. Another conversion this one I used http://extraconversion.com/base-number/base-10/base-10-to-base-2.html
3. ![](https://i.imgur.com/IZYvyvB.png)

**Completed**

---
# what's a net cat?
1. This was a pretty fast one just had to connect to the server via net cat
2. ![](https://i.imgur.com/64Hh9jj.png)

**Completed**

---
# strings it
1. I downloaded the file to my desktop and dragged it to VSC. 
2. I `ctrl f` to search for the word `pico`
3. The flag was in the middle 
4. ![](https://i.imgur.com/hJd0P1g.png)

**completed**

---
# Bases
1. What does this `bDNhcm5fdGgzX3IwcDM1` mean?
2. so I used the site https://www.base64decode.org/ to figure this out
3. I copy and pasted the tag and put it in to convert 

**completed**

---
# first grep
1. I started this out by downloading the file to my PicoCTF folder
2. I then tried to run `cat` to view the file and had no luck
3. I looked up the [[grep]] guide and found that I can run the command `grep 'topic to search' file name` to locate the item we are looking for the the file
4. Ran command and found the Flag
5. ![](https://i.imgur.com/Lq2fcH5.png)

**completed**

---
# code book
1. I started by downloading both files with `wget` into my PicoCTF directory 
2. Once both files were on my computer I used `python 3` and the file name for the `code.py` and ran it which gave me the flag
![](https://i.imgur.com/9mj470p.png)

**completed**

---
# covertime.py
1. `wget` the python file 
2. I then found a decimal to Binary converter at https://www.rapidtables.com/convert/number/decimal-to-binary.html
3. I then ran the file I downloaded with `python3 filename`
4. I was given a question to convert the decimal to binary, I used the site I found and got the answer. I typed the answer in the terminal and got the flag
![](https://i.imgur.com/VYP2BI6.png)

**Completed**

---
# fixme1.py
1. `wget` to download the file
2. So after downloading the file I was going to toss it into VIM but used VSC instead I saw that the error it gave was that the indention on line 20 was wrong. After looking I noticed that the word `print` was tabbed over so I backspaced it into place then ran it for the flag
![](https://i.imgur.com/rAMAYAj.png)

**completed**

---
# fixme2.py
1. `wget` to download the file
2. opened up file is VSC
3. Ran and found error log
4. We found there was a error in the syntax of `=` I changed it to a `==` and issue was fixed
![](https://i.imgur.com/d19FjJW.png)

**completed**

---
# Glitch cat 
1. I ran `nc saturn.picoctf.net 53933` and turned up
![](https://i.imgur.com/tf9DS2z.png)
2. This was a pain in the ass Had to input the string in python and print it I had to look up a guide to figure this one out
![](https://i.imgur.com/k3b9okN.png)

**completed**

---
