# UmpcRaspberry-Cardboard
Using a raspberry pi zero w to create a ultra-mini pocket computer

I built a small pocket computer using off the shelf components:
1. 10000 mAh power bank to supply the pi with power
2. MHS 3.5 inch touchscreen that mounts to the gpio header
3. tiny qwerty bluetooth keyword
4. custom carboard case

<h2> creating the umpc case:
</h2>1. I drew around the bluetooth keyboard and cut out a piece of cardboard for the base.
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

<h2> Note running the Lcd script for 
