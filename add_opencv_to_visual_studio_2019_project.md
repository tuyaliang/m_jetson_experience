## Environment

    Windows 10 (64-bit)
    Visual Studio 2019

## Step `1`: Download and extract the pre-built library

    Download the latest binary from opencv's Github repository
    [OpenCV 4.1.2](https://github.com/opencv/opencv/releases/download/4.1.2/opencv-4.1.2-vc14_vc15.exe)
    [OpenCV 3.4.6](https://github.com/opencv/opencv/releases/download/3.4.6/opencv-3.4.6-vc14_vc15.exe)

## Step `2`: Add to environment variable

    add to Path -   C:\opencv\build\x64\vc15\bin

## Step `3`: Set platform target to x64
Pre-built binaries are built for x64 Windows platforms.

## Step `4`: Add to Include Directories
Tell the compiler how the OpenCV library looks. This is done by providing a path to the header files `build/include`.

    Project → YourProjectName Properties → go to VC++ Directories → <Edit…> in Include Directories → add -  C:\opencv\build\include

## Step `5`: Add to Library Directories
Tell the linker where it can find the lib files for different modules.

    Project → YourProjectName Properties → go to VC++ Directories → <Edit…> in Library Directories → add -  C:\opencv\build\x64\vc15\lib

## Step `6`: Add Additional Dependencies
List `opencv_world`.

    Project → YourProjectName Properties → go to Linker → Input → <Edit…> in Additional Dependencies → add -  C:\opencv\build\x64\vc14\lib\opencv_world346d.lib

## Check out demo code!

    #include <opencv2/core/core.hpp>
    #include <opencv2/highgui/highgui.hpp>
    #include <opencv2/imgproc.hpp>
    #include <iostream>

    using namespace cv;
    using namespace std;

    int main()
    {
        Mat image = Mat::zeros(300, 600, CV_8UC3);
        circle(image, Point(250, 150), 100, Scalar(0, 255, 128), -100);
        circle(image, Point(350, 150), 100, Scalar(255, 255, 255), -100);
        imshow("Display Window", image);
        waitKey(0);
        return 0;
    }