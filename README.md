# **Create a macOS Installer ISO from Installer Application**
###### This can be used for virtual machines or to be installed regularly. Only usable on macOS devices. For [The VMware Center](https://youtube.com/@VMwareCenter).
##### If you want to download a macOS ISO directly, or don't have a Mac, go to [this link](https://link.com) for a list of all the macOS ISOs and download them. 
### **Step 1** - Download a macOS Installer
If you don't already have a macOS Installer app, follow [this link](https://link.com) to get instructions and links to download them. 
### **Step 2** - Create the ISO
First of all, open the Terminal app (which can be found in the ```Applications``` folder). Next, enter these lines of code to create the ISO from the installer app. **Your macOS Installer app must be in your Applications folder for this to work.** You may have to enter your login passcode for some of these commands, but they are strictly used to create the ISO. You may have to wait a while for these commands as well. 

1. ```sudo hdiutil create -o /tmp/BigSur -size 16384m -volname BigSur -layout SPUD -fs HFS+J```

2. ```sudo hdiutil attach /tmp/BigSur.dmg -noverify -mountpoint /Volumes/BigSur```

3. ```sudo /Applications/Install\ macOS\ Big\ Sur.app/Contents/Resources/createinstallmedia --volume /Volumes/BigSur --nointeraction```

4. ```hdiutil eject -force /Volumes/Install\ macOS\ Big\ Sur```

5. ```hdiutil convert /tmp/BigSur.dmg -format UDTO -o ~/Desktop/BigSur```

6. ```mv -v ~/Desktop/BigSur.cdr ~/Desktop/BigSur.iso```

7. ```sudo rm -fv /tmp/BigSur.dmg```
