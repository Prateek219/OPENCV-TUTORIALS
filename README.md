# OPENCV TUTORIALS:IMAGE PROCESSING
## INTRODUCTION
What is OpenCV? This might be the 'basic' question that
comes first to your mind. Well, it stands for ‘Open Source
Computer Vision Library’ initiated by some enthusiast
coders in ‘1999’ to incorporate Image Processing into a
wide variety of coding languages. It has C++, C, and Python
interfaces running on Windows, Linux, Android and Mac.
Before, I get into the use of OpenCV; Let’s get familiar with
the same. As, by now you must have understood that it is a
'library'
, so to use the functions available in the library you
would need a compiler.

To start off, you need to install 'OpenCV' and a 'compiler'
and then establish a linkage between the two (i.e. Compiler
is able to use the functions available with the library).

## GETTING STARTED:
OpenCV can be downloaded from the following link:
http://sourceforge.net/projects/opencvlibrary/
Choose any of the several available versions. Prefer OpenCV2.1, if
interested in simple image processing (we have used that version
while preparing this tutorial).
Next, you would need a compiler like DevC++, CodeBlocks,
VisualC++. These can be downloaded from the following links:
- DevC++ : http://sourceforge.net/projects/dev-cpp/files/Binaries/DevC%2B%2B%204.9.9.2/devcpp-4.9.9.2_setup.exe/download
- CodeBlocks : http://www.codeblocks.org/downloads/26/
- VisualC++ : http://www.microsoft.com/visualstudio/en-us/products/2010-
editions/visual-cpp-express
Install one of the above compilers and next you would need to
link the library with the installed compiler.

### For integrating OpenCV with DevC++ :
- First of all, you have to indicate the header files you want to add. For
that, select Tools->Compiler Options.
![Screenshot (76)](https://user-images.githubusercontent.com/64007722/79848721-14e94900-83df-11ea-9d3e-793e2a5380da.png)
- Then click on the __plus__ sign(under __compiler set to configure__) to add a
new compiler named here, __OpenCV__
![Screenshot (78)](https://user-images.githubusercontent.com/64007722/79849072-9b058f80-83df-11ea-9d84-7ec4f6b1c4a5.png)
.
- To finish on, in the section Add the following commands.. write

-L"C:\OpenCV2.1\lib" -lcxcore210 -lcv210 -lcvaux210 -lhighgui210 -
lml210
[ note that the text in inverted commas is basically the location of the
lib(libraries) folder of OpenCV2.1. So, it won't work well if u've not
installed OpenCV in the default folder. ]

## Configuring included files
Next, click on Directories and then on C Includes to add all the headers,
located in some C:\OpenCV2.1 subdirectories. You only need to
add __C:\OpenCV2.1\include\opencv__ in the include tab to get things to
work.

__If you want to code in C++ then do the same for C++ includes__
![Screenshot (80)](https://user-images.githubusercontent.com/64007722/79849655-5fb79080-83e0-11ea-94f7-2208f91824a1.png)

## Configuring static library files
In the libraries section under the same heading directories you will
need to add __C:\ OpenCV2.1\lib__ . (if already present, ignore this
step.)
![Screenshot (83)](https://user-images.githubusercontent.com/64007722/79850748-f9cc0880-83e1-11ea-94b4-dfbc56d145da.png)

## Configuring dynamic library files

And to finish, add the bin directory where the dlls are:
i.e. add __C:\ OpenCV2.1\bin__ to _binaries_ subdivision.
![Screenshot (83)](https://user-images.githubusercontent.com/64007722/79850748-f9cc0880-83e1-11ea-94b4-dfbc56d145da.png)
## Congratulations..!!
With this, You are done with configuring _OpenCV with DevCPP_, you can
try running a sample code.



__OpenCV__ can also be __configured__ with CodeBlocks and VisualC++ by
following the instructions on provided link

- CodeBlocks: http://opencv.willowgarage.com/wiki/MinGW

- VisualC++: http://www.scribd.com/doc/60304851/Steps-to-Integrate-Opencv-2-2-
With-Visual-Studio-2010

##### By now, you must be having a compiler integrated with OpenCV library. Before I move to next section in which I will take you through basic image processing let me introduce you to the basic OpenCV modules.


Basically there are four modules. I’ll explain briefly about each
module.
-__cv__ : Main OpenCV functions, Image processing and vision
algorithms.

- __cvaux__: Auxiliary (experimental) OpenCV functions.

- __cxcore__: Data structures, linear algebra support, XML
support drawing functions and other algorithms.

- __highgui__: GUI functions, Image and Video I/O.

Depending on what your program implements you wish to use,
you should include corresponding modules.


# Image Processing
“Image Processing” is what it intuitively suggests.
Image processing is IMAGE + PROCESSING .
What is an Image?
- Image is a collection of PIXELS.
- Each pixel is like an array of numbers.
- These numbers determine the color of the pixel.
Now let me introduce you to different types of images. There are
three types of images:

   * Binary image,

   * Grayscale Image and,

   * Coloured image.

Each kind of image has few attributes attached to it like number
of channels and depth .

- __Number of channels__ : Defines the dimension of array ,
each pixel is.
- __Depth__ : Defines the maximum bit size of the number which
is stored in the array

#### Let’s have a closer look at different types of images.
## Binary Image
Again, as the name suggest each number associated with
the pixel can have just one of the two possible values.
- Each pixel is a 1 bit number.
- It can take either 0 or 1 as its value.
- 0 corresponds to Black
- 1 corresponds to White
- Number of channels of a binary Image is 1
- Depth of a binary image is 1(bit)

![Screenshot (85)](https://user-images.githubusercontent.com/64007722/79853135-482ed680-83e5-11ea-86cf-a44af829bc67.png)



## Grayscale Image
- Each pixel is a 8 bit number
- It can take values from 0-255
- Each value corresponds to a shade between black
and white( 0 for black and 255 for white)
- Number of channels for a grayscale image is 1
- Depth of a gray scale image is 8(bits)

![Screenshot (88)](https://user-images.githubusercontent.com/64007722/79853510-ca1eff80-83e5-11ea-80ce-6583684197e4.png)


## RGB Image
- Each pixel stores three values:
1.R : 0-255
2.G : 0-255
3.B : 0-255
- Each number between 0-255 corresponds to a
shade of corresponding color
- Depth of a RGB image is 8(bits)
- Number of channels for a RGB image is 3

![Screenshot (90)](https://user-images.githubusercontent.com/64007722/79853849-36016800-83e6-11ea-8087-5e2b057ca352.png)

# Starting with Processing Images
_I will be using C language and DevC++ as compiler embedded with
OpenCV2.1. You need not worry if you are using a different compiler._
## 1. Displaying an image
To start, let’s get through a simple program of displaying an image already
saved on the disk (something similar to a ‘hello world type program’).
Every C code starts with inclusion of header file and this is nothing
different. So, we will include basic header files needed for our program.
We will need following header files:
- __cv.h
- __highgui.h

### Image is stored as a structure IplImage with following elements

![Screenshot (92)](https://user-images.githubusercontent.com/64007722/79854651-6a295880-83e7-11ea-9318-ac92b4ada325.png)


__There is no need to go into the details right now, we will get acquainted
with these elements during the course of the tutorial.__


#### Steps involved:
We first need to initialize a pointer to the image ( structure)

__IplImage * input;

Next, load the desired image to the pointer

__input = cvLoadImage(“filename.extension”,1);

[1 for colored and 0 for grayscale]

Note: The image must be stored in the same folder in which you save the
C program.

To display the loaded image you will need a window.

__cvNamedWindow (“window name”, 1);

Again [1 for colored and 0 for grayscale]

Above command creates a window and to display the loaded image we

use the following command:

__cvShowImage(“window name”, input);

Suppose you have an image named __“shivendu.jpg”__ in the same folder in

which you save your code then your code would look something similar to

the following 

```
#inclde “cv.h”
#include “ highgui.h”
Int main()
{
 IplImage * input;
 input = cvLoadImage(“shivendu.jpg”,1);
 cvNamedWindow(“Output”,1);
 cvShowImage(“Output”, input);
}

```

If you try to execute this code the output window flickers just once. To
appreciate the output we need __cvWaitKey(number)__

- If 0 or negative number is given as input: - Waits indefinitely till key
press and returns the ASCII value of the key pressed.

- If positive number is given as input: - Waits for corresponding
milliseconds.

#### NOW THE FINAL CODE LOOKS LIKE

```
#inclde “cv.h”          // Include header files
#include “ highgui.h”
Int main()
{
 IplImage * input;       // Variable declaration
 input = cvLoadImage(“shivendu.jpg”,1);       // Loads the image
cvNamedWindow(“Output”,1);           // Creates a window to
display image
 cvShowImage(“Output”, input);         // Displays the image
cvWaitKey(0);                  // Waits till a key is pressed
}


```

This simple code must have helped you in understanding the flow of the
program (This is how things work with OpenCV). A good programmer will
always clear the memory assigned to variables.

It is therefore advisable to release the image and destroy the window
created:

__cvDestroyWindow( "Output" );__ // _destroy the window_

__cvReleaseImage( &input );__ // _release the memory for the image_

Include above two lines to make it a good simple code.


## 1. Creating an image
To create an image you need to provide the following details

- Size( height and width)

- Depth

- Number of channels

- And specify the pixel values

For creating an image we need we use the following function:

__output=cvCreateImage(cvGetSize(input),IPL_DEPTH_8U,3)__

This will create a RGB image(most general case among the three types of

images discussed) without specifying pixel values
## 2. Some common OpenCV functions

- output=cvCloneImage(input) -----__Copies image from input to output__

- __cvCvtColor( input, output, conversion type)
 __{ Conv. type : CV_BGR2GRAY ,CV_BGR2HSV}
 __-----Saves input image in output pointer in__
 __other color space__
 
- __cvSaveImage("output.jpg",output)
 __-----Saves image pointed by output naming it output__
## 3. Morphological operations on a image
There are two different kinds of morphological operations :

   * 1. Erosion

   * 2. Dilation
   
For carrying out morphological operations we need to specify type of
structural element and number of iterations.


Erosion erodes the image. It tries to bring uniformity in the image by
converting bright points in neighborhood of points of less intensity into
darker ones


Notice the change in eyes, illuminates spots in the eyes are removed
because in the input image there is a stark change in illumination at points
near pupil.

Dilation dilates the image. It tries to bring uniformity in image by
converting dark points in neighborhood of points of higher intensity into
bright ones


Here, is the code which erodes and dilates an image saved in the same
folder where c code is saved

```
#include "cxcore.h"
#include "highgui.h"
#include<cv.h>
int main()
{
int i=1;
IplImage* input;
IplImage* dilate;
IplImage* erode;
IplConvKernel *structure_element;
structure_element=cvCreateStructuringElementEx(i*2+1, i*2+1,
i,i,CV_SHAPE_ELLIPSE ); // Defines the structural element
cvNamedWindow("ii", 1);
cvNamedWindow("oo_dilate",1);
cvNamedWindow("oo_erode",1);
input = cvLoadImage("apple.jpg",1);
cvShowImage( "ii", input );
//make erode and dilate, clones of input (remember that cloning
automatically copies height, width etc.)
dilate=cvCloneImage( input );
erode=cvCloneImage( input );
//dilate image
cvDilate(input,dilate,structure_element ,1);
//cvDilate(input image pointer , output image pointer , structural element
, number of iterations)
//erode image
cvErode(input,erode,NULL,1);
//cvErode(input image pointer , output image pointer , structural element
, number of iterations)
cvShowImage( "oo_dilate", dilate);
cvShowImage( "input", input);
cvShowImage( "oo_erode", erode );
cvWaitKey(0);
cvDestroyWindow( "ii" );
cvDestroyWindow( "oo_dilate" );
cvDestroyWindow( "oo_erode" );
cvReleaseImage( &input );
cvReleaseImage( &dilate );
cvReleaseImage( &erode );
return 0;
}
```

