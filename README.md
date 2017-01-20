Attention
===
Oneplus 3 and Oneplus 3T are shared with the common base code in Github, the only difference are binaries,
so please, DO NOT integrate Oneplus 3T's binaries into Oneplus 3. vice versa, Otherwise, your device will go to black screen...

Downloading the Source  
===
1. Repo sync all code with default.xml  
`repo init -u git://github.com/OnePlusOSS/android.git -b oneplus/QC8996_N`  
`repo sync`  
2. Root your device  
3. Pull the necessary libraries from your device by executing the script `pull_library.sh`  
4. After pull_library.sh be executed, a directory  named "vendor" should be generated. Copy this directory to root of project.

Building the System  
===
**[Set up environment]**  
Initialize the environment with the envsetup.sh script.  git a
`$ . build/envsetup.sh`  
**[Choose a Target]**  
Choose which target to build with lunch.  
`$ lunch`  
      enter **25** for msm8996-userdebug  
      enter **26** for msm8996-user  
**[Build the code]**  
Build everything with make. GNU make can handle parallel tasks with a -jN argument.  
`$ make -j4`  
**[Flash a Device]**  
Let device enter fastboot mode, run  
`$ adb reboot bootloader`  
Once the device is in fastboot mode, run  
`$ fastboot flash boot boot.img`  
`$ fastboot flash system system.img`  
If you want flash new /data partition, run  
`$ fastboot flash userdata userdata.img`

