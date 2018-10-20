ANNOUNCEMENT
===
When we launched the OnePlus 3, we started a very interesting tradition, Zero Day sources for our devices. Since then, every device has launched with them.

With the project treble in place, we think the AOSP(Qualcomm) device tree is not as useful or important as it used to be,

based on conversations we had with our dev community and the fact that we have only made few changes on AOSP(Qualcomm BSP) device tree, we will not be releasing AOSP device trees for future devices, the community can get the baseline from our device and get the source code from Qualcomm.

We always have had a great community of developers working on our devices, and we will continue providing support  to our dev community, you can always  get in touch with our team on GitHub

The kernel device-tree will be made available on GitHub and our Dev community working on one plus devices will have access on day one of the releases of the new devices.

Downloading the Source  
===
1. Repo sync all code with default.xml  
`repo init -u git://github.com/OnePlusOSS/android.git -b oneplus6/9.0.0`  
`repo sync`  
2. Root your device  
3. Pull all files from vendor partition
4. After all files pulled, copy these files to vendor/oneplus/vendor.

Building the System  
===
**[Set up environment]**  
Initialize the environment with the envsetup.sh script.  git a
`$ . build/envsetup.sh`  
**[Choose a Target]**  
Choose which target to build with lunch.  
`$ lunch`  
      enter 47. sdm845-userdebug
**[Build the code]**  
Build everything with make. GNU make can handle parallel tasks with a -jN argument.  
`$ make -j4`  
**[Flash a Device]**  
Let device enter fastboot mode, run  
`$ adb reboot bootloader`  
Once the device is in fastboot mode, run  
`$ fastboot --disable-verity flash vbmeta vbmeta.img`
`$ fastboot flash boot boot.img`  
`$ fastboot flash system system.img` 
`$ fastboot flash system vendor.img` 
If you want flash new /data partition, run  
`$ fastboot flash userdata userdata.img`

