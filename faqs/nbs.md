By using CodeUtilities, you can import .nbs files which contains data for noteblock music, to your DiamondFire plot!

First, there are two things you should know:
- **Music Player**  
  … which contains the codes needed to play music from imported nbs music data.
- **Music Data Functions**  
  … which contains the data of nbs music. CodeUtilities will generate Music Data Functions from your nbs files.

Now, I'll show you how to import music to DiamondFire plots!  
Make sure you are in dev mode! (`/dev`)
1. Setup the **Music Player**:
    1. Get Music Player Pack by typing `/nbs player` on your chat screen. You will receive a jukebox item in your hotbar.
    2. Place down the jukebox item you got (in your codespace), and open the chest that appears after you placed it.
    3. There should be two ender chests and one glowing jukebox inside the chest you opened. Pick all of them.
    4. Place down each item in your codespace, and some code will appear when you place it.
    5. Music Player setup done!
2. Import a **Music Data Function**:
    1. Put a .nbs file you want to import in `%appdata%/.minecraft/CodeUtilities/NBS Files` folder.
    2. Go back to Minecraft, and type `/nbs load <file name>` on your chat screen. Make sure to replace \<file name\> with the nbs file name you want to import.  (If importing fails, please read the later section of this page)
    3. After importing finished, you will receive a note block item in your hotbar. Place the item you got in your codespace.
    4. Music Data Function setup done!
3. Finally, play your music:
    1. Place Call Function code and select the Music Data Function you imported.
    2. Place another Call Function code after it, and select `playSong` function.
    3. Music setup done! This should play your music when these two functions are called.

If you want to import more music, repeat Step 2 and 3!

**Music doesn't play!**
Check several things:
1. Are Music Data Function and `playSong` function called?  
   Try playing music right after Player Event: Join. If the music plays, then Music Player is not broken.
2. Did you place all 3 functions inside the Music Player Pack?  
   The functions of the Music Player are `playSong`, `playTick` and `loadSong`. Check that these functions are placed in your codespace.
3. Is the Music Data Function the latest one?  
   Some people get Music Data Functions from DiamondFire plots where players can share their Code Templates. But the person who uploaded the template might be using older CodeUtilities version. Try importing your own nbs file using `/nbs load <file name>`!