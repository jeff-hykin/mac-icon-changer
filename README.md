# What is this?

Its the home of a Mac App you can use to change the icon for certain file extensions.
It is very much not-polished, but it does work.

# How do I use it?

You can download the app by clicking the download button [here](https://github.com/jeff-hykin/mac-icon-changer/blob/master/downloads/DefaultOpener.zip)
To change the icon for a file extension, such as python files
- go to (or create) a file with that extension. Ex: `a_file.py`
- right click and the click "get info"
- find the "open with" section
- change the app to be the "DefaultOpener" app you just downloaded
- click the "change all" button at the bottom of the "open with" section
- NOTE: it might take awhile for the icons to refresh, sometimes even rebooting isn't enough to cause a refresh

Note, by default all files are opened with VS Code.

# How do I customize the icons (the whole point)

Here you'll actually have to get your hands a bit dirty.<br>
- Open up the `DefaultOpener.app` (it is a folder even though Mac makes it look like a file)
- Find the icon you want, e.g. `PYTHON.icns` inside both the `Resources/` folder and the `Contents/Resources` folder.
- Replace it with your own icns file. (Find a online converter if you have a .png or .jpeg)

# How do I change what app it opens with?
- Open up the `DefaultOpener.app` (it is a folder even though Mac makes it look like a file)
- Open up `Contents/Resources/Scripts/main.scpt` **with the Mac Script Editor**.
- NOTE: trying to open up the script with a normal text editor will just show junk because of the file encoding
- Edit the part of the code that says `"Visual Studio Code"` and put whatever app you want


## How do I add an icon for something that isn't in `Resources/`?

I don't know ¯\\\_(ツ)_/¯ 


# How did you create this?
I used an applescript file to create a Mac app that opens things. Then I pulled app-settings from an old Sublime app that was already setting the icons for file extensions.

A copy of the applescript code can be found [here](https://github.com/jeff-hykin/mac-icon-changer/blob/master/main.applescript)
its literally (exactly)
```applescript
on open this_item
    tell application "Visual Studio Code"
        open this_item
    end tell
end open
```

<br>
<br>

### How could this be done better?
Maybe in the future I'll make an electron app that utilizes [file associations](https://www.electron.build/configuration/configuration#PlatformSpecificBuildOptions-fileAssociations) to accomplish this in a user-friendly way