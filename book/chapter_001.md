[Next Chapter](chapter_002.md)

# Introduction

## Prerequirements

As with all teaching programs this course assumes that the student already possess some skills. For instance if a child is brought to a basketball training it is generally assumed that the child knows how to stand upright, walk, run. Being able to tie the showlaces is also appreciated.

For the purpose of this course it is assumed that the student has a working computer with a internet connection. Operating system is not important. The programming language that will be used for practice examples to my knowledge works in Windows, MacOs, and most distributions of Linux. It is assumed that the student has a text editor on the computer and that student knows how to create, modify and save text files using the editor. It is assumed that the student has a terminal on their computer. I am not aware of any operationg system for a laptop/desktop computer in wide use today that does not have a terminal. It is also assumed that student has basic knowledge of how their computer works and is able to install programs on it. This will be needed in order to set up the programing language that will be used for examples during this course.

## What is a programming language

Computers are machines that can do a lot of tasks. They usually complete these tasks by executing a program. In order for computer to execute a program the program needs to be presented to the comupter in a way computer can understand. That usually means that program needs to be a series of simple machine instruction that the processor in a computer can execute. Example of the machine instruction can be found below. This is binary representation of the machine instruction. Binary since it only has two possible values for each character. 0 or 1. This is how processor will receive instruction and this is what processor knows how to execute.

```
00000001001010100100000000100000
```

As you can probably see for yourself writting program using just binary representation is not very convinient. That is why very early in computer evolution something called assembly was invented. Assembly was the "first" programming language in one sense since this was the first time some other representation for machine instructions was used. THe example of the assembly program can be seen below.

```
mov     X0, #1
adr     X1, helloworld
mov     X2, #13
mov     X16, #4
svc     #0x80
```

Now it is important to note here that machine instructions any computer can execute depends on the processor that computer is using. For that reason there are many "version" of machine instructions and conversly many versions of assembly.

To go back to assembly. While it made easier to write programs it was still required to write every machine instruction that computer will execute. The assembly example above just prints *helloworld*. It would be more convinient for a human to be able to write that program sequence as

```
print("helloworld)
```

That is why so called higher programming languages were invented. Higher programing languages allow us to write more concise code and than those instructions get translated to machine instructions by either compiler or interpreter.

## Compiled vs Interpreted programming languages

This is a complex topic that goes out of scope of this introductionary course. For now it is enough to understand that there are two ways in how the textual file containing the program you wrote gets presented to the computer.

If you are using compiling programmin language you would run a special program called the compiler that would read the program you wrote and generate coresponding machine instructions and store them in the executable file. 

```
compiler_for_you_language your_program_text_file
```

Once compiling is done you would run the executable file to get computer to run the program you just compiled

```
your_executable
```

Opposed to this interpreted programming languages use a special program called interpreter which takes text file containing your program as parameter reads it and start executing it immediately by translating it into macbine instructions computer can perform

```
your_interpreter your_program_text_file
```

There are advantages and drawback to both approached and as I said they go outside the scope of this course.

## Programming language that will be used for examples in this course

The programming language that I choose to present examples in this course will be [Golang](https://go.dev/) also known as Go.

Immediate question some people would ask would be why Go. In programming world there are many very good and popular programming languages and there is always debates which one is better. If you want to start a debate among programmer one of easy ways is to ask which programming language is the best or ask why is programming language X better than programming language Y.

There are several reasons I decided to choose Go.

Decent number of popular languages today that you may encountes looking for work as a programmer are "decendants" of programming language C. What I mean by this. A lot of languages today have been influenced by how C organized code, wrote structures etc and if you want to write a piece of code that does something and you write it in C, C++, C#, Java, JavaScript, Go and various other languages the resulting code would be very similar. That is why I believe using Go for examples in this course will help you to more easily "transfer" your knowlegde to other languages.

Go is garbage collected language. Now this again goes out of scope of the book but the most simples explanation I can give you is this. Every program you run on your computer will use memory of your computer. There are generally two options when comes to managing that memory so there are no issues. Either programmer does that and write the code being mindful how he allocates and release the memory or the compiler/interpreter does that for the programmer using garbage collector that does memory maangement for you. There are pros and cons with both approaces. One pro of garbage collection "programming model" is that is easier to write and understand code of garbage collected language. That is important in my opinion for this course.

Third reason I chose Go is that through my decades of experience being a professional programmer and teaching people how to program I noticed that some languages are great for advanced user but very hard for beginners. There are also languages that are easier for less experienced people. Go in my opinion is in the category of easier languages for beginners.

Fourth reason I choose to use Go for examples in this course is that it is one of the languages I am pretty decent in so I would be able to give you good examples on how to accomplish stuff with it.

Lastly I am not advocating Go is a superior language and that it shoul dbe used in all cases. As everything in life Go has its advantages and drawbacks over other languages. There are some practical applications where Go is really well suited. There are some practical application where I would never used Go since all the advantages Go offers are not important in that use case but the drawback of Go are a deal breaker.

To give you a driving example. If you are taking part in a car race you would not pick an truck. And if you need to transport three tons of coal you would not pick a formula one. As with everything in life you need to determine what is the right tool for the job at hand. If you later find a programming language that works for you or your particular problem better please use it over Go.

As I already said idea of this course is to cover the basics that exist in every language today. And with Go hope is that I can give you examples that would be simple enough to convert to any other language you choose. This will not be the course on programming in Go. I will not go into specific "best ways" to do something in Go. I will aim to give you the basic. But since programming is most effectively done by doing I will use Go to give you examples and exercises to try out for yourself.

## Preparing your computer for the course

Most courses on programming start by explaining you how to set up you computer to run all the tools you would need. I will not do that for several reasons. First computer and operating system that you use requires specific steps to get something running. Second even if I managed to write instructions for every variant of computer and operating systems they will be out of date within months.

What you need to have on your computer in order to work on this course is the following:

- text editor (this will be used to write and edit code examples)
- terminal (Terminal, PowerShell, what ever your operating system has that gives you option to write textual commands for your computer to execute)
- Installed Go (you can find instruction how to install Go on various operating systems on the official website)

Once you have all of this configured open the terminal and execute the following command

```
go version
```

Output on my Mac is

```
go version go1.22.5 darwin/arm64
```

If all is configured correctly you should see something similar.

Now that you have everything configured open file **sample.go** from *examples/chapter_001/exercise*.

You should see this in your editor

```
package main

import "fmt"

func main() {
	fmt.Println("hello world")
}
```

This is an example of the Go program. No need to try to understand what is what now. Just open the terminal navigate to the same folder where this **sample.go** file is and execute the following command

```
go run sample.go
```

You should get this output on the terminal

```
hello world
```

Congratulations you just executed your first program. Now let break down what you just did. Golang is compiled language. This means as I told you before that compiler needs to generate an executable first and then you run the executable. But that is not what we did. Go offers an option to run the compiler and execute the compiled program in one command by doing 

```
go run your_program.go
```

What Go does is it compiles the code from the text file you provided and immediately runs it if compilation is succesful.

If you what to compile the program only you would do

```
go build sample.go
```

On my machine this will result in executable file **sample** being created.

I can now run this executable with

```
./sample
```

Executing it on your operating sysgtem may differ. The output will be

```
hello world
```

liek before.

You exercise is to change the **sample.go** so that when you run the program the output is

```
welcome to introduction to programming
```

Please try to do the exercise on your own. If you get stuck the solution is in *examples/chapter_001/complete_exercise* folder.

[Next Chapter](chapter_002.md)