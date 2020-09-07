---
title: How are images compressed and stored in a computer
tree_state: 🌱
---
## How are images stored in a computer
- An image is just a collection of pixels where each pixel has a corresponding RGB (red, green, blue) value that dictates that pixel's color
- The quality/resolution of an image is determined entirely by the number of pixels that are stored for that image.
	- For example when we hear about screen resolution for a video/monitor we hear a term like **1080p**
		- 1080p is a set of HDTV high-definition video modes characterized by 1,920 pixels displayed across the screen horizontally and 1,080 pixels down the screen
		- 720p has an image resolution of 1280 pixels by 720 pixels

## Scaling Up and Down an Image
Suppose we have an image stored that's 100x100 pixels.
- Let's say you open up the image on your camera which has a resolution of 100x100 pixels (the same as the image). In the image you notice a big pimple on your left cheek and zoom in on it to get a closer look (suppose the area you're looking at makes up 20% of the image so we have 20x20 pixels stored for that area of the image). So now you are looking at a close up of your left cheek's big pimple on your camera's 100x100 pixel screen. But wait, how are you looking at a 20x20 close up of your left cheek when the entire image's resolution is 100x100 pixels?? When you zoom in on an image, your computer/camera recognized that you did not have enough pixels stored so it fills in the missing pixels for you, blurring the image in the process. This is the same thing that happens when you project a smaller image on a bigger screen.
- Let's say we want to store this 100x100 pixel image on a flash drive that doesn't have enough room to store the data from this image. What we can do is remove every other pixel from the image to get an image with now 50x50 pixels that we can store. When you are viewing an image in its original size and then you zoom out, this is what happens, you are deleting pixels to get a smaller picture.

However, when scaling a **vector graphic image**, the graphic primitives that make up the image can be scaled using geometric transformations, with no loss of image quality.

In image processing, these properties of image scaling are used to store images in a type of [pyramid](https://en.wikipedia.org/wiki/Pyramid_(image_processing))  where the original image is repeatedly scaled down and stored into images  that are subsequently smaller and smaller in resolution such that the result is a "pyramid" of images.
- This image processing format can be viewed as storing the "large-scale" features first and fine-grain details later in the file. A benefit of this is that a particular viewer displaying a small "thumbnail" or on a small screen can quickly download just enough of the image to display it in the available pixels so one file can support many viewer resolutions, rather than having to store or generate a different file for each resolution.