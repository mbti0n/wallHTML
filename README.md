# wallHTML
HTML to wallpaper

## HTML code
```HTML
<!DOCTYPE html>
<html>
<body style="background-color:(#hex_code);"><head>
<meta name="viewport"
content="width=device-width, initial-scale=1">
<style>
.circle1 {
  height: 1000px;
  width: 1000px;
  background-color: rgb(r, g, b);
  border-radius: 50%;
  position: absolute;
  top: x%;
  left: 40%
  }
.circle2 {
  height: 1000px;
  width: 1000px;
  background-color: rgb(r, g, b);
  border-radius: 50%;
  position: absolute;
  top: x%;
  left: 40%
  }
.circle3 {
  height: 1000px;
  width: 1000px;
  background-color: rgb(r, g, b);
  border-radius: 50%;
  position: absolute;
  top: x%;
  left: 40%
  }
.circle4 {
  height: 1000px;
  width: 1000px;
  background-color: rgb(r, g, b);
  border-radius: 50%;
  position: absolute;
  top: x%;
  left: 40%
  }
.circle5 {
  height: 1000px;
  width: 1000px;
  background-color: rgb(r, g, b);
  border-radius: 50%;
  position: absolute;
  top: x%;
  left: 40%
  }
.circle6 {
  height: 1000px;
  width: 1000px;
  background-color: rgb(r, g, b);
  border-radius: 50%;
  position: absolute;
  top: x%;
  left: 40%
  }
</style>
</head>
<div class="circle1"></div>
<div class="circle2"></div>
<div class="circle3"></div>
<div class="circle4"></div>
<div class="circle5"></div>
<div class="circle6"></div>
</body>
</html>
```

## Parts of my Python code
### Set as desktop and logon wallpaper (macOS, tested on Ventura)
```python
html_file_path = {html_file_path}
output_image_path = {output_path}
# Configure the output image resolution
options = {
    'format': 'jpg',
    'width': 5120,  # Specify the desired width of the image
    'height': 2880,  # Specify the desired height of the image
}

# Convert the HTML file to an image
imgkit.from_file(html_file_path, output_image_path, options=options)

# Path to the image you want to set as the wallpaper

image_path = {path_to_the_image}

# AppleScript command to set wallpaper
applescript_cmd = f'''
tell application "System Events"
    tell current desktop
        set picture to "{image_path}"
    end tell
end tell
'''

# Execute the command
os.system(f"osascript -e '{applescript_cmd}'")
```

### Set as desktop wallpaper (Windows 10/11)
```python
# Configure the output image resolution
options = {
    'format': 'jpg',
    'width': 5120,  # Image width
    'height': 2880,  # Image height
}

# Convert the HTML file to an image
imgkit.from_file(html_file_path_windows, output_image_path_windows, options=options)

SPI_SETDESKWALLPAPER = 20
WALLPAPER_PATH = {path_to_your_wallpaper}  # Replace with the actual path to your wallpaper image

# Set the wallpaper
def set_wallpaper():
    ctypes.windll.user32.SystemParametersInfoW(SPI_SETDESKWALLPAPER, 0, WALLPAPER_PATH, 3)

if __name__ == '__main__':
    set_wallpaper()
```
### Set as lock screen wallpaper (Windows 10/11)
```python
os.system (f"cmd /k \"cd {path of wallHTML.py} & igcmdWin10.exe setlockimage \"{WALLPAPER_PATH}\" & exit\"")
```
Make sure to replace the directory for the code to your corresponding directory for `igcmdWin10.exe` and `wallHTML.py`. `igcmdWin10.exe` must be in the same folder as `wallHTML.py`.


## Output
### HP Laptop 14-ck0xxx
14", 1366x768

![image](https://github.com/mbti0n/wallHTML/assets/105599214/cd2a5076-d633-4141-b8bc-6f75822f9826)

### Lenovo IdeaCentre AIO 3i 24"
24", 1920x1080

![image](https://github.com/mbti0n/wallHTML/assets/105599214/f3ab1bfb-3fc0-4213-a090-3e559d4cd616)

### MacBook Air 13" M2
13.6", 1710x1112 (notched, using TopNotch to hide the notch with a black area)

<img width="1710" alt="image" src="https://github.com/mbti0n/wallHTML/assets/105599214/a3f6cb19-f91d-497e-9415-dc3fdf9ac2f6">

