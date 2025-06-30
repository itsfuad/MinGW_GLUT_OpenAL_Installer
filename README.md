MinGW FreeGLUT & OpenAL Installer
----------------------------------

This script installs FreeGLUT and/or OpenAL headers and libraries into your MinGW environment.

REQUIREMENTS:
-------------
- MinGW with g++ must be installed and available in your system PATH.
- Place this script in a folder containing the following structure:
```
    freeglut\
        ├── include\GL\*.h
        ├── lib\x64\*.a           (for 64-bit)
        ├── lib\.\*.a             (for 32-bit)
        └── bin\x64\*.dll         (for 64-bit)

    OpenAL\
        ├── include\AL\*.h
        ├── libs\Win64\*.a, *.lib (for 64-bit)
        ├── libs\Win32\*.a, *.lib (for 32-bit)
        └── oalinst.exe           (optional OpenAL installer)
```
USAGE:
------
1. Right-click `install.bat` and select "Run as administrator" (or run from terminal with admin rights).

2. Choose what you want to install:
    ```
    [1] FreeGLUT only
    [2] OpenAL only
    [3] Both
    ```
4. The script will:
    - Detect your MinGW installation and architecture
    - Copy relevant header and library files
    - (If OpenAL is selected) silently run the OpenAL installer if available

NOTES:
------
- You must have admin rights to copy `.dll` files to the Windows system directory.
- At the end of the script, a summary will show what succeeded or failed.
- If errors occur, check that source folders and files exist in the correct locations.

EXAMPLE STRUCTURE:
------------------
    .
    ├── install.bat
    ├── README.txt
    ├── freeglut\
    │   ├── include\GL\freeglut.h ...
    │   ├── lib\x64\freeglut.a ...
    │   └── bin\x64\freeglut.dll ...
    └── OpenAL\
        ├── include\AL\al.h ...
        ├── libs\Win64\OpenAL32.a / .lib ...
        └── oalinst.exe
