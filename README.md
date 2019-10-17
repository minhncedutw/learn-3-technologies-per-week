# learn-3-technologies-per-week
> Each 7 days, learn 3 new techniques/technologies. Each time finishing 3-learning, it's able to jump to next streak of 3-learning.

## Streak 1(20191012-20191019): S-S-M-T-W-T-F

### 1 - Sat 20191012: Test-Driven Development(TDD)
![](https://upload.wikimedia.org/wikipedia/commons/0/0b/TDD_Global_Lifecycle.png)

**Key notes**
 - TDD(Test-Driven Development): kỹ thuật build code và automated test code đồng thời *(trước khi viết mỗi function/feature/product, viết test code cho mỗi cái trước)*.
 - BDD ???
 - Regression testing: mỗi khi build/modify 1 function thì phải run lại toàn bộ test chứ không chỉ test của riêng function đó.
 - TaaC(Test Case as a Code): mỗi test case đc thực hiện tự động bằng code, không phải test bằng tay.
 - Automation Test: tự động thực hiện các TaaC.
 - Phân loại Test:
    + Black-box testing:
        1. Acceptance testing: test project/test product.
    + White-box testing:
        1. Unit testing: test method(function) hoặc class(struct).
        2. Functional testing: test tính năng(feature), hay chuỗi chức năng(sequence of functions).

**Lecture**
 - General view: https://medium.com/@cuonggt/t%E1%BA%A3n-m%E1%BA%A1n-v%E1%BB%81-testing-15786963844

 - Nice definition: https://manhhomienbienthuy.github.io/2015/Dec/03/test-driven-development.html

### 2 - Mon 20191014: CI/CD(Continuous Integration/Continuous Deployment)

**CI(Continuous Integration)** là một phương pháp phát triển phầm trong đó, mỗi khi phần mềm được update tính năng, nó sẽ được kiểm tra một cách tự động, để phát hiện và thông báo lỗi sớm nhất cho developer, để fix ngay trong quá trình implementation.
![](https://viblo.asia/uploads/3ebb97df-6767-40dc-88ae-38cf392391f7.jpg)

**CD(Continuous Deployment)** là deploy sản phầm lên môi trường test, staging hay production một cách hoàn toàn tự động vào bất cứ khi nào.
![](https://viblo.asia/uploads/96d66313-9194-4e00-8f2d-d0e085135958.png)

**Tools for CI/CD**
 - Circle CI
 - Travis CI
 - Jenkins

**Lecture**
 - [Gerrit Code Review with Jenkins CI : Tích hợp CI / CD](https://viblo.asia/p/part-3-gerrit-code-review-with-jenkins-ci-tich-hop-ci-cd-eW65GYWOZDO#_vay-ci-cd-la-gi--2)
 - [Continuous Integration with Jenkins](https://viblo.asia/p/continuous-integration-with-jenkins-bai-1-gioi-thieu-ve-ci-va-jenkins-OeVKBggEZkW)
 - [Hướng dẫn tích hợp Travis-CI vào project trên github](https://toidicodedao.com/2015/09/15/huong-dan-tich-hop-travis-ci-vao-project-tren-github/)
 - **Pending of reading**: [Áp dụng CI/CD vào project của bạn (P1)](https://viblo.asia/p/ap-dung-cicd-vao-project-cua-ban-p1-gDVK2Q8e5Lj) + [Giới thiệu CI và áp dụng thực tế tool Circle CI](https://kipalog.com/posts/Gioi-thieu-CI-va-ap-dung-thuc-te-tool-Circle-CI)

### 3 - Thu 20191017: Build Visual C++ from command line

**Steps to Create a Visual C++ source file and Compile it on the command line**
 - create `hello` folder and a `hello.cpp` file inside with content:
```cpp
// hello/hello.cpp
#include <iostream>
using namespace std;
void main()
{
    cout << "Hello, world, from Visual C++!" << endl;
}
```
 - in command line, cd to `hello` folder
 - to compile program, execute: `C:\...\hello>cl /EHsc hello.cpp`
 - to run the built exe file, execute: `hello.exe`

*Refered from* [Walkthrough: Compiling a Native C++ Program on the Command Line](https://github.com/MicrosoftDocs/cpp-docs/blob/master/docs/build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)

**Compile a Visual Studio project from the command-line**
 - way 1st: `msbuild project.sln /Flags...`
 - way 2nd: `vcexpress project.sln /Build /Flags...`
 - way 3rd: `devenv project.sln /Build `

![](files/streak01-day03/command-line-tools.png)

*Refered from* [Use the Microsoft C++ toolset from the command line](https://docs.microsoft.com/en-us/cpp/build/building-on-the-command-line?view=vs-2019)

**Note!**
 - to run `cl` from command line, firstly execute: `call "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\VC\Auxiliary\Build\vcvarsall.bat" x64` or `call "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\VC\Auxiliary\Build\vcvars64.bat"`
 - to run `cl` from cmder, add task to settings: `cmd /k ""C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\VC\Auxiliary\Build\vcvarsall.bat" x64"`
 - explain [/EH (Exception Handling Model)](https://github.com/MicrosoftDocs/cpp-docs/blob/master/docs/build/reference/eh-exception-handling-model.md)
 - to compile multiple files: `cl /EHsc file1.cpp file2.cpp file3.cpp`
 - to rename the output file: `cl /EHsc file1.cpp /link /out:program1.exe`
 - to set the warning level when building: `cl /W4 /EHsc file1.cpp`


