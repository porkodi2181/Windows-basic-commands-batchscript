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
```
mkdir my-folder
```
<img width="522" height="54" alt="image" src="https://github.com/user-attachments/assets/ec47fcdd-7518-43ad-92d8-13c2a1d57e18" />


## COMMAND AND OUTPUT

Remove the directory "my-folder"
```
rmdir my-folder
```
<img width="537" height="67" alt="image" src="https://github.com/user-attachments/assets/8fed2add-4bc6-406b-8cc9-5abe5da29998" />


## COMMAND AND OUTPUT


Create the file Rose.txt
```
type nul > Rose.txt
```
<img width="594" height="69" alt="image" src="https://github.com/user-attachments/assets/e8398541-2879-4d07-b4d6-53c4ecc565b9" />


## COMMAND AND OUTPUT


Create the file hello.txt using echo and redirection
```
echo Hello World > hello.txt
```
<img width="742" height="61" alt="image" src="https://github.com/user-attachments/assets/94d2e0bb-6464-4230-9a18-fa0ee1a46376" />

## COMMAND AND OUTPUT

Copy the file hello.txt into the file hello1.txt
```
copy hello.txt hello1.txt
```
<img width="678" height="63" alt="image" src="https://github.com/user-attachments/assets/048bb66a-2cf3-45f3-8dcf-dc6b6fbb8c40" />


## COMMAND AND OUTPUT

Remove the file hello1.txt
```
del hello1.txt
```
<img width="476" height="39" alt="image" src="https://github.com/user-attachments/assets/143f8520-2827-48b1-8d3b-2f8fb205766a" />


## COMMAND AND OUTPUT

List out the file hello1.txt in the current directory
```
dir hello1.txt
```
<img width="593" height="241" alt="image" src="https://github.com/user-attachments/assets/f0669fb3-906b-4406-9b18-eef886ebd95e" />


## COMMAND AND OUTPUT

List out all the associated file extensions
```
assoc
```
<img width="552" height="814" alt="image" src="https://github.com/user-attachments/assets/0b775a89-4f3d-4818-b46b-8b298bf1a00d" />


## COMMAND AND OUTPUT


Compare the file hello.txt and rose.txt
```
fc hello.txt Rose.txt
```
<img width="465" height="140" alt="image" src="https://github.com/user-attachments/assets/97d0b15c-24c9-4c3e-adb7-3a5ee3a631ad" />



## COMMAND AND OUTPUT

## Exercise 2: Advanced Batch Scripting
Create a batch file named on the desktop. The batch file need to have a variable assigned with a desired name for ex. name="John" and display as "Hello, John".
```
@echo off
set name=John
echo Hello, %name%
pause
```




## OUTPUT
<img width="610" height="82" alt="image" src="https://github.com/user-attachments/assets/2da85461-8320-4e1f-8383-e9f8efde9104" />




Create a batch file  on the desktop that checks whether a user-input number is odd or not. The script should:
Prompt the user to enter a number.
Calculate the remainder when the number is divided by 2.
Display whether the number is odd or not.
Ask the user if they want to check another number.
Repeat the process if the user enters Y, and exit with a thank-you message if the user enters N.
Handle invalid inputs for the continuation prompt (Y/N) gracefully.
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


## OUTPUT
<img width="795" height="257" alt="image" src="https://github.com/user-attachments/assets/0fcfb96e-f867-411b-8a45-942c48c57158" />




Write a batch file that uses a FOR loop to iterate over a sequence of numbers (1 to 5) and displays each number with the label Number:. The output should pause at the end.
```
@echo off
for %%i in (1 2 3 4 5) do (
    echo Number: %%i
)
pause
```



## OUTPUT
<img width="610" height="214" alt="image" src="https://github.com/user-attachments/assets/369cd1f5-c698-4e93-9ba0-18bbeb92a466" />




Write a batch script to check whether a file named sample.txt exists in the current directory. If the file exists, display the message sample.txt exists. Otherwise, display sample.txt does not exist. Pause the script at the end to view the result.

Instructions:
Use the IF EXIST conditional statement.
Make sure the script works for files located in the same directory as the batch file.
Use pause to keep the command window open after displaying the message.
Expected Output (if the file exists):
```
@echo off
if exist sample.txt (
    echo sample.txt exists
) else (
    echo sample.txt does not exist
)
pause
```

## OUTPUT
<img width="546" height="61" alt="image" src="https://github.com/user-attachments/assets/52326fb1-ef21-4211-94e1-3be2391120b3" />


Write a batch script that displays a simple menu with three options:
Say Hello – Displays the message Hello, World!
Create a File – Creates a file named newfile.txt with the content This is a new file
Exit – Exits the script with a goodbye message
The script should repeatedly display the menu until the user chooses to exit. Use goto statements to handle menu navigation.
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

## OUTPUT
<img width="549" height="255" alt="image" src="https://github.com/user-attachments/assets/adb05ac5-87fe-4745-903c-514708e1bd8b" />


<img width="607" height="270" alt="image" src="https://github.com/user-attachments/assets/df1da65b-a5a0-4e92-b189-96aa0932ec94" />


<img width="586" height="259" alt="image" src="https://github.com/user-attachments/assets/4a8d5326-721f-4cee-997a-bf4301aaa8ee" />





# RESULT:
The commands/batch files are executed successfully.

