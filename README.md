#  Bash Scripting

## iterate arguments by index
```
# iterate the script arguments by index
echo  # writes empty line
echo -n "Arguments of script $0: " # writes text without adding new line
for (( i=1; i<=$#; i++ )); do
  # ${!i} allows to access the argument by index (search for 'indirect expansion' for more information)
  echo -n "${!i} "
done
echo -e "\n"  # -e enables interpretation of backslash-escaped characters 

```
