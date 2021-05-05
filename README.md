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

## handle argument options: 'getopts'
```
# get options
# if the option has an argument add ':' after the option like the options 'a' and 'b'
# if the option has no argument omit the ':' like in the options 'c' and 'h'
while getopts a:b:ch flag
do
  case "${flag}" in
    a) aOption=${OPTARG};;
    b) bOption=${OPTARG};;
    c) cOption='y';;
    h) echo -e "Usage: script.sh -a a_value -b b_value -c"
       exit 0
       ;;
    *) echo "Invalid options"
       echo -e "Usage: script.sh -a a_value -b b_value -c"
       exit 1
       ;;
  esac
done
echo "Arguments: a option value= $aOption; b option value= $bOption; c option present= $cOption"
```
