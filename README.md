# Garry's Mod Easy Addon Uploader

## Instructions

1. Create *the folder of your addon* in *garrysmod\addons* and place your files in it. If your addon is already there then ignore this step.

2. Create a thumbnail for your addon: picture of 512x512 pixels.
Save it as a JPEG image in *the folder of your addon* and name it the same as *the folder of your addon*.
Choose quality 100 if possible.
The [chroma subsampling](https://en.wikipedia.org/wiki/Chroma_subsampling) must be **4:2:0** (for instance GIMP and Photoshop can use 4:2:2 or 4:4:4).

3. Place *Upload.cmd* in *the folder of your addon*.

4. Run *Upload.cmd* and follow instructions **until the window closes automatically**.

When you want to update, just run *Upload.cmd* and enter the reason (with only US-ASCII characters). Your addon must contain the files *addon.json* and *workshop_id.cmd*.

If you do not want to place the addon in your *garrysmod\addons* folder then you need to make sure that the *GarrysMod* path is correct by editing *Upload.cmd*.

## Common issues

* *GMad* tells me that I have files that are not allowed by whitelist!
 1. Remove useless files or blacklist them with the `"ignore"` section of your *addon.json*.
 2. **Models** must be placed somewhere in the *models* folder.
 3. **Sounds** must be placed somewhere in the *sound* folder.
 4. **Materials, textures and PNG images** must be placed somewhere in the *materials* folder.
 5. **Lua scripts** must be placed somewhere in the *lua* folder.
 6. **Vehicle scripts** must be placed in the *scripts\vehicles* folder.
 7. **Fonts** must be placed in the *resource\fonts* folder.
 8. etc.
* I accidentally closed the window when it asked for the UID, I removed the *workshop_id.cmd*, or I mistyped the UID!
 1. Create or edit the file *workshop_id.cmd*
 2. Place this code inside: `set WorkshopId=000000000`
 3. Replace `000000000` by the UID of your addon. You can see it in the URL of your Workshop addon.
* I made a mistake in my *addon.json*, how do I re-generate it?
 1. Remove *addon.json*. You will have to enter information again.
* *GMad* tells me that I have uppercase characters, spaces or whatever forbidden in filenames!
 1. Simply rename everything including extensions to make them: lowercase, no accents, no spaces.
 2. If you rename models, you really should modify your QC script and re-generate the model (bug with *Entity:GetModel()* clientside).
 3. If you rename textures, do not forget to modify VMTs that need them.
 4. Of course, do not forget to update your scripts in order to match with the new filenames.
* *GMPublish* returns an error that I do not understand after uploading!
 1. You probably put accents / special characters in the title of your addon. The Windows console does not use the UTF-8 character set, so it generates illegal UTF-8 sequences. Please remove accents or edit your *addon.json* as UTF-8.
 2. The change note must not contain accents either for the same reason. Please do not type accents.

## Links

* [GMad usage](https://www.facepunch.com/showthread.php?t=1242185)
* [GMPublish usage](https://www.facepunch.com/showthread.php?t=1244179)
