# Add/Remove Context Menu for `.264` File Conversion to `.mp4`
This repository contains two `.reg` files for modifying the Windows context menu to add or remove an option for converting `.264` video files to `.mp4` using FFmpeg.

## **Files in This Repository**
- **`add-to-context-menu.reg`**: Adds a "Convert to MP4" option to the right-click context menu for `.264` files.
- **`remove-from-context-menu.reg`**: Removes the "Convert to MP4" option from the right-click context menu for `.264` files.

## **Prerequisites**
### **1. FFmpeg Installation**
The conversion process relies on [FFmpeg](https://ffmpeg.org/), a powerful command-line tool for handling video and audio files.

#### **Steps to Install FFmpeg**:
1. Download FFmpeg from the [official website](https://ffmpeg.org/download.html).
2. Extract the downloaded archive to a directory (e.g., `C:\ffmpeg`).
3. Add the `bin` folder to your system's `PATH` environment variable:
   - Open `Edit the system environment variables > Advanced > Environment Variables`.
   - Find the `Path` variable under "System variables" and click **Edit**.
   - Add the full path to the `bin` folder (e.g., `C:\ffmpeg\bin`).
4. Verify the installation by opening Command Prompt and typing:
   ```
   ffmpeg -version
   ```
   You should see FFmpeg's version information.

> **Note**: By adding FFmpeg to your system's `PATH`, you can run `ffmpeg.exe` from any directory without specifying its full location.

## **How to Use the `.reg` Files**
### **1. Add the Context Menu**
1. Double-click the `add-to-context-menu.reg` file.
2. Click **Yes** when prompted to modify the Registry.
3. Right-click any `.264` file, and you should see a "Convert to MP4" option.
4. Selecting this option will convert the `.264` file to `.mp4` in the same directory using FFmpeg.

### **2. Remove the Context Menu**
1. Double-click the `remove-from-context-menu.reg` file.
2. Click **Yes** when prompted to modify the Registry.
3. The "Convert to MP4" option will no longer appear in the context menu for `.264` files.

## **How It Works**
- The `add-to-context-menu.reg` file creates a context menu entry for `.264` files.
- When you right-click a `.264` file and select "Convert to MP4," it runs the following FFmpeg command:
  ```
  ffmpeg.exe -i "input.264" -c:v copy "input.mp4"
  ```
  - `"%1"`: Refers to the full path of the selected `.264` file.
  - `"%~dpn1.mp4"`: Automatically sets the output file name and location, replacing the `.264` extension with `.mp4`.

## **Troubleshooting**
- **No Context Menu Option Appears**: Ensure the `.reg` file was successfully imported.
- **Conversion Doesn't Work**: Check if FFmpeg is installed correctly and accessible from the command line (`ffmpeg -version`).

## **Disclaimer**
Use these `.reg` files with caution. Always back up your Registry before applying changes. The author is not responsible for any issues caused by modifying the Registry.

## **Contact** ✉
- E-mail: [velimir.paleksic@gmail.com](velimir.paleksic@gmail.com).
- VexSystems GitHub: [github.com/vexsystems](https://github.com/vexsystems).
- VexSystems Instagram: [@vex.systems](https://www.instagram.com/vex.systems/).