# cut out center portion of an image

convert image-original.jpg -resize {height or width, what is greater}x{height or width, what is greater} image-resized.jpg
convert image-resized.jpg -gravity center -crop {width}x{height}+0+0 +repage image-final.jpg

# show real image sizes in cm (with 300 dpi)

```
ls -1 | while read file
do
    height="`identify -format "%w" $file`"
    width="`identify -format "%h" $file`"
    heightCm=`echo "scale=2; ($height/300)*2.54" | bc -l`
    widthCm=`echo "scale=2; ($width/300)*2.54" | bc -l`
    echo "$file: $heightCm cm  x  $widthCm"
done
```
