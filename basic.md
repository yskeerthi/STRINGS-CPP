
# C++ String Methods and Algorithms

This document covers **basic to advanced string methods** in C++ along with code examples.

---

## Basic String Operations

### 1. String Initialization

You can initialize strings in various ways.

```cpp
#include <iostream>
#include <string>

int main() {
    std::string str1 = "Hello, World!";
    std::string str2("Hello, World!");
    std::string str3(str1);  // Copy constructor
    std::string str4(5, 'A');  // Creates a string of 5 'A's (AAAAA)

    std::cout << "String 1: " << str1 << std::endl;
    std::cout << "String 2: " << str2 << std::endl;
    std::cout << "String 3 (copy of String 1): " << str3 << std::endl;
    std::cout << "String 4 (initialized with 5 A's): " << str4 << std::endl;
}
```
### 2. length() / size()
Returns the length of the string
```cpp
#include <iostream>
#include <string>

int main() {
    std::string str = "Hello";
    std::cout << "Length of string: " << str.length() << std::endl;
    std::cout << "Size of string: " << str.size() << std::endl;
}

```

### 3. empty()
Checks if the string is empty.
```cpp
#include <iostream>
#include <string>

int main() {
    std::string str = "";
    if (str.empty()) {
        std::cout << "String is empty." << std::endl;
    }
}
```

### 4. clear()

#####Clears the content of the string, making it empty.
```cpp

#include <iostream>
#include <string>

int main() {
    std::string str = "Hello";
    str.clear();
    std::cout << "String after clear: " << str << std::endl;
}
```

### 5. at() and []
Accesses characters in the string. at() provides bounds checking, while [] does not.
```cpp
#include <iostream>
#include <string>

int main() {
    std::string str = "Hello";
    std::cout << "Character at index 1: " << str.at(1) << std::endl;  // bounds checked
    std::cout << "Character at index 1: " << str[1] << std::endl;  // no bounds checking
}

```

### 6. append()
Appends a string or a character to the end of the current string.

```cpp
#include <iostream>
#include <string>

int main() {
    std::string str1 = "Hello";
    std::string str2 = " World";
    str1.append(str2);
    std::cout << "Appended string: " << str1 << std::endl;
}

```

### 7. insert()
Inserts a substring into a string at a specified position.
```cpp
#include <iostream>
#include <string>

int main() {
    std::string str = "Hello!";
    str.insert(5, ", World");
    std::cout << "Inserted string: " << str << std::endl;
}

```


### 8. replace()

Replaces a portion of the string with another substring.

```cpp
#include <iostream>
#include <string>

int main() {
    std::string str = "Hello, World!";
    str.replace(7, 5, "Universe");
    std::cout << "Replaced string: " << str << std::endl;
}

```

### 9. erase()
Removes a part of the string starting from the given position.
```cpp
#include <iostream>
#include <string>

int main() {
    std::string str = "Hello, World!";
    str.erase(5, 7);  // Erases " World!"
    std::cout << "Erased string: " << str << std::endl;
}


```

### 10. substr()
Extracts a substring from the string.
```cpp
#include <iostream>
#include <string>

int main() {
    std::string str = "Hello, World!";
    std::string sub = str.substr(7, 5);  // Extract "World"
    std::cout << "Extracted substring: " << sub << std::endl;
}

```

### 11.find() and rfind()
Finds the first occurrence (find) or last occurrence (rfind) of a substring or character.

```cpp
#include <iostream>
#include <string>

int main() {
    std::string str = "Hello, World!";
    size_t pos = str.find("World");
    if (pos != std::string::npos) {
        std::cout << "'World' found at position: " << pos << std::endl;
    }
}

```
### 12. compare()

```cpp
#include <iostream>
#include <string>

int main() {
    std::string str1 = "Apple";
    std::string str2 = "Banana";
    
    if (str1.compare(str2) < 0) {
        std::cout << str1 << " comes before " << str2 << std::endl;
    } else if (str1.compare(str2) > 0) {
        std::cout << str1 << " comes after " << str2 << std::endl;
    } else {
        std::cout << str1 << " is equal to " << str2 << std::endl;
    }
}

```


### 13. swap()
Swaps the contents of two strings.
```cpp
#include <iostream>
#include <string>

int main() {
    std::string str1 = "Hello";
    std::string str2 = "World";
    
    str1.swap(str2);
    
    std::cout << "str1: " << str1 << std::endl;  // Outputs "World"
    std::cout << "str2: " << str2 << std::endl;  // Outputs "Hello"
}


```
 ### 14. c_str()
Converts a std::string to a C-style string (const char*).
 ```cpp
#include <iostream>
#include <string>

int main() {
    std::string str = "Hello";
    const char* cstr = str.c_str();
    std::cout << "C-style string: " << cstr << std::endl;
}


```
### 15. getline()
Reads a line of input into a string, including spaces.
 ```cpp
#include <iostream>
#include <string>

int main() {
    std::string input;
    std::cout << "Enter a line: ";
    std::getline(std::cin, input);
    std::cout << "You entered: " << input << std::endl;
}
```

### 16. stoi(), stof(), stod(), etc.
These functions convert strings to integers, floats, and doubles.
```cpp

#include <iostream>
#include <string>

int main() {
    std::string str = "123";
    int num = std::stoi(str);
    std::cout << "Integer: " << num << std::endl;
}
```

### 17. String Concatenation
Concatenation can be done using the + operator or the .append() method.
```cpp
#include <iostream>
#include <string>

int main() {
    std::string str1 = "Hello";
    std::string str2 = " World";
    
    std::string result = str1 + str2;  // Concatenating using +
    std::cout << "Concatenated string: " << result << std::endl;

    str1.append(str2);  // Appending using .append()
    std::cout << "Appended string: " << str1 << std::endl;
}


```
### 18. Substrings
You can extract a portion of a string using the .substr() method.
``` cpp

#include <iostream>
#include <string>

int main() {
    std::string str = "Hello, World!";
    std::string sub = str.substr(7, 5);  // Extract "World"
    
    std::cout << "Original string: " << str << std::endl;
    std::cout << "Extracted substring: " << sub << std::endl;
}

```
### 19. Replacing Substrings
The .replace() method replaces part of the string with another substring.
```cpp
#include <iostream>
#include <string>

int main() {
    std::string str = "Hello, World!";
    str.replace(7, 5, "Universe");  // Replace "World" with "Universe"
    std::cout << str << std::endl;  // Output: "Hello, Universe!"
}
```
### 20. Finding Substrings
You can find the first occurrence of a substring using .find() and the last occurrence using .rfind().
```cpp
#include <iostream>
#include <string>

int main() {
    std::string str = "Hello, World!";
    size_t pos = str.find("World");

    if (pos != std::string::npos) {
        std::cout << "'World' found at position: " << pos << std::endl;
    } else {
        std::cout << "'World' not found!" << std::endl;
    }
}
```

### 21. Converting C-Style Strings to std::string

C-style strings (char* or const char*) can easily be converted to std::string.
```cpp
#include <iostream>
#include <string>

int main() {
    const char* cstr = "Hello";
    std::string str = cstr;  // Convert C-string to std::string
    std::cout << "C++ string: " << str << std::endl;
}


```

### 22. Converting Strings to C-Style Strings
You can convert a std::string to a C-style string (const char*) using .c_str().
```cpp
#include <iostream>
#include <string>

int main() {
    std::string str = "Hello";
    const char* cstr = str.c_str();
    std::cout << "C-style string: " << cstr << std::endl;
}
```


### 23. Erasing Part of a String
.erase(index, length): Removes a portion of the string.
```cpp
std::string str = "Hello, World!";
str.erase(5, 7);  // Output: Hello!
```


#Advanced String Algorithms

### 1. Knuth-Morris-Pratt (KMP) Algorithm

KMP efficiently searches for a pattern within a text in O(n + m) time, where n is the length of the text, and m is the length of the pattern. It uses a preprocessing table (LPS array) to skip unnecessary comparisons.

```cpp
#include <vector>
#include <iostream>
#include <string>

// Function to compute the Longest Prefix Suffix (LPS) array.
// The LPS array helps to avoid redundant comparisons in the pattern string.
void computeLPSArray(const std::string &pat, std::vector<int> &lps) {
    int len = 0;  // Length of the previous longest prefix suffix
    lps[0] = 0;   // lps[0] is always 0 since there's no proper prefix for a single character pattern.
    
    int i = 1;  // Start from the second character of the pattern
    while (i < pat.length()) {
        // If the characters match, increase the length of the LPS and store it in lps[i]
        if (pat[i] == pat[len]) {
            len++;
            lps[i] = len;
            i++;
        } else {
            // If the characters don't match
            if (len != 0) {
                // Reduce the length of the current LPS using the previously computed LPS values
                len = lps[len - 1];
            } else {
                // If len becomes 0, just set lps[i] to 0 and move to the next character
                lps[i] = 0;
                i++;
            }
        }
    }
}

// Function to perform KMP search for the pattern in the given text
void KMPsearch(const std::string &pat, const std::string &txt) {
    int M = pat.length();  // Length of the pattern
    int N = txt.length();  // Length of the text

    // Create an array to hold the longest prefix suffix values for the pattern
    std::vector<int> lps(M);

    // Preprocess the pattern to compute the LPS array
    computeLPSArray(pat, lps);

    int i = 0;  // Index for the text
    int j = 0;  // Index for the pattern

    // Loop through the entire text
    while (i < N) {
        // If the characters of the pattern and text match
        if (pat[j] == txt[i]) {
            j++;  // Move to the next character in the pattern
            i++;  // Move to the next character in the text
        }

        // If j matches the length of the pattern, it means the entire pattern is found
        if (j == M) {
            std::cout << "Found pattern at index " << i - j << std::endl;
            // Reset j using the last lps value to continue searching for more occurrences
            j = lps[j - 1];
        }

        // If characters don't match, reset j using the LPS array
        else if (i < N && pat[j] != txt[i]) {
            if (j != 0)
                j = lps[j - 1];  // Reset j to the longest matching prefix
            else
                i++;  // If no prefix matches, just move to the next character in the text
        }
    }
}

int main() {
    std::string txt = "ABABDABACDABABCABAB";  // The text in which we want to search
    std::string pat = "ABABCABAB";  // The pattern we want to search for
    KMPsearch(pat, txt);  // Perform the KMP search
}

```
Output
```
std::string txt = "ABABDABACDABABCABAB";  // The text in which we want to search
std::string pat = "ABABCABAB";  // The pattern we want to search for

```

### 2. Rabin-Karp Algorithm
The Rabin-Karp algorithm uses hashing to find patterns in the string.
``` cpp
#include <iostream>
#include <string>

// d is the number of characters in the input alphabet (for ASCII, it's 256)
// q is a prime number used as a modulus to reduce the hash values
const int d = 256;
const int q = 101;  // A prime number for modulus in hash function

// Rabin-Karp Search function to find occurrences of pattern in the text
void rabinKarpSearch(const std::string &pat, const std::string &txt) {
    int M = pat.length();  // Length of the pattern
    int N = txt.length();  // Length of the text
    int i, j;
    int p = 0;  // Hash value for the pattern
    int t = 0;  // Hash value for the current window of text
    int h = 1;  // The value of h will be "pow(d, M-1) % q"

    // Precompute h = d^(M-1) % q for use in removing the first character's contribution to the rolling hash
    for (i = 0; i < M - 1; i++) {
        h = (h * d) % q;
    }
    // After this loop, h will be equal to (d^(M-1)) % q, which helps in rolling hash calculation

    // Calculate the hash value for the pattern and the first window of the text
    for (i = 0; i < M; i++) {
        p = (d * p + pat[i]) % q;  // Hash for the pattern
        t = (d * t + txt[i]) % q;  // Hash for the current window of the text
    }

    // Slide the pattern over the text one character at a time
    for (i = 0; i <= N - M; i++) {

        // Check if the current hash values of the text window and the pattern match
        if (p == t) {
            // If hash values match, check each character to ensure it's an exact match
            for (j = 0; j < M; j++) {
                if (txt[i + j] != pat[j])
                    break;
            }

            // If the pattern matches the current window in the text
            if (j == M) {
                std::cout << "Pattern found at index " << i << std::endl;
            }
        }

        // Calculate the hash for the next window of text:
        // Remove the leading character of the current window and add the trailing character
        if (i < N - M) {
            t = (d * (t - txt[i] * h) + txt[i + M]) % q;

            // We might get a negative value for the new hash, so we convert it to positive
            if (t < 0) {
                t = (t + q);
            }
        }
    }
}

int main() {
    std::string txt = "ABCCDDAEFG";  // The text in which to search
    std::string pat = "CDD";         // The pattern to search for
    rabinKarpSearch(pat, txt);       // Execute the Rabin-Karp search algorithm
}
```
Output
```
std::string txt = "ABCCDDAEFG";
std::string pat = "CDD";
```
