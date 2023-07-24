# string2array
Bash utility string to array with quote parsing

## USAGE
      string2array <option> "string"
### examples
* `toto="1 \"2 5\" 7 toto"; string2array -s "\"" $toto`
* `string2array -s "\[section\]" "1 2 [section]5 6 7 [section]"`
* `string2array -s "'" --any-sep "-o 'font_family=\"Iose'vka Term Extended\"' -o background_opacity=0.9"`
* `string2array -s "'" --only-sep "-o 'font_family=\"Iose'vka Term Extended\"' -o background_opacity=0.9"`
 
The script returns the array elements parsed line by line.
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

### INSTALLATION

Just copy the string2array file into /usr/local/bin or any bin PATH location you want.
