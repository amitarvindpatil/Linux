## If, Elif and Else Statements
============================================

if [ some_condition_is_True ]
then
    // executable code
elif [ some_other_condition_is_true ]
then
    // execute this code
else
    // execute_this_code
fi 

### TESTING CONDITIONS => man test
===================================================
| command | example     | Description                |
| :-------- | :------- | :------------------------- |
|For numbers (integers) |
|`-eq`| equal to
|`-ne`| not equal to
|`-lt`| less than
|`-le`| less than or equal to
|`-gt`| greater than
|`-ge`| greater than or equal to
|For files:|
|`-s`|file exists and is not empty
|`-f`|file exists and is not a directory
|`-d`|directory exists
|`-x`|file is executable by the user
|`-w`|file is writable by the user
|`-r`|file is readable by the user
|For Strings|
|`=`|     the equality operator for strings if using single square brackets [ ]
|`==`|    the equality operator for strings if using double square brackets [[ ]]
|`!=`|    the inequality operator for strings
|`-n $str `|   str is nonzero length
|`-z $str `| str is zero length

`&&`   => the logical and operator 
`||` => the logical or operator