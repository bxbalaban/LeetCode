
# Approach
^ and $ are used to specify the beginning and end of the line respectively, to ensure that the entire line matches the pattern. - ( and ) are used to match parentheses, which are escaped with backslashes because they have special meaning in regular expressions. - [0-9]{3} is used to match exactly three digits. - | is used to specify an alternative match, either a group of three digits surrounded by parentheses, followed by a space, or a group of three digits separated by a hyphen. - file.txt is the name of the file that we want to search. This regular expression matches phone numbers in the format (xxx) xxx-xxxx or xxx-xxx-xxxx. The output of this one-liner bash script will be the list of valid phone numbers in the file.



# Code
```
# Read from the file file.txt and output all valid phone numbers to stdout.
grep -E '^(\([0-9]{3}\) |[0-9]{3}-)[0-9]{3}-[0-9]{4}
``` file.txt
```