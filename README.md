# Windows-basic-commands-batchscript
Ex08-Windows-basic-commands-batchscript

# AIM:
To execute Windows basic commands and batch scripting

# DESIGN STEPS:

### Step 1:

Navigate to any Windows environment installed on the system or installed inside a virtual environment like virtual box/vmware 

### Step 2:

Write the Windows commands / batch file . Save each script in a file with a .bat extension. Ensure you have the necessary permissions to perform the operations. Adapt paths as needed based on your system configuration.
### Step 3:

Execute the necessary commands/batch file for the desired output. 




# WINDOWS COMMANDS:
## Exercise 1: Basic Directory and File Operations
Create a directory named "my-folder"

mkdir %userprofile%\Desktop\MyLab

<img width="618" height="44" alt="image" src="https://github.com/user-attachments/assets/537ca91e-c64a-40d7-b0d3-744a3dd27e9c" />

## COMMAND AND OUTPUT

Remove the directory "my-folder"

## COMMAND AND OUTPUT

rmdir my-folder

<img width="408" height="50" alt="image" src="https://github.com/user-attachments/assets/b4957c7a-00fc-4b9a-bfbd-06d5da5971f9" />

Create the file Rose.txt

## COMMAND AND OUTPUT

type nul > Rose.txt

<img width="439" height="55" alt="image" src="https://github.com/user-attachments/assets/2bd4f8ab-c517-4c09-a6d5-f5c12fac886e" />

Create the file hello.txt using echo and redirection

## COMMAND AND OUTPUT

echo Hello World > hello.txt

<img width="558" height="52" alt="image" src="https://github.com/user-attachments/assets/38af332b-7cc6-4c5d-a466-25a0e787a826" />

Copy the file hello.txt into the file hello1.txt

## COMMAND AND OUTPUT

copy hello.txt hello1.txt

<img width="497" height="69" alt="image" src="https://github.com/user-attachments/assets/f3f67570-7b58-4a18-bfe8-061930eb9054" />

Remove the file hello1.txt

## COMMAND AND OUTPUT

del hello1.txt

<img width="390" height="49" alt="image" src="https://github.com/user-attachments/assets/36b06cd9-c58c-4d60-a0bb-20c66e12e743" />

List out the file hello1.txt in the current directory

## COMMAND AND OUTPUT

dir hello1.txt

<img width="438" height="182" alt="image" src="https://github.com/user-attachments/assets/f5791875-11e4-4fdb-9453-e7102dbc9091" />

List out all the associated file extensions 

## COMMAND AND OUTPUT

assoc

<img width="625" height="880" alt="image" src="https://github.com/user-attachments/assets/d29354ee-d2d9-4a1a-a33c-426425bb1f49" />

Compare the file hello.txt and rose.txt

## COMMAND AND OUTPUT

fc hello.txt Rose.txt

<img width="536" height="159" alt="image" src="https://github.com/user-attachments/assets/a9f12bd9-100b-4387-9ebf-5df133d0f4ea" />

## Exercise 2: Advanced Batch Scripting

Create a batch file named on the desktop. The batch file need to have a variable assigned with a desired name for ex. name="John" and display as "Hello, John".

## OUTPUT:

<img width="494" height="77" alt="image" src="https://github.com/user-attachments/assets/62d69609-73c3-47b5-a53c-57b0541b1147" />

Create a batch file  on the desktop that checks whether a user-input number is odd or not. The script should:
Prompt the user to enter a number.
Calculate the remainder when the number is divided by 2.
Display whether the number is odd or not.
Ask the user if they want to check another number.
Repeat the process if the user enters Y, and exit with a thank-you message if the user enters N.
Handle invalid inputs for the continuation prompt (Y/N) gracefully.

## CODE:
```
@echo off
:START
set /p num=Enter a number: 

set /a rem=%num% %% 2

if %rem%==1 (
    echo The number %num% is ODD
) else (
    echo The number %num% is NOT ODD
)

:CHOICE
set /p choice=Do you want to check another number? (Y/N): 

if /I "%choice%"=="Y" goto START
if /I "%choice%"=="N" goto END

echo Invalid choice. Please enter Y or N.
goto CHOICE
:END
echo Thank you!
pause
```

## OUTPUT:

<img width="656" height="202" alt="image" src="https://github.com/user-attachments/assets/a4720e67-4a44-4efd-8b8e-cea2779c934f" />

Write a batch file that uses a FOR loop to iterate over a sequence of numbers (1 to 5) and displays each number with the label Number:. The output should pause at the end.

## CODE:
```
@echo off
for %%i in (1 2 3 4 5) do (
    echo Number: %%i
)
pause
```

## OUTPUT:

<img width="457" height="165" alt="image" src="https://github.com/user-attachments/assets/30d2b9c0-636f-46f9-a6d9-0387e8d3f6a6" />

Write a batch script to check whether a file named sample.txt exists in the current directory. If the file exists, display the message sample.txt exists. Otherwise, display sample.txt does not exist. Pause the script at the end to view the result.

Instructions:
Use the IF EXIST conditional statement.
Make sure the script works for files located in the same directory as the batch file.
Use pause to keep the command window open after displaying the message.
Expected Output (if the file exists):

## CODE:
```
@echo off
if exist sample.txt (
    echo sample.txt exists
) else (
    echo sample.txt does not exist
)
pause
```

## OUTPUT:

<img width="422" height="52" alt="image" src="https://github.com/user-attachments/assets/cc700b67-a8ae-4f91-9e16-cc35a93d74e6" />

Write a batch script that displays a simple menu with three options:
Say Hello – Displays the message Hello, World!
Create a File – Creates a file named newfile.txt with the content This is a new file
Exit – Exits the script with a goodbye message
The script should repeatedly display the menu until the user chooses to exit. Use goto statements to handle menu navigation.

## CODE:
```
@echo off
:MENU
cls
echo ===== MENU =====
echo 1. Say Hello
echo 2. Create a File
echo 3. Exit
echo =================
set /p choice=Enter your choice: 

if "%choice%"=="1" goto HELLO
if "%choice%"=="2" goto CREATE
if "%choice%"=="3" goto EXIT

echo Invalid choice!
pause
goto MENU

:HELLO
echo Hello, World!
pause
goto MENU

:CREATE
echo This is a new file > newfile.txt
echo File created successfully!
pause
goto MENU
:EXIT
echo Goodbye!
pause
exit
```

## OUTPUT 1:

<img width="410" height="192" alt="image" src="https://github.com/user-attachments/assets/d0104adc-b181-496f-ae99-861c26cb9170" />

## OUTPUT 2:

<img width="441" height="203" alt="image" src="https://github.com/user-attachments/assets/df3597b0-0b74-40b3-9094-7aec04b799b8" />

## OUTPUT 3:

<img width="431" height="197" alt="image" src="https://github.com/user-attachments/assets/f3ab090b-eba0-4056-afb2-d1b9fc83cbe2" />

# RESULT:

The commands/batch files are executed successfully.

