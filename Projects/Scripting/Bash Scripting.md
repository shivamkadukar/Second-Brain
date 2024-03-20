Bash(Bourne-Again SHell)
other available shell -Korn shell (ksh), C shell (csh), and Z shell (zsh).

Reference - 
[1. Bash Scripting Tutorial](https://www.freecodecamp.org/news/bash-scripting-tutorial-linux-shell-script-and-command-line-for-beginners/#pre-requisites)
[2. Bash Scripting Tutorial](https://linuxconfig.org/bash-scripting-tutorial)

checkout [[Batch Scripting]] for windows script automation

Bash command syntax:
```bash
command [OPTIONS] arguments
```

`date` - displays current date

`pwd` - display present working directory

`ls` - list content of current directory
	`ls -a` list all files(including hidden files)
	`ls -l` list all files with more details
	`ls -R` list files recursively
	`ls -r` sorts file list in reverse
	`ls -t` sorts files on time of modification

`echo` - prints string of text or value of a variable.

`man` - opens command manual for any bash command, syntax   ```man [COMMAND]```

> bash scripts ends with `.sh` extension

Bash script starts with __shebang__, it tells the shell to execute it via bash shell. It is absolute path to the bash interpreter.
shebang statement-
```bash
#!/bin/bash
```
The bash shell path can found using
```bash
which bash
```

### Basics

- Comments in bash starts with `#`.

- Variables 
	- No data types in bash, variable can store numeric value, single char or string.
	```bash
	country="India"
	same_country=$country
    ```
	- naming convention is same as python(can have letters, numbers and underscores, cannot start with a number).

- Gathering input
	- reading user input and storing it in a variable using `read` keyword.
	```bash
	#!/bin/bash
	echo -e "\n Enter your name: "
	read user_name
    ```
	 - denotes first argument, `$2` denotes second argument and so on.
		```bash
		#!/bin/bash
		echo "Hello, $1"
		```
		```bash
		>> ./greetings.sh Shivam
		```
		```bash
		>> Hello, Shivam
		```
- Displaying output
	-  printing to terminal
		```bash
		echo "Hello, World!"
		```
	- Writing to file
		```bash
		echo "write this text to file" > output.txt
		```
	- Appending to a file
		```bash
		echo "more text" >> output.txt
		```
	-  Redirecting output to a file
		```bash
		ls > list.txt
		```
- Basic bash commands
	1. `cd`: Change the directory to a different location.
	2. `ls`: List the contents of the current directory.
	3. `mkdir`: Create a new directory.
	4. `touch`: Create a new file.
		also used to update the timestamp of a file
	5. `rm`: Remove a file or directory.
	6. `cp`: Copy a file or directory.
	7. `mv`: Move or rename a file or directory.
	8. `echo`: Print text to the terminal.
	9. `cat`: Concatenate and print the contents of a file.
	10. `grep`: Search for a pattern in a file.
	11. `chmod`: Change the permissions of a file or directory.
	12. `sudo`: Run a command with administrative privileges.
	13. `df`: Display the amount of disk space available.
	14. `history`: Show a list of previously executed commands.
	15. `ps`: Display information about running processes.

### Operators
- ### Comparisons
	- #### Arthmetic Comparisons
		| Operator | Syntax |
		| -------- | ------ |
		| `-lt`    | <      |
		| `-gt`    | >      |
		| `-le`    | <=     |
		| `-ge`    | >=     |
		| `-eq`    | ==     |
		| `-ne`    | !      |
	- #### String Comparisons
		| Operator                 | Syntax |
		| ------------------------ | ------ |
		| equal                    | =      |
		| not equal                | !=     |
		| less than                | <      |
		| greater than             | >      |
		| string {s1} is not empty | -n s1  |
		| string {s1} is empty     | -z s1       |

### Conditional Statements(if/else)

```bash
if [[ condition ]];
then
	statement
elif [[ condition ]]; then
	statement 
else
	do this by default
fi
```






### Loops
- #### For Loop
```bash
#!/bin/bash

for f in $( ls/var/ ); do
	echo $f;
done
```

- #### While Loop
```bash
#!/bin/bash
COUNT=6
# bash while loop
while [ $COUNT -gt 0 ]; do
	echo Value of count is: $COUNT
	let COUNT=COUNT-1
done
```

- #### Until Loop
```bash
 #!/bin/bash
COUNT=0
# bash until loop
until [ $COUNT -gt 5 ]; do
        echo Value of count is: $COUNT
        let COUNT=COUNT+1
done
```





### Function
```bash
#!/bin/bash

# declaring function
function function_A {
	echo $1
}

# function call
function_A "Function A."

# output
>> Function A.
```


### Bash Select
```bash
#!/bin/bash
 
PS3='Choose one word: ' 

# bash select
select word in "linux" "bash" "scripting" "tutorial" 
do
  echo "The word you have selected is: $word"
# Break, otherwise endless loop
  break  
done
```




> In bash script, escaping meta characters can be done by using `\` before the character.
> Single quotes `''` will suppress special meaning of every meta characters.
> Double quotes `""` will suppress meaning of every meta characters except `$`, `\` and `. 

### Scheduling script using cron
Reference - https://www.freecodecamp.org/news/cron-jobs-in-linux/
```bash
# Cron job example
* * * * * sh /path/to/script.sh
# * represent minute(s) hour(s) day(s) month(s) weekday(s), respectively.
```
|SCHEDULE|DESCRIPTION|EXAMPLE|
|---|---|---|
|`0 0 * * *`|Run a script at midnight every day|`0 0 * * * /path/to/script.sh`|
|`*/5 * * * *`|Run a script every 5 minutes|`*/5 * * * * /path/to/script.sh`|
|`0 6 * * 1-5`|Run a script at 6 am from Monday to Friday|`0 6 * * 1-5 /path/to/script.sh`|
|`0 0 1-7 * *`|Run a script on the first 7 days of every month|`0 0 1-7 * * /path/to/script.sh`|
|`0 12 1 * *`|Run a script on the first day of every month at noon|`0 12 1 * * /path/to/script.sh`|

||VALUE|DESCRIPTION|
|-|---|---|
|Minutes|0-59|Command would be executed at the specific minute.|
|Hours|0-23|Command would be executed at the specific hour.|
|Days|1-31|Commands would be executed in these days of the months.|
|Months|1-12|The month in which tasks need to be executed.|
|Weekdays|0-6|Days of the week where commands would run. Here, 0 is Sunday.|


