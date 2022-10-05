# string2array
Bash utility string to array quote parsing

## USAGE
      string2array <option> "string"
### examples
* `toto="1 \"2 5\" 7 toto"; string2array -s "\"" $toto`
* `string2array -s "\[section\]" "1 2 [section]5 6 7 [section]"`

The script returns the array elements parsed line by line
To use it to set an array inside a bash script:
```bash
mapfile myarray < <(string2array $string)
```
or
```bash
while read line; do 
    myarray+=("$line")
done < <(string2array -s "\"" $string)
```

# Installation

Just copy the string2array file into /usr/local/bin or any bin PATH location you want
