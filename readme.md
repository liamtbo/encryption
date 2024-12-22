Encryption Project

This project implements four classic encryption methods in C++: Caesar Cipher, ROT13, Running Key, and Vigenère Cipher. The program allows users to encrypt and decrypt text using these methods with a command-line interface (CLI). It includes functionality for testing the encryption methods against test files.
Encryption Methods
1. Caesar Cipher

The Caesar Cipher is a substitution cipher where each letter in the plaintext is shifted by a fixed number of positions down or up the alphabet. For example, with a shift of 3, 'A' becomes 'D', 'B' becomes 'E', and so on.

    Input format: The first line of the input file contains the shift distance, and the second line contains the plaintext.
    Decryption: The decryption of a Caesar cipher is simply applying the inverse shift to the ciphertext.

2. ROT13

ROT13 (rotate by 13 places) is a simple cipher that shifts each letter by 13 positions. It is a special case of the Caesar Cipher with a shift of 13. Since 13 is half of 26 (the number of letters in the alphabet), applying ROT13 twice results in the original text.

    Input format: The plaintext is provided, and each letter is replaced with its 13th letter forward or backward.
    Decryption: Since applying ROT13 twice restores the original text, it serves as both an encryption and decryption method.

3. Running Key Cipher

The Running Key Cipher is a variation of the Vigenère cipher. It uses a key as long as the plaintext and applies the key to the message in a continuous, repeating fashion.

    Input format: The key is provided, and it is applied cyclically to the plaintext.
    Decryption: The key is used to reverse the encryption process by subtracting the key’s values from the ciphertext.

4. Vigenère Cipher

The Vigenère Cipher is a method of encrypting alphabetic text by using a simple form of polyalphabetic substitution. The cipher uses a keyword, where each letter of the keyword specifies the number of positions to shift corresponding letters in the plaintext.

    Input format: The keyword is provided, and it is repeated to match the length of the plaintext.
    Decryption: The decryption process involves reversing the encryption by using the same keyword.

How to Build the Project

To compile the project, use the following Makefile. This will generate an executable named cipher that you can use to encrypt and decrypt text files.

make

This will compile all the source files and generate the cipher executable.
Makefile Explanation:

    Sources: All .cc files in the directory.
    Objects: Corresponding .o files for each .cc file.
    Flags: Compiler options for debugging (-g), enabling warnings (-W, -Wall), and setting the C++ standard to C++14.
    Target: The final executable name (cipher).

Clean Up:

To remove the compiled object files and executable, run:

make clean

How to Run the Program

After compiling the project, you can run the program to test the encryption methods. The basic syntax for running the program is:

./cipher -m <method> -i <input_file> -o <output_file>

Where:

    -m <method>: Specifies the encryption method. Use one of the following:
        c for Caesar cipher
        r for ROT13
        k for Running Key
        v for Vigenère cipher
    -i <input_file>: Specifies the input file that contains the plaintext to be encrypted. The first line of the file should contain the shift distance or the key depending on the cipher being used.
    -o <output_file>: Specifies the output file that will contain the encrypted text on the first line and the decrypted text on the second line.

Example:

For testing the Caesar cipher with an input file called caesar.txt and outputting to caesar_out.txt, you would run:

./cipher -m c -i ./test1/caesar/caesar.txt -o ./test1/caesar/yourName_caesar_out.txt

    In this example, caesar.txt should contain:
        Line 1: The shift distance (e.g., 3)
        Line 2: The plaintext (e.g., "Hello World")

The output file caesar_out.txt will contain:

    Line 1: The encrypted text
    Line 2: The decrypted text (which should match the original plaintext)

Additionally, the program will generate a file def_caesar_out.txt, which contains the output when using the default constructor (shift distance of 0).
Testing the Program

To test your program with the provided test files:

    Make sure you have the input files prepared. For example, caesar.txt, rot13.txt, etc.
    Run the program as shown in the "How to Run the Program" section.
    The program will generate the output files as specified and will also include a default output file for comparison (def_caesar_out.txt).