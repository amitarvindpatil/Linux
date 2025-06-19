## Special Variables and Positional Arguments
=========================================================
`./script.sh filename1 dir1 10.0.0.1`
| command | Description     |
| :-------- | :------- | 
| `$0` |  is the name of the script itself (script.sh). 
| `$1` |  is the first positional argument (filename1)
| `$2` |  is the second positional argument (dir1)
| `$3` |  is the last argument of the script (10.0.0.1)
| `$9` |  would be the ninth argument and ${10} the tenth
| `$#` |  is the number of the positional arguments
| `$*` |  is a string representation of all positional arguments: $1, $2, $3 ....
| `$?` |  is the most recent foreground command exit status

## Bash Variables
===========================================================
| command | Description     |
| :-------- | :------- | 
| defining a variable: variable_name=value
| variable names should start with a letter or underscore and can contain letters, digits and underscore
| `os="Kali Linux"` | 
|`version=10`|
|referencing the value of a variable (getting the variable value): $variable_name|
|`echo $os`|
|`echo $version`|
|`declare -r temperature=100`|  defining a read-only variable (constant)
|`unset version`|removing (unsetting) a variable
|`env` and `printenv`|listing all environment variables|
|searching for an environment variable|
|`printenv PATH` and `env | grep -i path`
|`export IP="80.0.0.1"`|creating new environment variables for the user: in ~/.bashrc add export MYVAR=”value” 
|`export PATH=$PATH:~/scripts`|  in ~/.bashrc  => Changing a path
| getting user input|
|`read MY_VAR`|
|`echo $MY_VAR`|
|displaying a message|
|`read -p "Enter the IP address: " ip`|
|`ping -c 1 $ip`|
|`read -s -p "Enter password:" pswd`|
|`echo $pswd`|
