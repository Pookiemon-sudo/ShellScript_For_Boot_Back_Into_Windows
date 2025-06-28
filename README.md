# 🚀 Shell Script: Boot Back Into Windows with One Click!

**Easily reboot from Linux straight into Windows with a simple shell script.**  
Perfect for dual-booters who want a seamless experience!

---

## 📝 What You’ll Do

- Create a script that sets Windows as the next boot target
- Make it executable with a click or a command
- (Optional) Add it to Steam as a “game” for super easy access!

---

## 🛠️ Step 1: Prepare the Script
  Download the windows.sh and open in text editor of your preference
  ```sh
  sudo efibootmgr -n **
  reboot
  ```
  it might look like something like this save this we need this for later time 

## 🔍 Step 2: Find Your Windows Boot Number
  Open Konsole or Terminal in your favourite Linux distro and enter the following comment 
  ```sh
  efibootmgr
  ```
![image](https://github.com/user-attachments/assets/7d283364-f352-49eb-a0cc-a78de45e541b)

This will look something like this

Note down the boot order number which will look something like this (mine is 23)

![image](https://github.com/user-attachments/assets/f7168da1-1dc5-47f7-92d1-11251c4926d7)

## ✏️ Step 3: Update the Script
  Now open the windows.sh in text editor and delete the ** and add your bootorder value 
  The changes looks something like following 
  ```sh
  sudo efibootmgr -n 23
  reboot
  ```
## ✅ Step 4: Make the Script Executable
  Now chmod the shellscript into an executable file using following command 
  ```sh
  sudo chmod +x ./windows.sh
  ```

## 🔒 Step 5: Allow Passwordless efibootmgr 
  ```sh
  which efibootmgr
  ```
by using this command you can know the directory which looks some thing like this

![image](https://github.com/user-attachments/assets/985da6bb-4ea7-4272-ac74-86021e6437c3)

Note that down we need that in furthur steps 

## 🚦 Step 6: Run the Script!
  ```sh
  sudo nano /etc/sudoers.d/sudo-exempt
  ```

  Now enter the following thing in that file 
  ```sh
  %wheel ALL=(root) NOPASSWD: /usr/sbin/efibootmgr
  ```
now execute the file which will surely take boot you back to the windows 

## 🎮 Step 7: (Optional) Add to Steam for One-Click Access
  Open steam and go to library
  
  Now click add non steam games and browse the .sh and add
  
  After adding that which will looks something like below
  
  ![image](https://github.com/user-attachments/assets/f4c950ed-fa8c-4e36-afd0-b756c8ab7e8e)

  This completely optional.

## 🎉 You’re Done!

Now you can jump from Linux to Windows with a single click or command.  
Happy dual-booting!

---

**Tip:**  
You can further customize this script or create similar ones for other OSes or boot targets!

*If you found this helpful, star ⭐ the repo and share with fellow dual-booters!*

