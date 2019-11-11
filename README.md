# PyTorchTip

## Import PyTorch Model to C++ in Windows

1/ Download latest LibTorch version in pytorch website https://pytorch.org (my version is 1.3.1, release version recommended)

2/ Install Visual Studio (2015 and above)

3/ Follow this tutorial to export your model to .pt file 
https://pytorch.org/tutorials/advanced/cpp_export.html

4/ Make new C++ solution in VStudio (Console Application)

5/ main.cpp as in cpp_export tutorial

6/ Add Include Dir: Select Project Property --> C/C++ --> Additional Include Directories --> Add full libtorch\include path

7/ Add lib file: Create new folder/filter named "lib" to solution explorer --> Drag all .lib files in libtorch\lib path to lib folder

8/ Change to Release and x64 Platform

9/ Copy all .dll files in libtorch\lib path to folder contain .exe run file (i.e. \x64\Release\)

10/ Fix some bugs in torch source code and build solution

Bug [unary minus operator applied to unsigned type result still unsigned] --> change -(UINT64_C to -1*(UINT64_C in .h error file

Bug [syntax error: 'constant'] --> rename UNICODE to UNICODEX

11/ Run with/without Debug
