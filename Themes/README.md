# Advanced Theming Guide
Before you do any of this, you need some basic understanding of JSON \
(You will most likely need to change some values in the `theme-info.json` file)

### Basic Info
 * Selecting a theme from `Settings/Choose Preset` **doesn't** equip it. It will copy all the content inside of the folder, and paste it in `.user-theme` folder.
 * So if you want to create a completely new theme then you should either:
   * Duplicate a theme folder and change the content there \
   **IMPORTANT:** *(The folders name and `themeName` inside of `theme-info.json` **HAS** to match)*
   * Change the content of the `.user-theme` folder and then save the theme in `Settings/Save Theme`

### Reloading the resources
 * If you want to **reload your resources** you need to select your theme in `Settings/Choose Preset`.
 * If you're working in the `.user-theme` folder, then you can press **ALT + R** to reload the resources. \
 **IMPORTANT:** *(If you select a theme your changes in `.user-theme` won't be saved, so make sure to save it in `Settings/Save Theme`)*

### Replacing resources
 * If you would like to replace **sprites/audio/fonts** you can do that by going to `theme-name/resources` and replace the files there.
 * Try keeping the same resolution for the sprites for the best results.
 * If you would like to replace the **Font of the keys**, then you can add a **new font file** inside `theme-name/resources/fonts`, then set 
 `noteFontPath` in `theme-name/theme-info.json`.

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
   2. Go to `theme-name/theme-info.json` and add the **path** and **BPM of the song** for each `.wav` file in the `menuSongs` list
   3. Reload your resources and it should play a random song from the list
