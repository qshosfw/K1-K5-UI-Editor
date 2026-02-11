
1. Interface Overview
Top Bar: Control center for visual settings. Includes canvas resizing buttons (Quick Dims), Clean Canvas (C), and UI theme toggles.
Canvas (Center): Your primary drawing workspace. It features a coordinate grid to help you place pixels accurately.
Sidebar (Right): The code processing zone. The Top Text Box is for Input (pasting code to draw). The Bottom Text Box is for Output (getting the code from your drawing).

2. Basic Controls & Drawing
LMB (Left Mouse Button): Draws a pixel (fills it with color).
RMB (Right Mouse Button): Erases a pixel (returns it to background color).
Straight Lines: Click a starting point, then hold Shift and click the end point. The program will automatically calculate and draw a perfect line between them.
Zooming: Use the Mouse Wheel to scale the canvas. This is crucial for precise pixel work.
Undo System: Press Ctrl + Z to step back. The editor remembers your last 10 actions.
Quick Cleaning: Press the C key or click "CLEAN CANVAS" to wipe everything instantly.

3. Display & Grid Settings
SCALE: Changes the size of the pixel squares on your monitor.
RATIO: Adjusts pixel height. Set to 1.45 by default to match the physical aspect ratio of target LCD screens.
L-GRID: Toggles "Page Lines." Since display memory is often managed in 8-bit vertical chunks, these lines show you exactly where each byte boundary lies.
Themes: Use B, O, W for Blue, Orange, or White styles. INV swaps the "ink" and "paper" colors. Use the 🎨 icon to pick a custom accent color.
Quick Dims: Use 7x16, 10x16, 6x8, 3x5 to instantly crop the workspace to standard font sizes. Use RESET to return to the full 128x64 resolution.

4. Working with Code (Import/Export)
How to Edit Existing Code: Copy your array (e.g., {0x1F, 0x2E...}) and paste it into the Top Input Box. Click the canvas to refresh. 
The parser is smart: it ignores comments like /*0x00*/ and extracts only the relevant data.
How to Save Your Work: Draw your icon, then click HEX or BINARY. The code will appear in the Bottom Output Box. Use COPY CODE to grab it immediately.
Status Mode: The STATUS button generates specific code for status-line updates: gStatusLine[index] |= 0xValue;.

5. Mastering MULTI Mode (The Stamp Tool)
This mode allows you to "stamp" long sequences of characters or icons onto the canvas without manually drawing each one.
Step 1: The Input: Paste a large block of code containing multiple bracketed sets, like {char1}, {char2}, {char3} into the Top Input Box.
Step 2: Activation: Click the MULTI button. It will stay active until you click it again.
Step 3: Setting the Gap: In the SPACE field, enter a number (e.g., 2). This is the distance in pixels that will be automatically placed between each character.
Step 4: The Placement: Click LMB anywhere on the canvas. The entire sequence from the input box will be "stamped" starting from that exact pixel. The program automatically 
detects if the character is 8 or 16 pixels high.
Step 5: Adding More: This is key—you can add to your drawing without starting over. Simply delete the text in the input box, paste a new icon code, and click a different spot on the canvas.
 The new icon will appear while the previous ones remain exactly where they were.
Pro-Tips: If you stamp a sequence in the wrong spot, Ctrl + Z removes the entire group in one go. If your string is longer than 128 pixels, it will be safely clipped at the edge. 
Use the POS indicator (bottom left) to find the perfect starting X/Y coordinates before you click.

6. Summary Checklist for Success
Paste your code blocks {...} into the Input Box. 
2. Enable MULTI mode and set your SPACE gap. 
3. Click the canvas to "stamp" the sequence. 
4. To add more without erasing, just swap the code in the Input Box and click again in a new location. 
5. Once the screen looks perfect, click HEX to generate the final combined data array for your firmware.
