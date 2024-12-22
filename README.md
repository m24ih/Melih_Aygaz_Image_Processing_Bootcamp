# Melih_Aygaz_Image_Processing_Bootcamp

## This repository is an example of Image Processing Bootcamp.

## Personal note: To be honest this project was my first image processing project. Feel free to open Issues and Pull Request to improve project. Special thanks for Global AI Hub to for organizing this bootcamp. I learned a lot thanks to this project. From now, I will tell you about my project. As you see there are more than one .ipynb files in the repository. I uploaded them to see accuracy differences.

### Libraries

- os
  - used for saving/reading processed, manipulated, and augmented images
- cv2
  - used for reading and manipulating photos
- numpy
  - used for array operations, for example creating color constancy function, concatenation and others
- matplotlib
  - used for showing examples of correct and incorrect predicted of images
- sklearn
  - used for creating test and train data from images
- tensorflow.keras
  - used for creating model, and data augmentation

---

### Image_Processing_Bootcamp_Final_Editon Cells

- 1st Cell: Imported libraries
- 2nd Cell: I initialized image directory as `base_path`. Then I created an array for animal classes that I need. I created a nested for loop for searching animals using `os` library. After that I create a for loop to show how many image that datase has.

- ![alt text](image-5.png)
- 3rd Cell: Used for loop to show directories
  ![alt text](image-6.png)
- 4th Cell: First 650 images are resized, normalized and saved to `processed_images` path.
- 5th Cell: In this cell I created `load_images` and `manipulate_images` function. For manipulating images, I adjusted brightness, contrast, and white balance.
- 6th Cell: Created a save function that i manipulated images above the cell.
- 7th Cell: I used `load_images` function to loading processed and manipulated images. Then I concatenated them with using `numpy` library. So i can train my model with combined datasets.
- 8th Cell: I split my train and test data. After that I create my model with different layers. Then I compiled my model.
  ![alt text](image-4.png)
- 9th Cell: At this cell I use `ImageDataGenerator` function from `tensorflow.keras` library. With that function I made augmentation. Then I applied to the train dataset.
- 10th Cell: Now, finally I can train my model and see accuracy points. Which is 78%
  ![alt text](image-3.png)
- 11th Cell: I created only manipulated dataset for testing my model.
- 12th Cell: With manipulated dataset, my model's accuracy is 89% which is great. But this wasn't always like that high.
  ![alt text](image-2.png)
- 13th Cell: I made an operation and then I see how many predictions are correct.
  ![alt text](image-1.png)
- 14th Cell: I want to see which images are incorrect predicted. Randomly chosen 5 picture is shown at this cell's output which their real and predicted animal classes.
- 15th Cell: Same thing but with correct predicts.
- 16th Cell: I created an color constancy algorithm with `get_wb_images` function. Which uses `numpy` library to make array operations like mean, sum, and normalize.
- 17th Cell: Applied color constancy algorithm to the manipulated images, and saved them.
- 18th Cell: Loading color constanced images
- 19th Cell: Normalize and test accuracy point for color constanced images which is 34%
  ![alt text](image.png)

---

## From now on I will only tell differences between other files and why i keep them.

First of all I started project with `bootcamp.ipynb` file. I tried Google Colab but it took over 50 minutes just to train the model. After that I decied working with my computer. As you see trainings are only take 82 seconds to finish. It was like fairytale until my vram and ram are completely fill. I searched for a solution but solutions are not worked for me. For example `gc.collect()` function.

So `bootcamp.ipynb` file way my base file. In that file results are like that: Training and test accuracy for; Processed images = **78%**, test accuracy for; Manipulated images = **9%**, test accuracy for White balance (color constancy) applied images = **10%**

Then I changed parameters in the model. In base file has `layers.Dense(128, activation='relu')` parameter for model. I increased to `layers.Dense(256, activation='relu')` Training and test accuracy for; Processed images = **84%**, test accuracy for; Manipulated images = **11%**, test accuracy for White balance (color constancy) applied images = **9%**

After that again I increased to `layers.Dense(512, activation='relu')` but this time Training and test accuracy for; Processed images = **75%**, test accuracy for; Manipulated images = **12%**, test accuracy for White balance (color constancy) applied images = **10%**

So optimum value is `layers.Dense(256, activation='relu')` for this model. Then I thought, what happens if i train my model with processed and manipulated images.
This time my results are like Training and test accuracy for; Processed images = **78%**, test accuracy for; Manipulated images = **89%**, test accuracy for White balance (color constancy) applied images = **11%**

That wasn't enough for me, and I didn't want to overfit my model. So I started browsing and asking ai to how improve color constancy, then I found that I should use data augmentation methods. With `ImageDataGenerator` function from `tensorflow.keras` library, I added properties to the dataset. Finally results are Training and test accuracy for; Processed images = **78%**, test accuracy for; Manipulated images = **89%**, test accuracy for White balance (color constancy) applied images = **34%**

Still Color constancy test accuracy is not enough but I don't have time to increase that accuracy before the deadline. 