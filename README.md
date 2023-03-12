# Gradle
Exploring auto-build tools with gradle.
```bash
$ sudo apt-get update
$ sudo apt-get upgrade
$ sudo apt-get install openjdk-8-jdk
$ wget https://services.gradle.org/distributions/gradle-7.2-bin.zip
$ sudo mkdir /opt/gradle
$ sudo unzip -d /opt/gradle gradle-7.2-bin.zip
$ sudo nano /etc/profile

export GRADLE_HOME=/opt/gradle/gradle-7.2
export PATH=${GRADLE_HOME}/bin:${PATH}

$ source /etc/profile
$ gradle --version
```
how to compile two c files by gradle

To compile two C files using Gradle, you can use the C plugin provided by Gradle. Here are the steps:

    Create a new directory for your Gradle project and navigate to it.

    Create a build.gradle file in the project directory and add the following code:

    javascript

apply plugin: 'c'

model {
    components {
        main(NativeExecutableSpec) {
            sources {
                c {
                    source {
                        srcDir '.'
                        include 'file1.c', 'file2.c'
                    }
                }
            }
        }
    }
}

In the sources section, specify the directory where your C files are located and list the files that you want to compile.

Run the following command to compile the C files:

ruby

    $ gradle build

    This will generate the executable file in the build/bin directory.

Note that you may need to install the C toolchain and set up the environment variables for it to work properly. Additionally, you may need to customize the model section of the build.gradle file depending on your specific needs, such as specifying additional compiler or linker options.

install c tool chain

To install a C toolchain on Linux, you can follow these steps:

    Open a terminal window and update the package list:

    ruby

$ sudo apt update

Install the build-essential package, which includes the GCC compiler and other necessary tools:

ruby

$ sudo apt install build-essential

Verify that the GCC compiler is installed by running the following command:

css

    $ gcc --version

    This should display the version of the GCC compiler installed on your system.

Congratulations! You have successfully installed a C toolchain on your Linux system. Note that depending on your specific needs, you may need to install additional packages or customize your toolchain further.
