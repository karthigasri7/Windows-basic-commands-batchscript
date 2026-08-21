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
mkdir karthiga
```

## COMMAND AND OUTPUT

<img width="898" height="111" alt="image" src="https://github.com/user-attachments/assets/1e0a84ce-4377-4f3f-933d-a78258bc5e64" />

Remove the directory "my-folder"

```
rmdir karthiga
```

## COMMAND AND OUTPUT

<img width="779" height="111" alt="image" src="https://github.com/user-attachments/assets/5a1594c0-638b-4e0b-ae22-d70d298ecf3e" />


Create the file Rose.txt

```
type nul > rose.txt
```
## COMMAND AND OUTPUT

<img width="948" height="56" alt="image" src="https://github.com/user-attachments/assets/3eed1168-4dd0-4f21-a5da-77ed90271035" />


Create the file hello.txt using echo and redirection

```
echo Hello world > hello.txt
```

## COMMAND AND OUTPUT

<img width="950" height="51" alt="image" src="https://github.com/user-attachments/assets/75459306-75ed-42c3-b23e-2aa9a0a440c6" />


Copy the file hello.txt into the file hello1.txt

```
copy hello.txt hello1.txt
```

## COMMAND AND OUTPUT

<img width="1015" height="66" alt="image" src="https://github.com/user-attachments/assets/af907ae7-5cb3-4585-9a76-e1aa06e05a57" />

Remove the file hello1.txt

```
del hello1.txt
```

## COMMAND AND OUTPUT

<img width="1167" height="57" alt="image" src="https://github.com/user-attachments/assets/2c769450-d13e-408d-ada1-225ae54bd073" />


List out the file hello1.txt in the current directory

```
dir hello1.txt
```

## COMMAND AND OUTPUT

<img width="1161" height="185" alt="image" src="https://github.com/user-attachments/assets/e3d46437-1217-4d31-9f0a-530d59de14c3" />


List out all the associated file extensions 

```
assoc
```
## COMMAND AND OUTPUT

<img width="1020" height="544" alt="image" src="https://github.com/user-attachments/assets/67233927-9d91-4c72-bdb5-d2f0c5ca6201" />

Compare the file hello.txt and rose.txt

```
fc hello.txt rose.txt
```

## COMMAND AND OUTPUT

<img width="756" height="160" alt="image" src="https://github.com/user-attachments/assets/9d76b231-961f-4748-b0d9-a2a3a6e82d79" />

## Exercise 2: Advanced Batch Scripting
Create a batch file named on the desktop. The batch file need to have a variable assigned with a desired name for ex. name="John" and display as "Hello, John".

```
@echo off
set name=John
echo Hello, %name%
pause
```

## OUTPUT

<img width="427" height="76" alt="image" src="https://github.com/user-attachments/assets/3e33d500-e05c-4bf5-b6ae-755fa8f4dc89" />



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

<img width="1897" height="182" alt="image" src="https://github.com/user-attachments/assets/68569050-d0e2-4894-96c5-0a38850956d7" />



Write a batch file that uses a FOR loop to iterate over a sequence of numbers (1 to 5) and displays each number with the label Number:. The output should pause at the end.

```
@echo off
for %%i in (1 2 3 4 5) do (
    echo Number: %%i
)
pause
```


## OUTPUT

<img width="1874" height="149" alt="image" src="https://github.com/user-attachments/assets/b9913904-1db6-4717-b2d5-6c7886a13b5d" />



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

<img width="1702" height="60" alt="image" src="https://github.com/user-attachments/assets/5c44739c-bb29-4c65-9360-beaa1137fa78" />


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

<img width="1919" height="212" alt="image" src="https://github.com/user-attachments/assets/1bbde50c-26a9-4136-8ad2-9e87ef1a3181" />
<img width="1919" height="231" alt="image" src="https://github.com/user-attachments/assets/78a69e51-e325-4562-a07e-4dc4fa3f0f03" />
<img width="1919" height="213" alt="image" src="https://github.com/user-attachments/assets/dad4dcfa-a26a-4290-9d8d-62c6f1dec634" />


# RESULT:
The commands/batch files are executed successfully.

