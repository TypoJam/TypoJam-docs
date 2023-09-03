# Advanced Theming Guide
Before you do any of this, you need some basic understanding of JSON \
(You will most likely need to change some values in the `theme-info.json` file)

### Basic Info
 * Selecting a theme **doesn't** equip it. It will copy all the content inside of the folder, and paste it in `.user-theme` folder.
 * So if you want to create a completely new theme then you should either:
   1. Duplicate a theme folder and change the content there
   2. Change the content of the `.user-theme` folder and then save the theme inside the **Settings** tab

### Reloading the resources
 * By pressing **CTRL + R** you can reload the resources inside of `.user-theme`.
 * This doesn't reload the `menu-songs` immediately, you will have to reload the menu by either:
   * Clicking on the **Map Editor** then back to the menu
   * Playing a map, then going to the menu from there
   * Relaunching the game *(All resources immediately reload after relaunching the game)*

### Replacing resources
 * If you would like to replace **sprites/audio/fonts** you can do that by going to `theme-name/resources` and replace the files there.
 * Try keeping the same resolution for the sprites, though it *shouldn't* matter.
 * If you would like to replace the Font of the keys, then you can add a new font in `theme-name/resources/fonts`, then set the fonts path in `theme-name/theme-info.json`.

### Changing pixels per unit
 * You can change the **pixels per unit** for each **sprite** if you want to. *(Default value is 100)*
 * The **pixels per unit** change the number of pixels in the **sprite** that correspond to one unit in world space.

### Changing the borders of the sprites
 * You pretty much only want to do this with the `button-sprite`.
 * if you don't change the resolution of the image, you **DON'T** have to follow these steps.
 * To change the border all you need to do is:
   1. Get your **sprite** resolution
   2. Divide it by 2
   3. Subtract 1
   4. Summary: **Sprite Resolution / 2 - 1**
   5. Add this number to all 4 sides *(Left, Top, Right, Bottom)*

### Changing the songs in the menu
 * You can add as many songs for the **Main Menu** as you want, it will always pick one randomly and loop it.
 * To add songs follow these instructions:
   1. Go to `theme-name/resources/audio/menu` and add your audio file(s) there *(Note: the file can only be a `.wav`)*
   2. Go to `theme-name/theme-info.json` and add the **path** and **BPM of the song** for each `.wav` file in the `menuSongs` array
   3. Reload the **Main Menu** in the game and it should play a random song from the list