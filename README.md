# Melih_Aygaz_Image_Processing_Bootcamp
 
## This repository is an example of Image Processing Bootcamp. 
Personal note: To be honest this project was my first image processing project. Feel free to open Issues and Pull Request to improve project. Special thanks for Global AI Hub to for organizing this bootcamp. I learned a lot thanks to this project. From now, I will tell you about my project. As you see there are more than one .ipynb files in the repository. I uploaded them to see accuracy differences. 
---
### Libraries
- os 
    - used for saving/reading processed, manipulated, and augmented images
- cv2 
    -  used for reading and manipulating photos
- numpy 
    - used for array operations, for example creating color constancy function, concatenation and others
- matplotlib 
    - used for showing examples of correct and incorrect predicted of images
- sklearn
    - used for creating test and train data from images
- tensorflow
    - used for creating model, and data augmentation

---
### Cells 
- 1st Cell: Imported libraries
- 2nd Cell: I initialized image directory as `base_path`. Then I created an array for animal classes that I need. I created a nested for loop for searching animals using `os` library. After that I create a for loop to show how many image that datase has.
- 3rd Cell: Used for loop to show directories
- 4th Cell: First 650 images are resized, normalized and saved to `processed_images` path.
- 5th Cell: In this cell I created `load_images` and `manipulate_images` function. For manipulating images, I adjusted brightness, contrast, and white balance.
- 6th Cell: Created a save function that i manipulated images above the cell.
- 7th Cell: I used `load_images` function to loading processed and manipulated images. Then I concatenated them with using `numpy` library. So i can train my model with combined datasets.
- 8th Cell: I split my train and test data. After that I create my model with different layers. Then I compiled my model.
- 9th Cell: At this cell I use `ImageDataGenerator` function from `tensorflow` library. With that function I made augmentation. Then I applied to the train dataset.
- 10th Cell: Now, finally I can train my model and see accuracy points. Which is 78%
- 11th Cell: I created only manipulated dataset for testing my model.
- 12th Cell: With manipulated dataset, my model's accuracy is 89% which is great. But this wasn't always like that high.
- 13th Cell: I made an operation and then I see how many predictions are correct.
- 14th Cell: I want to see which images are incorrect predicted. Randomly chosen 5 picture is shown at this cell's output which their real and predicted animal classes.
- 15th Cell: Same thing but with correct predicts.
- 16th Cell: I created an color constancy algorithm with `get_wb_images` function. Which uses `numpy` library to make array operations like mean, sum, and normalize.
- 17th Cell: Applied color constancy algorithm to the manipulated images, and saved them.
- 18th Cell: Loading 
