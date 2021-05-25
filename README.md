# UmpcRaspberry-Cardboard
Using a raspberry pi zero w to create a ultra-mini pocket computer

I built a small pocket computer using off the shelf components:
1. 20000 mAh power bank to supply the pi with power
2. MHS 3.5 inch touchscreen that mounts to the gpio header
3. tiny qwerty [bluetooth keyword](https://www.amazon.com/dp/B01CNKXM54/ref=sspa_dk_detail_2?pd_rd_i=B01CNKXM54&pd_rd_w=Ya7pL&pf_rd_p=085568d9-3b13-4ac1-8ae4-24a26c00cb0c&pd_rd_wg=XMuYI&pf_rd_r=T7F6RFKKFD7B3WC1GBQB&pd_rd_r=6749350c-0253-441b-9c38-f31dbd668cc2&spLa=ZW5jcnlwdGVkUXVhbGlmaWVyPUEzTTJRSEJRRUhENVQzJmVuY3J5cHRlZElkPUEwODIyNjk2M0laWVdPU042NjAyUiZlbmNyeXB0ZWRBZElkPUEwMDc1MTAzMzcwU1lMOFE0OU9SJndpZGdldE5hbWU9c3BfZGV0YWlsJmFjdGlvbj1jbGlja1JlZGlyZWN0JmRvTm90TG9nQ2xpY2s9dHJ1ZQ&th=1)
4. custom carboard case

<h2> creating the umpc case:
</h2>

1. I drew around the bluetooth keyboard and cut out a piece of cardboard for the base. 
2. I cut strips of carboard and duct taped then to the interior of the base to create a holder for the keyboard
3. I measured out the lcd screen and cut a base and sides for its enclosure and duct taped the interior together
4. I created a joint between to the two pieces out of an old colored pencil and some zipties and used masking tape to connect it to both pieces
5. I covered the case in several coats of wood glue and modge podge, to strengthen the carboard and make it more resistant to moisture 
6. I painted the case case green and applied a last coat of clear modge podge

<h2> getting the screen and bluetooth to connect
</h2>

1. I set up the pi adn ran the lcd wiki script for the MHS 3.5 inch screen
2. This caused the main terminal and some virtual terminals to not display correctly
3. So I entered the second virtual terminal and ran 

```
   sudo nano /boot/cmdline.txt
```
4. then changed fbcon=map:10 to

```
   fbcon=map:1
```
5. and that fixed it except it deleted the bluetooth module and now the hciconfig doesn't work, if I find an answer I will kept you posted

