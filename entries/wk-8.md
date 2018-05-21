## Week 8: Final Touches

Sometimes you think the solution to your problem is way more complicated than it really is. *I know I am not the only one who complicates things in my mind.* I thought I would need a for loop to do something like the example in EarSketch of Sonfication. However, it all just depends on what you want to accomplish. I realized by the end of this week that what I wanted to accomplish did not require for loops (because that complicates what I want to accomplish and makes me feel lost).

There is a function that actually converts an image to a 2D (two dimensional) or 3D (three dimensional) array. The function is called **`importImage`**. The syntax of `importImage` is: **`importImage(imageURL, nrows, ncols, includeRGB = False)`**. The parameter `inlcludeRGB` determines whether the array will be 2D or 3D. `False` is the default value, you do not need to set `includeRGB` to `'False'`. If you want the array to contain the RGB values of the picture then you need to set `includeRGB` to `'True'`. An array with RGB values is 3D and an array with black and white values is 2D. This is a lovely function, but I dislike it because I like to see the array visually without making it appear in the Console whenever I want to see it. So I used the [EarSketch Image Converter](https://earsketch.gatech.edu/imageConversion/) which appears to be the older version of the `includeRGB` function. This converter simply gives you the 2D or 3D array that you want, the same result that you get behind the scenes from using the `includeRGB`. Now I had the array that I wanted to see, but the array just looked funky and was hard for me to follow. I thought I might need to iterate through the array in order to get the numbers I wanted to use. As silly as it sounds, I did not know how to iterate through the 3D array I got. So I searched for videos that explain how to iterate through both 2D and 3D arrays. I found a [really great video](https://www.youtube.com/watch?v=Go-FfGhxbSM) that clearly explained how to access values from a multi-dimensional array. **_I felt really dumb after watching the video. Why? Because I realized I did not even need to iterate I just needed to organize the array in a way I could read it and to use the indices!_** There are these really neat array/list functions like `max()` and `min()` that I used to tell the program to find the minimum value and the maximum value from the array (not the whole array). from the 0th index value and in that array full of values of arrays the 0th index (in code form: `myImage_3d[0][0]`). As you can see in the code below, I used that change the pitch of the sound clip by using the product of the 5 times the sum of the maximum value and minimum value and then dividing that by the maximum value. 


#### Code Sample
```python
from earsketch import *

myImage_3d = [
             [[0,0,14,17,21,38,0,0,13,0,23,6,0,4,0,1],[7,1,0,3,5,5,7,6,38,1,28,1,4,0,0,0],[16,1,78,60,30,43,20,29,114,40,64,78,26,2,2,16],[69,22,17,28,11,2,14,26,63,9,131,13,11,0,4,4]],
             [[45,15,61,63,63,75,35,42,60,29,71,65,59,52,11,22],[40,15,33,36,27,40,37,35,68,29,61,30,39,16,11,27],[16,4,51,43,22,20,22,20,99,28,42,60,24,10,5,13],[41,7,1,0,2,1,6,5,58,1,84,1,17,1,3,4]],
             [[64,30,79,78,75,91,51,59,78,45,83,79,75,75,25,41],[55,26,50,53,41,59,48,51,78,43,78,48,58,30,25,44],[16,11,66,49,33,38,35,37,92,40,44,72,35,21,14,30],[17,14,1,17,5,0,4,10,39,0,92,3,3,5,8,6]]
             ]

init()
setTempo(90)

main_sound = YG_NEW_HIP_HOP_PIANO_5

fitMedia(main_sound, 1, 1, 9)

maxVal0_0 = max(myImage_3d[0][0])
minVal0_0 = min(myImage_3d[0][0])

pitchShiftAmount = 5 * (maxVal0_0 - minVal0_0)/(maxVal0_0)
setEffect(1, PITCHSHIFT, PITCHSHIFT_SHIFT, pitchShiftAmount)


finish()

```

### Takeaways
- **Do not overcomplicate the solution to your problem!:** I overcomplicated the solution to my problem. I thought I needed to iterate using a for loop to get the numbers I wanted from the array. However, I realized the solution was super simple and all I needed was the indices of the values of the array. Simple solutions are great!
- **Refresh your memory!:** If I did not find that video I probably would have wasted more time trying to figuring out how to iterate through a multi-dimensional array instead of realizing I did not need to iterate at all! I needed a refresher really on what I could do with just the accessing array values using the indices of array values. It never hurts to refresh your brain with information you may already know from the past.   

### Next Steps
- There really is not much to do next for me other than revising or making small changes. 
- Prepare to present my project by creating a powerpoint/google slide.

---

[**Next**](wk-9.md)

[**Back**](wk-7.md)

[**Back to the Homepage**](../README.md)