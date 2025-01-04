Steps for setting up to compile software using MAKE in Windows:
Prerequisite:
- GCC download link: https://developer.arm.com/downloads/-/gnu-rm
- make tool download link (take only the binary folder and dependecies folder): https://gnuwin32.sourceforge.net/packages/make.htm
    -> Copy *.dll from dependecies folder into the bin folder and correspondingly the manifest folder

B1: Follow link youtube: https://www.youtube.com/watch?v=jcy5TpbXfAY&t=584s and modify some changes for your computer below:
- After getting the new file c_cpp_properties.json created, replace below paths with actual path to the gcc path:
- You can get the referred file from github link: https://github.com/prtzl/Embedded_videos/blob/master/043_BUILDING-PT2/test-f407vg/.vscode/c_cpp_properties.json
From:
    "/usr/arm-none-eabi/include",
    "/usr/arm-none-eabi/include/c++/10.2.0",
    "/lib/gcc/arm-none-eabi/10.2.0/include",
    "/lib/gcc/arm-none-eabi/10.2.0/include-fixed",
    "/usr/arm-none-eabi/include/machine",
    "/usr/arm-none-eabi/include/newlib-nano",
    "/usr/arm-none-eabi/include/sys"
To:
    "C:\\Program Files (x86)\\GNU Arm Embedded Toolchain\\10 2021.10\\arm-none-eabi\\include",
    "C:\\Program Files (x86)\\GNU Arm Embedded Toolchain\\10 2021.10\\arm-none-eabi\\include\\c++\\10.3.1",
    "C:\\Program Files (x86)\\GNU Arm Embedded Toolchain\\10 2021.10\\lib\\gcc\\arm-none-eabi\\10.3.1\\include",
    "C:\\Program Files (x86)\\GNU Arm Embedded Toolchain\\10 2021.10\\lib\\gcc\\arm-none-eabi\\10.3.1\\include-fixed",
    "C:\\Program Files (x86)\\GNU Arm Embedded Toolchain\\10 2021.10\\arm-none-eabi\\include\\machine",
    "C:\\Program Files (x86)\\GNU Arm Embedded Toolchain\\10 2021.10\\arm-none-eabi\\include\\newlib-nano",
    "C:\\Program Files (x86)\\GNU Arm Embedded Toolchain\\10 2021.10\\arm-none-eabi\\include\\sys"
B2: Add to environment variables:
- Window + R --> sysdm.cpl --> Go to tab Advanced --> Environment Variables
- In System Variables window --> Go to the Variable "Path" --> Add bin folder path for both arm-none-eabi-gcc and make

B3: Restart the computer

Enjoy!!

=================================
Using ST-Link Ultility
If using that, need to reselect the hex file 1 more time to make the application reload the file then the file can be updated


