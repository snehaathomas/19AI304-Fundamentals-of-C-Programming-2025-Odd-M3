# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M3
# IAPR-3- Module 3 - FoC
## 5. Implementation of one-dimensional array and multidimensional array.
## 6. Implementation of string manipulation.
# Ex.No:11
  Formulate a C program to convert a given decimal number into its binary equivalent and display it.
# Date : 27.12.2025
# Aim:
To formulate a C program to convert a decimal number into its binary equivalent and display it.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3: 
  Declare variables: num (input number), rem (remainder), binary[] (array to store binary digits), and loop counters i and k.
### Step 4: 
  Read the decimal number from the user.
### Step 5: 
  Initialize i = 0.
### Step 6: 
  Repeat while num > 0:
  Divide num by 2 and store the remainder in binary[i].
  Increment i.
  Update num = num / 2.
### Step 7: 
  Display the binary digits in reverse order (from i-1 down to 0).
### Step 8: 
   Stop
# Program:
```
#include <stdio.h>
int main()
{
int a,r,d=0,c=1;
printf("Enter decimal number: ");
scanf("%d",&a);
int temp=a;
while(temp>0)
{
    r=temp%2;
    d=d+(r*c);
    c=c*10;
    temp=temp/2;
}
printf("%d in decimal = %d in binary", a,d);
return 0;
}
```
# Output:
<img width="1187" height="366" alt="Screenshot 2025-12-27 074432" src="https://github.com/user-attachments/assets/eeb2ed05-a3eb-4b15-848a-1f764ba67639" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M3
# IAPR-3- Module 3 - FoC
# Ex.No:12
  Develop a C program to read a matrix and find its saddle point. A saddle point is an element that is the minimum in its row and also the maximum in its column. If such an element exists, display its position and value.
# Date : 27.12.2025
# Aim:
  To develop a C program that inputs a matrix, checks each row for its minimum element, verifies whether that element is also the maximum in its corresponding column, and displays the saddle point and its position if it exists.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3: 
 Declare variables i, j, k, m, min, max and a position array pos[2][2].
### Step 4: 
 Read the order of the square matrix m.
### Step 5: 
 Declare an m × m matrix and read its elements.
### Step 6: 
 Display the matrix.
### Step 7: 
   For each row `i` from `0` to `m−1`:
- **Step 7.1:** Set `min` as the first element of the row.  
- **Step 7.2:** Scan the row to find its minimum element and store its position in `pos[0]`.  
- **Step 7.3:** Let `j` be the column of this minimum element.  
- **Step 7.4:** Set `max` as the first element of column `j`.  
- **Step 7.5:** Scan column `j` to find its maximum element and store its position in `pos[1]`.  
### Step 8: 
  Check if the row minimum equals the column maximum:
- If `min == max` **and their positions match**, then the element is a **saddle point**.
- Print the saddle point value and its position.
### Step 9: 
  Stop
# Program:
```
#include <stdio.h>
int main()
{
    int i, j, k, m;
    int min, max;
    int pos[2][2];
    scanf("%d", &m);
    int a[m][m];
    for (i = 0; i < m; i++)
    {
        for (j = 0; j < m; j++)
        {
            scanf("%d", &a[i][j]);
        }
    }
    for (i = 0; i < m; i++)
    {
        min = a[i][0];
        pos[0][0] = i;
        pos[0][1] = 0;
        for (j = 1; j < m; j++)
        {
            if (a[i][j] < min)
            {
                min = a[i][j];
                pos[0][1] = j;
            }
        }
        j = pos[0][1];
        max = a[0][j];
        pos[1][0] = 0;
        pos[1][1] = j;
        for (k = 1; k < m; k++)
        {
            if (a[k][j] > max)
            {
                max = a[k][j];
                pos[1][0] = k;
            }
        }
        if (min == max && pos[0][0] == pos[1][0])
        {
            printf("Saddle Point: %d\n", min);
            printf("Position: (%d, %d)\n", pos[0][0], pos[0][1]);
            return 0;
        }
    }
    printf("No Saddle Point\n");
    return 0;
}
```
# Output:
<img width="391" height="260" alt="image" src="https://github.com/user-attachments/assets/8c2aa5a9-0536-48a5-a1fe-d15d56e96a1e" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M3
# IAPR-3- Module 3 - FoC
# Ex.No:13
  Formulate a C program to reverse a string entered by the user and display the reversed string.
# Date : 27.12.2025
# Aim:
  To formulate a C program that reads a string from the user, reverses it, and prints the reversed string.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3: 
  Declare two character arrays: `s` to store the input string and `d` to store the reversed string.
### Step 4: 
  Read the string from the user using `scanf("%[^\n]s", s);`
### Step 5: 
  Find the length of the string `s` by traversing it until the null character `'\0'` is encountered.
### Step 6: 
  Initialize a counter `j` for the reversed string.
### Step 7: 
  Copy characters from the end of `s` to the beginning of `d` using a loop until all characters are copied in reverse order.
### Step 8: 
  Terminate the reversed string `d` with the null character `'\0'`.
### Step 9: 
  Print the reversed string.
### Step 10: 
  Stop
# Program:
```
#include <stdio.h>
int main()
{
    char s[100];
    scanf("%[^\n]s",s);
    int c=0;
    for(int i=0;s[i]!='\0';i++)
    {
        c++;
    }
    for(int i=c-1;i>=0;i--)
    printf("%c",s[i]);
    return 0;
}
```
# Output:
<img width="358" height="145" alt="image" src="https://github.com/user-attachments/assets/d82bc46b-5dd4-49d0-ad77-0ee2be301792" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.

# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M3
# IAPR-3- Module 3 - FoC
# Ex.No:14
  Formulate a C program to count the frequency of each character in a given string and display the count of every character.
# Date : 27.12.2025
# Aim:
  To formulate a C program that accepts a string from the user and calculates the frequency of each character in the string.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3: 
  Declare a character array `s[100]` to store the input string, an integer array `visited[256]` initialized to `0`, and variables `i`, `n`, and `count`.
### Step 4: 
  Read the string from the user using `scanf("%[^\n]", s);`
### Step 5: 
  Calculate the length of the string using `strlen(s)` and store it in `n`.
### Step 6: 
 For each character `s[i]` in the string (from `i = 0` to `n - 1`):
 - If `visited[(unsigned char)s[i]] == 0` (character not yet counted):  
  - Initialize `count = 0`.  
  - Loop through the string again and increment `count` for every occurrence of `s[i]`.  
  - Print `s[i]` and its count.  
  - Set `visited[(unsigned char)s[i]] = 1` to mark it as counted.
### Step 7: 
  Repeat Step 6 for all characters.
### Step 8:
  Stop
# Program:
```
#include <stdio.h>
#include <string.h>
int main()
{
    char s[100];
    int visited[256] = {0};
    int i, j, n, count;
    scanf("%[^\n]", s);
    n = strlen(s);
    for (i = 0; i < n; i++)
    {
        if (visited[(unsigned char)s[i]] == 0)
        {
            count = 0;
            for (j = 0; j < n; j++)
            {
                if (s[i] == s[j])
                {
                    count++;
                }
            }
            printf("%c : %d\n", s[i], count);
            visited[(unsigned char)s[i]] = 1;
        }
    }
    return 0;
}
```
# Output:
<img width="380" height="252" alt="image" src="https://github.com/user-attachments/assets/a77e61d6-0079-4397-a6de-6b0bb1fd097a" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M3
# IAPR-3- Module 3 - FoC
# Ex.No:15
  Formulate a C program to remove duplicate words from a given string and display the string with only unique words.
# Date : 27.12.2025
# Aim:
  To formulate a C program to remove duplicate words from a given string and display the string with only unique words.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3: 
  Declare a character array `str` to store the input string and a 2D array `words` to store individual words.
### Step 4: 
  Read the input string using `scanf("%[^\n]s", str);`
### Step 5: 
 Split the string into words:
 - Traverse the string character by character.  
 - When a space is encountered, terminate the current word with `'\0'` and move to the next row in `words`.  
 - Otherwise, copy the character into the current word.
### Step 6: 
  Compare each word with all other words to detect duplicates:
  - If a duplicate is found, mark it by setting the first character to `'\0'`.
### Step 7: 
  Print all words that are not marked as duplicates.
### Step 8: 
  Stop
# Program:
```
#include <stdio.h>
#include <string.h>
int main()
{
    char str[200];
    char words[50][50];
    int i, j, k = 0, w = 0;
    scanf("%[^\n]s", str);
    for (i = 0; str[i] != '\0'; i++)
    {
        if (str[i] == ' ')
        {
            words[w][k] = '\0';
            w++;
            k = 0;
        }
        else
        words[w][k++] = str[i];
    }
    words[w][k] = '\0';
    w++;
    for (i = 0; i < w; i++)
    {
        if (words[i][0] == '\0')
            continue;

        for (j = i + 1; j < w; j++)
        {
            if (strcmp(words[i], words[j]) == 0)
            words[j][0] = '\0';
        }
    }
    for (i = 0; i < w; i++)
    {
        if (words[i][0] != '\0')
        printf("%s ", words[i]);
    }
    return 0;
}
```
# Output:
<img width="393" height="119" alt="image" src="https://github.com/user-attachments/assets/47969e6a-834e-461c-a6db-efca09d510ad" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.
Thus, the program was implemented and executed successfully, and the required output was obtained.

