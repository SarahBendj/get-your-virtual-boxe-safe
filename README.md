# get-your-virtual-boxe-safe

While securing a Linux environment may seem unobvious,though it's crucial because Linux systems are not immune to security vulnerabilities, based on a recent experience, here are some tips you can follow to enhance the security of your Linux environment:


## EASY & LAZY STEPS 

### CHECK THE ACCESS PERMISSION OF YOUR BROWSER
You have to make sure that your broswer isn't letting some unknown site some freedom or access

##### GO TO YOUR [SETTINGS !](chrome://settings/content)


### KEEP YOUR BROWSER UPDATED

``` bash 
wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | sudo apt-key add - 
sudo sh -c 'echo "deb http://dl.google.com/linux/chrome/deb/ stable main" >> /etc/apt/sources.list.d/google-chrome.list'
sudo apt-get update 
sudo apt-get install google-chrome-stable
sudo apt-get --only-upgrade install google-chrome-stable 
```


### USE SMART EXTENSIONS 
There are so many extentions available that could help having some  of privacy & I would highly recommend the following browser extensions.

- Ad Blockers storing search history.
- HTTPS Everywhere
- GHOSTERY
- NOSCRIPT
### INSTALL AN ANTIVARUS
ClamAV® is an open-source  anti-virus it's a command-line scanner and an advanced tool for automatic database updates.
One
#### COMMANDLINE 

Run these command in your terminal

1- Installation

```bash 
sudo apt-get upgdate ## preparing your packages by updating them
sudo apt-get install clamav clamav-daemon  ## installing your antivarus package
clamav --version ##checking the version if it exists
sudo systemctl stop clamav-freshclam ##  Stopping the service is necessary to ensure a clean update.
sudo freshclam ##  updates the ClamAV database by fetching the latest virus definitions from the internet
sudo systemctl stop clamav-freshclam ## restart the automatic updates of Clamav databases 

```
2- Display clamAV icon
```bash 
sudo clamtk
```
3-Running scan

```bash 
sudo clamscan--infected --recursive --remove /
```
#### WHAT THIS IS ABOUT 
|command| explaination|
|-------|-------------|
|--infected |Select infected directories only. |
|--recursive|not only to the top-level directory but also to all its subdirectories and their subdirectories.| 
|--remove  | detele them.   |
| / |  starting from the root. |


Or simply using the  application that now you have since you ran the second bloc command sudo clamtk"

Notice
- That you can use any path you want.
- Some data might be deleted ,if somehow infected (save your data before running scan).
- The duration of the scan line code can vary depending on the size of your files and directories, as well as the presence of any infected files.