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
  Now chmod the shellscript into an executable file using following command 
  ```sh
  sudo chmod +x ./windows.sh
  ```

## Step 5
  ```sh
  which efibootmgr
  ```
by using this command you can know the directory which looks some thing like this

![image](https://github.com/user-attachments/assets/985da6bb-4ea7-4272-ac74-86021e6437c3)

Note that down we need that in furthur steps 

## Step 6
  ```sh
  sudo nano /etc/sudoers.d/sudo-exempt
  ```

  Now enter the following thing in that file 
  ```sh
  %wheel ALL=(root) NOPASSWD: /usr/sbin/efibootmgr
  ```
now execute the file which will surely take boot you back to the windows 

## Step 7 (optional step)
  Open steam and go to library
  
  Now click add non steam games and browse the .sh and add
  
  After adding that which will looks something like below
  
  ![image](https://github.com/user-attachments/assets/f4c950ed-fa8c-4e36-afd0-b756c8ab7e8e)

  This completely optional 
