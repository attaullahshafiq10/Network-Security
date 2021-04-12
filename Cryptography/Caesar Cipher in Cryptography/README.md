Caesar Cipher in Cryptography
The Caesar Cipher technique is one of the earliest and simplest method of encryption technique. It’s simply a type of substitution cipher, i.e., each letter of a given text is replaced by a letter some fixed number of positions down the alphabet. For example with a shift of 1, A would be replaced by B, B would become C, and so on. The method is apparently named after Julius Caesar, who apparently used it to communicate with his officials.
Thus to cipher a given text we need an integer value, known as shift which indicates the number of position each letter of the text has been moved down.
The encryption can be represented using modular arithmetic by first transforming the letters into numbers, according to the scheme, A = 0, B = 1,…, Z = 25. Encryption of a letter by a shift n can be described mathematically as.
 



 
Examples :
Text : ABCDEFGHIJKLMNOPQRSTUVWXYZ
Shift: 23
Cipher: XYZABCDEFGHIJKLMNOPQRSTUVW

Text : ATTACKATONCE
Shift: 4
Cipher: EXXEGOEXSRGI
Algorithm for Caesar Cipher:
Input:
1.	A String of lower case letters, called Text.
2.	An Integer between 0-25 denoting the required shift.
Procedure:
•	Traverse the given text one character at a time .
•	For each character, transform the given character as per the rule, depending on whether we’re encrypting or decrypting the text.
•	Return the new string generated.
Program that receives a Text (string) and Shift value( integer) and returns the encrypted text.
•	C++
•	Java
•	Python
•	C#
•	PHP
filter_none
edit
play_arrow
brightness_4
#A python program to illustrate Caesar Cipher Technique 
def encrypt(text,s): 
    result = "" 
  
    # traverse text 
    for i in range(len(text)): 
        char = text[i] 
  
        # Encrypt uppercase characters 
        if (char.isupper()): 
            result += chr((ord(char) + s-65) % 26 + 65) 
  
        # Encrypt lowercase characters 
        else: 
            result += chr((ord(char) + s - 97) % 26 + 97) 
  
    return result 
  
#check the above function 
text = "ATTACKATONCE"
s = 4
print "Text  : " + text 
print "Shift : " + str(s) 
print "Cipher: " + encrypt(text,s) 
Output:
Text : ATTACKATONCE
Shift: 4
Cipher: EXXEGOEXSRGI
How to decrypt?
We can either write another function decrypt similar to encrypt, that’ll apply the given shift in the opposite direction to decrypt the original text. However we can use the cyclic property of the cipher under modulo , hence we can simply observe
Cipher(n) = De-cipher(26-n)
Hence, we can use the same function to decrypt, instead we’ll modify the shift value such that shift = 26-shift (Refer this for a sample run in C++).

