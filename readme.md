
# Converting Minecraft texture pack from Java to Bedrock version

### Differences between Java and Bedrock
As noted in [Microsoft page](https://learn.microsoft.com/en-us/minecraft/creator/documents/convertingtexturepacks?view=minecraft-bedrock-stable) there are several differences. To compare the versions the best way is to [download for the most recent Bedrock Edition resource pack](https://github.com/Mojang/bedrock-samples/releases). 

In the downloaded source code navigate to */resource_packs/textures*. This is the content of the Bedrock texture pack. 

### Using tools for conversion
Although it is possible to manually change the directory structure, naming conventions, file extensions etc. we can speed up the process by using [ConvertJavaTextureToBedrock](https://modifiedcommand.github.io/ConvertJavaTextureToBedrock/) online tool. This is open source and requires no upload of files and works directly in the browser. Drag and drop the Java texture pack and you will recieve the Bedrock compatible pack. To install it, change the *.zip* extension to *.mcpack* and execute it.

However after installing this texture pack on Bedrock there might be some textures missing - they are be replaced by vanilla textures.

### Fixing the Bedrock pack
To fix the issue of missing textures you need to check the differences between the texture pack and mentioned [recent Bedrock Edition resource pack](https://github.com/Mojang/bedrock-samples/releases).

In my case  (Minecraft version 1.20) there were two directories missing in the converted pack - *textures/blocks/deepslate* and *textures/blocks/candles*.

![diff](https://github.com/umfy/convert-minecraft-texture-pack/assets/39531680/3d586057-f439-4b55-b5ee-05d45bb54c36)

To fix the problem, copy the directories and files from official samples into the pack and then replace the files inside them with corresponding files from the texture pack.


Also the textures for pathways were not correctly converted so I had to rename those:
- dirt_path_side.png to grass_path_side.png
- dirt_path_top.png to grass_path_top.png
- mangrove_log.png to mangrove_log_side.png
- stripped_mangrove_log.png to stripped_mangrove_log_side.png
- cherry_log.png to cherry_log_side.png
- stripped_cherry_log.png to stripped_cherry_log_side.png

### Caveats
I did not test  that with any directories other than *textures/blocks* since the texture pack I fixed did not affect other textures.

Remember to remove the texture pack from the minecraft client before installing it again.
