# Readying the Mesh
To create a new head, you'll need a mesh! I always convert my meshes from other video games (usually *The Sims 2*). 
Today I'll be taking a head mesh from a mod for *The Elder Scrolls III: Morrowind* and converting it to *The Sims 1*. I won't be covering how to extract meshes from any games here. I already have my meshes and textures ready to go, so I'll import the meshes into my 3D program. You can use Blender or Milkshape for this step. I'll use Milkshape.  
![Files](mesh1.jpg)  
There's already a couple big problems: The head is facing downward, and it's huge. So I've also imported another mesh for size reference. See that red spot in the middle? That's about the size and orientation we need our mesh to be. This is where Blender would come in handy, if you want. It's a lot easier and quicker to resize the head mesh in Blender.  

Now our mesh is a much nicer size. But theres another problem: This mesh is actually three separate meshes. One for the head, one for the ears, and one for the hair. Each of these mesh parts has its own texture, too. So we'll need to combine these three meshes into one single mesh, and likewise combine the three textures into one single texture. If we left these meshes separate, we'd need a separate .SKN file for each head mesh, and the .CMX file would get complicated fast. I only ever recommend having separate mesh parts for a head that has accessories, such as glasses or a cigar.  

So now I'm going to go into photoshop and create the texture for the head. Here's the three textures I'll need to combine. The ears texture has a lot of empty space, so I'll be arranging the face and hair texture on top of the texture for the ears. Maxis head textures are 128x128, but I usually make my textures 256x256. The ear texture is 512x512, so I'll resize the face and hair to be 256x256, fit them on the 512x512 canvas, and then resize the whole image to 256x256.

At this point, we also need to pick what we're going to name our files. [See this page for naming conventions!](skn2objcxm.md) I've picked the numbers `457` and the name `redguardf`, so my mesh group will be `c457_redguardf`. Sims 1 only has three skintones to choose from: light, medium, and dark. Redguards have dark skin, so the texture will be named `c457drk_redguardf`. Usually I make my heads avilable for all three skintones, but since this is a specific head from a specific game, I only have one skin texture to work with. If I had a texture for the medium and light skin swatches, they would be called `c457med_redguardf` for the medium skin, and `c457lgt_redguardf` for the light skin swatch. Simple as that!

Now that our textures are all on the same image, we are going to export the texture as an **indexed BMP**. In Photoshop, you go to Image/Mode/Indexed Color and it should be 256. Sims 1 can only use this type of BMP for the textures in-game. If they are not Indexed BMPs, they *will* show correctly in The Sims Creator, but not in the game! If your texture is the wrong format, it will show up in-game as blank and pure white instead of the correct texture.

Now that our texture is ready, it's time to fix the UV map. I'm going to add this new texture we created onto each one of the mesh parts, and then adjust the UV map as necessary. Ctrl + T is the shortcut to open the UV editor in Milkshape. Then I'll resize the face and hair UV by half and move them into place to fit the new texture. 

Before:

After:

Now that the UV maps are fixed, I can combine all three mesh parts into one single mesh, and the UV maps will combine as well, creating one mesh that is mapped to one texture. Here it is!:

Our mesh is now finished, and we can export the mesh as a .obj file. Now we'll open Skn2Obj and create the .skn file.
