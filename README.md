# OpenNI

Website: http://structure.io/openni

## Contributing ##

Pull requests that do not apply cleanly on top of the [`develop` branch head](http://github.com/occipital/OpenNI2/tree/develop) will be rejected.  Other than that, sensible and meaningful contributions are very welcome!

## Platform-specific Building Prerequisites

### OS X

- Libusb 1.0
    First, install Homebrew: ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"
    brew install libusb --universal

### Windows
  Download and install the following:

- Microsoft Visual Studio 2010
  - From: http://msdn.microsoft.com/en-us/vstudio/bb984878.aspx
  
- Microsoft Kinect SDK v1.6
    - From: http://go.microsoft.com/fwlink/?LinkID=262831
    
- Python 2.6+/3.x
    - From: http://www.python.org/download/
    
- PyWin32
    - From: http://sourceforge.net/projects/pywin32/files/pywin32/
    - Please make sure you download the version that matches your exact python version.

- JDK 6.0
    - From: http://www.oracle.com/technetwork/java/javase/downloads/jdk-6u32-downloads-1594644.html
    You must also define an environment variable called "JAVA_HOME" that points to the JDK installation directory.
    For example: set JAVA_HOME=c:\Program Files (x86)\Java\jdk1.6.0_32

- WIX 3.5
    - From: http://wix.codeplex.com/releases/view/60102

- Doxygen
    - From: http://www.stack.nl/~dimitri/doxygen/download.html#latestsrc

- GraphViz
    - From: http://www.graphviz.org/Download_windows.php

### Linux
  Download and install the following:
  
- GCC 4.x
    - From: http://gcc.gnu.org/releases.html
    Or via apt:
    sudo apt-get install g++

- Python 2.6+/3.x
    - From: http://www.python.org/download/
    Or via apt:
    sudo apt-get install python

- LibUSB 1.0.x
    - From: http://sourceforge.net/projects/libusb/files/libusb-1.0/
    - Or via apt:
    sudo apt-get install libusb-1.0-0-dev

- LibUDEV
    - sudo apt-get install libudev-dev

- JDK 6.0
    - From: http://www.oracle.com/technetwork/java/javase/downloads/jdk-6u32-downloads-1594644.html
    - Or via apt:
    sudo apt-get install openjdk-6-jdk

- FreeGLUT3
    - From: http://freeglut.sourceforge.net/index.php#download
    - Or via apt:
    sudo apt-get install freeglut3-dev

- Doxygen
    - From: http://www.stack.nl/~dimitri/doxygen/download.html#latestsrc
    - Or via apt:
    sudo apt-get install doxygen

- GraphViz
    - From: http://www.graphviz.org/Download_linux_ubuntu.php
    - Or via apt:
    sudo apt-get install graphviz

### Android
- Note: These instructions assume Android KitKat which reached roughly 40% adoption in May 2015 per Google's [Dashboard][dashboard] page. Refer to [this][lollipopissue] issue for updated information regarding OpenNI2 on Android Lollipop.

##### All host platforms:
- As of the May 2015 Android Studio's NDK support continues to be reported as incomplete and is therefore not recommended as a build environment. The following focuses on Eclipse plus the ADT plugin.

- JAVA
  - Download and install the latest [JDK][javadownloadsindex]

- Android SDK
    - Download the [SDK][androidsdk]
      - Make sure to download the appropriate SDK Tools Only package for your host platform
    - Follow "Installing the Stand-alone SDK Tools" [here][standalonesdkinstall]
    - Follow the [ADDING SDK PACKAGES][addingpackages] link 
    - Define the ANDROID_HOME environment variable pointing to the SDK installation directory

- Android NDK
    - Download the lastest [NDK][ndkdownload] and follow [instructions][installingthendk] for installing the NDK
    - Define the NDK_HOME environment variable pointing to the NDK installation directory
    
- Eclipse
  - Download the latest Eclipse release for your host platform [here][eclipsedownload]
  - Go to Eclipse->Preferences->Android->NDK and set the NDK Location
  
- Eclipse ADT plugin
  - Follow the instructions for downloading and configuring the Eclipse ADT plugin [here][eclipseadtplugin]

##### Windows specific:
- Ant
  - Download from: https://code.google.com/p/winant

- JDK 6.0
  - Download from: http://www.oracle.com/technetwork/java/javase/downloads/jdk-6u32-downloads-1594644.html
  - You must also define an environment variable called "JAVA_HOME" that points to the JDK installation directory.
  -- For example: set JAVA_HOME=c:\Program Files (x86)\Java\jdk1.6.0_32

##### Ubuntu specific:
- Ant
  - sudo apt-get install ant
- JDK 6.0
  - Download from: http://www.oracle.com/technetwork/java/javase/downloads/jdk-6u32-downloads-1594644.html
      Or via apt:
      sudo apt-get install openjdk-6-jdk

## Building for various Host Platforms

### Windows:
  Build the Visual Studio solution OpenNI.sln
  
### Linux / OS X:
  Run:
  $ make

### Using XCode on OS X:
- TBD

### Cross-Compiling for ARM on Linux:
  The following environment variables should be defined:
  - ARM_CXX=<path to cross-compilation g++>
  - ARM_STAGING=<path to cross-compilation staging dir>
  Then, run:
  $ PLATFORM=Arm make
  
### Android:
  - Create an Eclipse workspace at the root of the OpenNI2 hierarchy
  - Import all projects under root directory
  - Projects found should include:
    - NiViewer
    - OpenNIForAdroid
    - SimpleRead
    - SimpleViewer
  - Set the Project Build Target for all imported projects 

## Creating OpenNI2 Package

- Go into the directory 'Packaging'
- Run ReleaseVersion.py [x86|x64|Arm|Android]
- Installer will be placed in the 'Final' directory

[addingpackages]: http://developer.android.com/sdk/installing/adding-packages.html
[androidsdk]: http://developer.android.com/sdk/index.html#Other
[standalonesdkinstall]: http://developer.android.com/sdk/installing/index.html?pkg=tools
[eclipsedownload]: http://www.eclipse.org/downloads/
[eclipseadtplugin]: http://developer.android.com/sdk/installing/installing-adt.html
[javadownloadsindex]: http://www.oracle.com/technetwork/java/javase/downloads/index.html
[ndkdownload]: http://developer.android.com/tools/sdk/ndk/index.html#Downloads
[installingthendk]: http://developer.android.com/tools/sdk/ndk/index.html#installing
[dashboard]: http://developer.android.com/about/dashboards/index.html
[lollipopissue]: https://github.com/occipital/OpenNI2/issues/43
