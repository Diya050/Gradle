# Gradle
Gradle is a build automation tool that helps software developers to automate the process of building, testing, and deploying software. It is used to manage dependencies, compile source code, and package software into a distributable format.

Gradle uses a domain-specific language (DSL) based on Groovy or Kotlin, which allows developers to write concise and readable build scripts. These build scripts can be used to define the build process for any type of project, from small libraries to large enterprise applications.

# Installation of Gradle
Here are the steps to install Gradle on Linux:

  1. Open a terminal window.
  2. Run the following commands:
  ```bash
$ sudo apt-get update
$ sudo apt-get upgrade
```
  3. Install the necessary dependencies by running the following commands:
  ```bash
  $ sudo apt-get install openjdk-8-jdk
  $ sudo apt install build-essential
  $ sudo apt-get install manpages-dev
  $ gcc --version
  ```
  4. Download the latest Gradle distribution using the following command:
  ```bash
$ wget https://services.gradle.org/distributions/gradle-7.2-bin.zip
$ sudo mkdir /opt/gradle
```
  5. Unzip the downloaded distribution archive to the /opt/gradle directory using the following command:
```bash
$ sudo unzip -d /opt/gradle gradle-7.2-bin.zip
$ sudo nano /etc/profile
```
 6. Add the following line to the end of the ~/.profile file:  
 ``` profile
export GRADLE_HOME=/opt/gradle/gradle-7.2
export PATH=${GRADLE_HOME}/bin:${PATH}
```
 7. Reload the ~/.profile file to apply the changes by running the following command:
 ``` bash
$ source /etc/profile
```
 8. Verify that Gradle is installed correctly by running the following command:
```bash
$ gradle --version
```
That's it! You have successfully installed Gradle on Linux.


# How to compile two C/C++ files using Gradle:

To compile two C++ files using Gradle, you can use the cpp plugin provided by Gradle. Here are the steps:

1. Create a new directory for your Gradle project and navigate to it.
2. Create a build.gradle file in the project directory and add the following code:
```C++
apply plugin: 'cpp'

model {
    components {
        main(NativeExecutableSpec) {
            sources {
                cpp {
                    source {
                        srcDir '.'
                        include '**/*.cpp'
                    }
                }
            }
        }
    }
}

task compileC(type: Exec) {
    commandLine 'gcc', 'file1.cpp', 'file2.cpp', '-o', 'output'
}
```

3. In the sources section, specify the directory where your C files are located and list the files that you want to compile.
4. Run the following command to compile the C++ files:

```bash
$ gradle build
```
5. This will generate the executable file in the build directory.

Note that you may need to install the C toolchain and set up the environment variables for it to work properly. Additionally, you may need to customize the model section of the build.gradle file depending on your specific needs, such as specifying additional compiler or linker options.


# Installing C tool chain

To install a C toolchain on Linux, you can follow these steps:

 1. Open a terminal window and update the package list:
```bash
$ sudo apt update
```
 2. Install the build-essential package, which includes the GCC compiler and other necessary tools:
```bash
$ sudo apt install build-essential
```
 3. Verify that the GCC compiler is installed by running the following command:
```bash
$ gcc --version
```
 4. This should display the version of the GCC compiler installed on your system.

Congratulations! You have successfully installed a C toolchain on your Linux system. Note that depending on your specific needs, you may need to install additional packages or customize your toolchain further.
