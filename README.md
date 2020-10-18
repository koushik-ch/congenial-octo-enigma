

# Given an image of a vehicle (Indian), you need to identify the dimensions of each character (A-Z, 0-9) from the license plate


Language used: Python 3 \
Tools  & Packages used:- OpenCV
			      Tesseract OCR \
			      PyTesseract \
			      Jupyter Notebooks 

## Steps involved: -
*	Import OpenCV and Pytesseract which are the necessary packages
*	Read the image using the imread() function from OpenCV library
*	A pre trained model for recognizing license plates of vehicles which is stored as an xml file is loaded as a cascade classifier into an Object. [Reference](https://docs.opencv.org/3.4/db/d28/tutorial_cascade_classifier.html)
*	The number plate is then detected by the Cascade classifier Object which contains the function detectMultiScale() which detects objects of different sizes in the input image. 
*	The detected objects are returned as a list of rectangles.
*	The dimensions of the first rectangle are stored and are drawn as a rectangle on the given image using the rectangle() function from the OpenCV library
*	The given image is cropped to the drawn rectangle.
*	The Cropped image is passed into the method cv2.COLOR_BGR2GRAY which is passed to the function cv2.cvtColor from the OpenCV library. This is done to convert the image into grayscale image.
*	The grayscale image is then passed into the method cv2.THRESH_BINARY which is passed to the function cv2.threshold from the OpenCV library. This is done to convert the image into Binary image using the given threshold values [Reference](https://docs.opencv.org/master/d7/d4d/tutorial_py_thresholding.html)
*	The binary image is then passed into the function image_to_string() offered by  the package  pytesseract. It is configured in such a way that the function only detects letters and numbers.
*	The detected text is then printed.
*	The text is then stored as a list of individual characters.
*	The height and width of the plate are found using the image.shape method and is then printed.
*	The bounding boxes of each individual characters are then stored in a list
*	It is then made to run through a loop where the bounding boxes for each character is drawn using the stored values in the list.
*	The height of each character is found by subtracting the lowest y-axis value with the highest y-axis value.
*	The width of each character is found by subtracting the lowest x-axis value with the highest x-axis value.
*	The spacing between each of the characters is found by subtracting the right most x-axis value of the previous character with the left most x-axis value of the current character.
*	The obtained values are then printed.

## Sample Input and Output

Input image:

 [IMG](https://github.com/rahulrk2303/Assignment-for-2nd-and-3rd-year-IT-students/blob/main/input_images/img31.png)

OUTPUT:
Detected license plate Number is: TSO7FX3534

Plate dimensions: 77 x 310 \
T :- Height: 44  Width: 22  Space: 4 \
S :- Height: 43  Width: 22  Space: 7 \
O :- Height: 54  Width: 22  Space: 8 \
7 :- Height: 44  Width: 22  Space: 8 \
F :- Height: 44  Width: 23  Space: 7 \
X :- Height: 45  Width: 22  Space: 7 \
3 :- Height: 43  Width: 22  Space: 8 \
5 :- Height: 55  Width: 28  Space: 3 \
3 :- Height: 44  Width: 21  Space: 8 \
4 :- Height: 45  Width: 23  Space: 8 

 
INPUT IMAGE:
 [IMG](https://github.com/rahulrk2303/Assignment-for-2nd-and-3rd-year-IT-students/blob/main/input_images/IMG_20200801_160718.jpg)

OUTPUT:

Detected license plate Number is: TN02BC8326

Plate dimensions: 128 x 386 \
T :- Height: 55  Width: 23  Space: 19 \
N :- Height: 55  Width: 24  Space: 8 \
0 :- Height: 57  Width: 20  Space: 25 \
2 :- Height: 56  Width: 20  Space: 8 \
B :- Height: 55  Width: 22  Space: 25 \
C :- Height: 57  Width: 23  Space: 9 \
8 :- Height: 57  Width: 19  Space: 25 \
3 :- Height: 75  Width: 27  Space: 1 \
2 :- Height: 56  Width: 20  Space: 8 \
6 :- Height: 57  Width: 20  Space: 7 

 


INPUT IMAGE:

 [IMG](https://github.com/rahulrk2303/Assignment-for-2nd-and-3rd-year-IT-students/blob/main/input_images/1596049634587.png)

OUTPUT:
Detected license plate Number is: MHOZEP1543

Plate dimensions: 67 x 269 \
M :- Height: 31  Width: 4  Space: 33 \
H :- Height: 31  Width: 17  Space: 5 \
O :- Height: 31  Width: 15  Space: 8 \
Z :- Height: 31  Width: 16  Space: 7 \
E :- Height: 31  Width: 16  Space: 8 \
P :- Height: 31  Width: 16  Space: 5 \
1 :- Height: 31  Width: 5  Space: 17 \
5 :- Height: 30  Width: 16  Space: 8 \
4 :- Height: 30  Width: 16  Space: 6 \
3 :- Height: 64  Width: 45  Space: 5 
 



INPUT IMAGE:
[IMG](https://github.com/rahulrk2303/Assignment-for-2nd-and-3rd-year-IT-students/blob/main/input_images/7.png)
 

OUTPUT:

Detected license plate Number is: MH12EG8179 E

Plate dimensions: 32 x 127 \
M :- Height: 13  Width: 12  Space: 6 \
H :- Height: 12  Width: 10  Space: 1 

1 :- Height: 13  Width: 6  Space: 4 \
2 :- Height: 12  Width: 8  Space: 1 \
E :- Height: 12  Width: 8  Space: 4 \
G :- Height: 13  Width: 10  Space: 1 \
8 :- Height: 12  Width: 7  Space: 4 \
1 :- Height: 12  Width: 5  Space: 1 \
7 :- Height: 12  Width: 6  Space: 1 \
9 :- Height: 12  Width: 7  Space: 1 
 
## Referred Websites/Tutorials:
https://www.youtube.com/watch?v=WQeoO7MI0Bs&t=2726s
https://www.youtube.com/watch?v=6DjFscX4I_c&t=1059s
https://medium.com/programming-fever/license-plate-recognition-using-opencv-python-7611f85cdd6c
https://towardsdatascience.com/ai-based-indian-license-plate-detector-de9d48ca8951

