# UmpcRaspberry-Cardboard
Using a raspberry pi zero w to create a ultra-mini pocket computer
<h2> Images
</h2>

![umpc off and open](/images/20210524_155739.jpg)
![umpc closed](/images/20210524_155746.jpg)
![umpc open and on](/images/20210524_155916.jpg)
![umpc open and on and typing](/images/20210601_203316.jpg)

I built a small pocket computer using off the shelf components:
1. 20000 mAh [power bank](https://www.amazon.com/ENEGON-Portable-20000mAh-Charger-Battery/dp/B083QCGPHZ/ref=asc_df_B083QCGPHZ/?tag=hyprod-20&linkCode=df0&hvadid=416804729915&hvpos=&hvnetw=g&hvrand=2400125951467309697&hvpone=&hvptwo=&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=1020414&hvtargid=pla-877205369897&psc=1&tag=&ref=&adgrpid=96943124074&hvpone=&hvptwo=&hvadid=416804729915&hvpos=&hvnetw=g&hvrand=2400125951467309697&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=1020414&hvtargid=pla-877205369897) to supply the pi with power
2. MHS 3.5 inch [touchscreen lcd](https://www.amazon.com/dp/B01CNKXM54/ref=sspa_dk_detail_2?pd_rd_i=B01CNKXM54&pd_rd_w=Ya7pL&pf_rd_p=085568d9-3b13-4ac1-8ae4-24a26c00cb0c&pd_rd_wg=XMuYI&pf_rd_r=T7F6RFKKFD7B3WC1GBQB&pd_rd_r=6749350c-0253-441b-9c38-f31dbd668cc2&spLa=ZW5jcnlwdGVkUXVhbGlmaWVyPUEzTTJRSEJRRUhENVQzJmVuY3J5cHRlZElkPUEwODIyNjk2M0laWVdPU042NjAyUiZlbmNyeXB0ZWRBZElkPUEwMDc1MTAzMzcwU1lMOFE0OU9SJndpZGdldE5hbWU9c3BfZGV0YWlsJmFjdGlvbj1jbGlja1JlZGlyZWN0JmRvTm90TG9nQ2xpY2s9dHJ1ZQ&th=1) that mounts to the gpio header
3. tiny qwerty [bluetooth keyword](https://www.amazon.com/Pocket-Mini-Bluetooth-Wireless-Keyboard/dp/B088K8RXYQ/ref=pd_sbs_4?pd_rd_w=WFej6&pf_rd_p=98101395-b70f-4a52-af63-8fac2c513e02&pf_rd_r=Y35HHFAM8ZYTAE7R5TM5&pd_rd_r=7e1487a1-1120-4026-8b2a-461cf28d52b7&pd_rd_wg=VDDK3&pd_rd_i=B088K8RXYQ&psc=1)
4. custom carboard case

<h2> Creating the UMPC case:
</h2>

1. I drew around the bluetooth keyboard and cut out a piece of cardboard for the base. 
2. I cut strips of carboard and duct taped then to the interior of the base to create a holder for the keyboard.
3. I measured out the lcd screen and cut a base and sides for its enclosure and duct taped the interior together.
4. I created a joint between to the two pieces out of an old colored pencil and some zipties and used masking tape to connect it to both pieces.
5. I covered the case in several coats of wood glue and modge podge, to strengthen the carboard and make it more resistant to moisture.
6. I painted the case case green and applied a last coat of clear modge podge.

<h2> Getting the screen and bluetooth to connect
</h2>

1. I set up the pi and run the lcd wiki [script](http://www.lcdwiki.com/MHS-3.5inch_RPi_Display) for the MHS 3.5 inch screen
2. This caused the main terminal and some virtual terminals to not display correctly
3. So I entered the second virtual terminal and ran 

```
   sudo nano /boot/cmdline.txt
```
4. Then I changed fbcon=map:10 to

```
   fbcon=map:1
```
5. And that fixed it except it deleted the bluetooth module.
6. So you have to change a parameter in /boot/config.txt

```
   sudo nano /boot/config.txt
```
7. Then you add
```
   dtoverlay=miniuart-bt
```
8. This seems to make the bluetooth device controller appear and then you can use a [guide](https://www.cnet.com/how-to/how-to-setup-bluetooth-on-a-raspberry-pi-3/) to further set up the bluetooth

