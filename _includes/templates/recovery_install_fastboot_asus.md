## Unlocking the bootloader

{% include note.html content="The steps below only need to be run once per device." %}

{% include warning.html content="Once you unlock this device you will no longer receive updates from Asus and your Warranty will be void, please read the notice on screen now for more details." %}

1. On your phone visit the [asus.com/support](https://www.asus.com/support).
2. Enter your phone name into the search bar and go into the device support page.
3. Scroll down and go into **Driver & Tools**.
4. Scroll down again and under "Please select OS" select `Android`.
5. Now select **Utilities**.
6. Now go to the "Unlock Device App: Unlock boot loader" box and read the "Notice".
7. Once you are happy with what it tells you, download the apk by clicking the `Global` link.
8. A message may come up saying "This type of file can harm your device...", tap **ok**.
9. The apk should be called "UnlockApp_[devicetype]_[dateofcreation].apk".
9. Make sure to allow for Unknown Sources to be installed in `Settings` > `Security`.
10. Install the apk by allowing it access to certain permissions.
11. Now run the app on your phone.
12. Read through the "End User License Agreement" and tick the box that confirms "I have read and agree to all the terms and conditions of the License Agreement".
13. Again read the notice.
14. Once you are happy with the notice, tap **Agree** and then tap **Press to unlock your device**.
15. If you have a lock screen password it will ask for that to be entered.
16. The device will now power off and go into the bootloader where it will flash some of the files associated with locking the bootloader.
17. The device will restart again and if a white Asus boot screen comes up then you have successfully unlocked the bootloader on your device.

## Updating the bootloader using `fastboot`

{% include note.html content="You only need to do this section if the line on your bootloader --continue to fastboot process-- is blue, if it is green then skip this section and move onto the section Installing a custom recovery using fastboot" %}

1. Make sure your computer has working [fastboot and adb]({{ "adb_fastboot_guide.html" | relative_url }}).
2. Shut down your phone.
3. Press the On button and the Volume Up button to enter the bootloader.
4. You should now see the bootloader screen.
5. Connect your device to your PC.
6. On your PC visit [theflamingskull.com/zenfone2](http://theflamingskull.com/zenfone2.html).
7. Scroll down to the "MM BOOTLOADER/FIRMWARE" section and download the MM bootloader that suits your device.
8. Extract the zip using your favourite extraction tool.
9. Now go into the folder that you have extracted and move into the `tools` folder.
10. Open a terminal in this folder (terminal for Linux/MacOs, CMD for Windows) and type the following command:

        fastboot devices

11. Your device should show up here.  If it does not you may have not installed fastboot correctly or your system may have problems detecting your device.
12. Now go back up to the M_BL_upgrade folder (the containing folder of `tools`) and run the relevent script based on your system. (Linux - upgrade_linux.sh, Windows - upgrade.bat, MacOs - upgrade_mac.sh)
13. Your phone will restart a few times and your PC will install the Marshmallow bootloader files.
14. Once it has finished, check the bootloader screen again on your phone (Power Button + Volume Up)  and the line `continue to fastboot process` should now be green.  You have now successfully updated your bootloader to Marshmallow.

{% include templates/recovery_install_fastboot_generic.md %}
