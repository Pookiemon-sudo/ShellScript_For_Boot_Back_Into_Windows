# ShellScript_For_Boot_Back_Into_Windows

### This git repo teaches you to how to create a .sh file in your prefered linux distro to boot back into windows (we assume that you dual booted your pc) 

#### There will be some small steps to perform then you can get right into your windows install just a click of a botton 

## Step 1
  Download the windows.sh and open in text editor of your preference
  ```sh
  sudo efibootmgr -n **
  reboot
  ```
  it might look like something like this save this we need this for later time 

## Step 2 
  Open Konsole or Terminal in your favourite Linux distro and enter the following comment 
  ```sh
  efibootmgr
  ```
![image](https://github.com/user-attachments/assets/7d283364-f352-49eb-a0cc-a78de45e541b)

This will look something like this

Note down the boot order number which will look something like this (mine is 23)

![image](https://github.com/user-attachments/assets/f7168da1-1dc5-47f7-92d1-11251c4926d7)

## Step 3
  Now open the windows.sh in text editor and delete the ** and add your bootorder value 
  The changes looks something like following 
  ```sh
  sudo efibootmgr -n 23
  reboot
  ```
## Step 4
