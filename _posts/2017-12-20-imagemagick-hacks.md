# cut out center portion of an image

convert image-original.jpg -resize {height or width, what is greater}x{height or width, what is greater} image-resized.jpg
convert image-resized.jpg -gravity center -crop {width}x{height}+0+0 +repage image-final.jpg
