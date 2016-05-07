# TeamWin Recovery Project 3.X.X for Huawei Honor 4C / 4X
<b>Target Device: </b>Huawei Honor 4C / 4X  
<b>Target Board: </b>HiSilicon Kirin 620 (hi6210sft)

### Preparing Build Environment and Syncing the OmniROM sources
* Fortunately for you, there is a great guide to achieve that .  
   _For OmniROM_: http://docs.omnirom.org/Setting_Up_A_Compile_Environment
  
### How to build and flash?
1. You'll first need to clone this device tree to download the files needed to build the recovery.
  * _cd_ to the _device_ directory in your main work folder (where you have synced CM or OmniROM sources)  
  `cd device`
  * Create a new folder _huawei_  
  `mkdir huawei`
  * Clone this repository  
  `git clone https://github.com/muhammadfahadbaig/android_device_huawei_cherry/ cherry`  
2. _cd_ back to your main work folder. Prepare device specific source code  
  `source build/envsetup.sh && lunch omni_cherry-userdebug`
3. Finally, build the image!  
  `make -j# recoveryimage` _replace # with your total host cpu cores + 1_
4. Your recovery image will be located at `out/target/product/cherry/recovery.img`
5. Use _fastboot_ to flash the recovery `fastboot flash recovery recovery.img`
