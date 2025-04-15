# The case of disappearing machines on remote desktop

## Chapter 1 - Woe is me
It was a sad monday morning when the student found out that the machine they normally used on remote desktop had disappeared. 
Thinking that it may just be a small problem with the specific machine, they decided to try redownload all the software onto a new machine. 
However, at around halfway through the steps of [Brian Lovell's fantastic software installation guide](https://lovellbrian.github.io/2023/10/02/BYODImage.html), 
the student attemped to logout of the computer for a software installation and ultimately found that this time the new machine has disappeared 
from the remote desktop as well. Slighty sad and confused after being ghosted by 2 different machines, the student attempts the redownloads 
with a third machine. After running into the exact same problem a second time, the student decides to try something different. On the next 
attempt it was found that when installing Docker Desktop onto the machine, the user would be prompted to logout of the machine to finish the 
installation. But this was the trap! The user actually had to call `shutdown /r` from the terminal instead. 
After finding the issue, the student felt happy that they were able to get things working. But alas, precious hours were wasted, 
and the student worries for the future problems they will face in the course...

The end
