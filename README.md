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
# Binary Image
Again, as the name suggest each number associated with
the pixel can have just one of the two possible values.
- Each pixel is a 1 bit number.
- It can take either 0 or 1 as its value.
- 0 corresponds to Black
- 1 corresponds to White
- Number of channels of a binary Image is 1
- Depth of a binary image is 1(bit)
