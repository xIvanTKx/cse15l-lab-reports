# Lab Report 1
For each of the commands cd, ls, and cat, and using the workspace you created in this lab:

1. Share an example of using the command with no arguments.
2. Share an example of using the command with a path to a directory as an argument.
3. Share an example of using the command with a path to a file as an argument.

# Command `cd`
![image](https://github.com/xIvanTKx/cse15l-lab-reports/assets/110268085/39a051c9-0dc4-4415-b839-3ccece39409a)
> Using *cd* with no argument would change our current directory to home, no matter what the previous working directory was. There is no output in the terminal except for the change in the present working directory.

![image](https://github.com/xIvanTKx/cse15l-lab-reports/assets/110268085/cd440c56-79e5-411d-b15e-fabde7abc6b8)
> Using *cd* with a path to a directory as an argument would allow us to change our current working directory if the specified path and directory exist. Again, there is no output in the terminal except for the change in the present working directory.

![image](https://github.com/xIvanTKx/cse15l-lab-reports/assets/110268085/6a59707a-e879-4ac1-a5c7-4242e42555e1)
> Using *cd* with a path to a file as an argument would output an error message because a file is not a directory. Thus, changing our current working directory to a *file* is not realistic.


# Command `ls`
![image](https://github.com/xIvanTKx/cse15l-lab-reports/assets/110268085/eb19804f-d3d6-4ab9-8ddf-0868b78c894e)
> Using *ls* with no argument in the terminal will list all the files/sub-directories in the present working directory. However, if there's no file or folder in the present working directory, then there would be no output in the terminal.

![image](https://github.com/xIvanTKx/cse15l-lab-reports/assets/110268085/4ee8941f-347e-498c-8b34-37602e24f00b)
> Using *ls* with a path to a directory as an argument will output all the files/folders of the specified directory. Even if the specified directory is not the current working directory, it will still output the files/folders.

![image](https://github.com/xIvanTKx/cse15l-lab-reports/assets/110268085/7aa9d982-a675-4709-ba22-58b221acba58)
> Using *ls* with a path to a file as an argument will output the file's name. The output will only contain the specified file name and is not an error because the command is to list the specified file only.


# Command `cat`
![image](https://github.com/xIvanTKx/cse15l-lab-reports/assets/110268085/7ef83dd6-5c4b-4599-bbc7-e0ac5961bfe8)
> Using *cat* with no argument will allow the terminal to wait for user input, and it will then display what's entered on the screen until `CTRL+D` is pressed, signaling the end of input. The output is no error at all, however, *cat* without arguments is not very useful.

![image](https://github.com/xIvanTKx/cse15l-lab-reports/assets/110268085/99415402-3e8b-43c7-99ec-9ecea4c1df1f)
> Using *cat* with a path to a directory as an argument would result in an error message. The *cat* command is used to concatenate and display the contents of one or more files. It is not designed to work with directories.

![image](https://github.com/xIvanTKx/cse15l-lab-reports/assets/110268085/eb4d75bc-41bd-450f-b110-fe9e5074905b)
> Using *cat* with a path to a file as an argument will display the content of the file. The output is the entire content of the file, not error messages.
