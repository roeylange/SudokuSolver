# Image-based Sudoku Solver
## Introduction
In this project, we developed an image-based Sudoku solver using computer vision and image processing techniques. The goal was to accurately identify and solve Sudoku puzzles in images.

## Running The Program
This program was developed using Google Colab, so that it can be used on any OS or device. In order to run the program correctly, first you need to upload the notes to Google Colab, and then run the required "pip install" commands and restart the runtime environment. Second, you need to upload the desired images, and upload the OCR model attached to the code. Finally, you need to change the name of the image to the corresponding image of your choice here:
![Code line](.\images\CodeLine.png)

## Project Overview
Our solution consists of the following steps:

* Image pre-processing to improve image quality
* Contour detection to identify the Sudoku grid
* Perspective transformation to correct for any tilts in the grid
* Cell segmentation to extract each individual cell
* Number recognition using OCR
* Sudoku solving using backtracking algorithm
* Technical Details
* Image Pre-processing
* We used OpenCV library to apply various filters to improve the image quality, such as thresholding and blurring.

![Flow chart](.\images\Flowchart.png)

### Image Pre-processing
We used OpenCV library to apply various filters to improve the image quality, such as thresholding and blurring.

### Contour Detection
Using OpenCV library, we identified the outermost contour in the image, which is the Sudoku grid. We then validated the grid by checking its aspect ratio and the number of corners.

### Perspective Transformation
We Applied perspective transformation to the grid, correcting for any tilts in the image. This step involved finding the four corner points of the grid and transforming the image based on those points.

### Rotation
After applying perspective transformation to the image, we further processed it by checking if it needed to be rotated. Due to the nature of the input images, it was possible for them to be rotated by 90, 180, or 270 degrees on the X-Y axis - since we've mainly used the geometrical features of the grid rather than referring to the actual digits it contains.

To detect and correct the rotation, we used the Pytesseract library, a tool that is used to recognize text from images. It allowed us to detect the orientation of the digits in the grid, and then rotate the image accordingly to align them with the X-Y axis.

### Cell Segmentation
We used OpenCV library to divide the grid into individual cells by detecting the vertical and horizontal lines of the grid. We then extracted each cell as a separate image for further processing.

### Number Recognition
We used a pre-trained OCR model to recognize the numbers in each cell. The OCR model was trained on a large dataset of handwritten digits and was able to recognize the numbers with high accuracy.

### Sudoku Solving
We used an [external](https://github.com/Lakshmi1212/Sudoku_Solver_LP/blob/main/Solver_LP.ipynb) backtracking algorithm to solve the Sudoku puzzle. The algorithm starts by filling in a number in the first empty cell and recursively solves the rest of the puzzle. If the algorithm reaches a dead end, it backtracks to the previous cell and tries a different number until the puzzle is solved.

## Examples
The first example is a simple image found online, not rotated or tilted:
 ![First example](.\images\sudoku-not_rotated_3.jpeg)
 ![Contoured image](.\images\sudoku-not_rotated_3_contours.jpeg)
 ![Transformed](.\images\sudoku-not_rotated_3_transformed.jpeg)
 ![Numbers found](.\images\sudoku-not_rotated_3_numbers.jpeg)
 ![Solve](.\images\sudoku-not_rotated_3_sol.jpeg)

To make a tilt or a rotation of an image, there are several ways: by trying to rotate the image syntactically, or by picturing the image manually under the specified tilt and rotation wanted. In the second case, the tilt and rotation were created using a website found online, that rotates an image syntactically:
 ![Second example](.\images\sudoku-rotated180.png)
 ![Contoured image](.\images\sudoku-rotated180_con.png)
 ![Transformed](.\images\sudoku-rotated180_transformed.png)
 ![Numbers found](.\images\sudoku-rotated180_num.png)

And for the latter case, you can create the picture yourself using an app that captures the picture without any special effects/compression of any kind. For example, Camera Scanner can be used. 

 ![Second example](.\images\Right_Side.jpg)
 ![Contoured image](.\images\Right_Side_con.jpg)
 ![Transformed](.\images\Right_Side_transformed.jpg)
 ![Numbers found](.\images\Right_Side_num.jpg)


## Project Limitations
It's important to acknowledge the limitations of our project, including:

* Blurry images
* Tilted images
* Bad image format/bad image ratio
* Corruption caused by compression/app auto edit
* OCR limitations
* Lighting conditions
* Background distractions
## Conclusion
In conclusion, our image-based Sudoku solver was able to accurately identify and solve Sudoku puzzles in images. Through the use of computer vision and image processing techniques, we were able to develop a solution that was capable of handling a variety of image conditions, including tilted and blurry images. The success of this project demonstrates the potential for computer vision in solving real-world problems and provides a proof of concept for further development and application in other domains.

Thank you for considering our project.