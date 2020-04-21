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
add C:\OpenCV2.1\include\opencv in the include tab to get things to
work.
If you want to code in C++ then do the same for C++ includes
