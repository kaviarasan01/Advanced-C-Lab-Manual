EXP NO:1 C PROGRAM FOR ARRAY OF STRUCTURE TO CHECK ELIGIBILITY FOR THE VACCINE.

Aim:
To write a C program for array of structure to check eligibility for the vaccine person age above 6 years of age.

Algorithm:
1.	Declare structure eligible with age (integer) and n (character array)
2.	Declare variable e of type eligible
3.	Input age and name using scanf, store in e
4.	If e.age <= 6
-	Print "Vaccine Eligibility: No"
Else
-	Print "Vaccine Eligibility: Yes"
5.	Print details (e.age, e.n)
6.	Return 0
 
Program:
```
#include <stdio.h>

struct eligible {
    int age;
    char name[50];
};

int main() {
    int n, i;
    printf("Enter number of persons: ");
    scanf("%d", &n);

    struct eligible e[n];  // array of structures

    for (i = 0; i < n; i++) {
        printf("\nEnter name of person %d: ", i + 1);
        scanf("%s", e[i].name);

        printf("Enter age of person %d: ", i + 1);
        scanf("%d", &e[i].age);

        if (e[i].age <= 6) {
            printf("Vaccine Eligibility: No\n");
        } else {
            printf("Vaccine Eligibility: Yes\n");
        }

        printf("Details - Name: %s, Age: %d\n", e[i].name, e[i].age);
    }

    return 0;
}
```

Output:

<img width="350" height="315" alt="image" src="https://github.com/user-attachments/assets/5b636356-785b-4f80-8fc5-05dc67c96ebd" />



Result:
Thus, the program is verified successfully. 



EXP NO:2 C PROGRAM FOR PASSING STRUCTURES AS FUNCTION ARGUMENTS AND RETURNING A STRUCTURE FROM A FUNCTION
Aim:
To write a C program for passing structure as function and returning a structure from a function

Algorithm:
1.	Define structure numbers with members a and b.
2.	Declare variable n of type numbers.
3.	Prompt the user to enter values for a and b.
4.	Input values for a and b into n using scanf.
5.	Call the add function with n as an argument.
6.	Print the result returned by the add function.
7.	Return 0
 
Program:
```
#include <stdio.h>

// Step 1: Define structure
struct numbers {
    int a;
    int b;
};

// Step 5: Function to add values
int add(struct numbers n) {
    return n.a + n.b;
}

int main() {
    struct numbers n;  // Step 2: Declare variable

    // Step 3: Prompt user
    printf("Enter value for a: ");
    scanf("%d", &n.a);

    printf("Enter value for b: ");
    scanf("%d", &n.b);

    // Step 6: Call add function and print result
    int result = add(n);
    printf("Sum = %d\n", result);

    return 0;  // Step 7
}
```
Output:
<img width="365" height="211" alt="image" src="https://github.com/user-attachments/assets/a5931734-0772-4d00-938c-8c049207720e" />


Result:
Thus, the program is verified successfully


 
EXP.NO:3 C PROGRAM TO READ A FILE NAME FROM USER AND WRITE THAT FILE USING FOPEN()

Aim:
To write a C program to read a file name from user

Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p.
Declare a character array name to store the file name.
4.	Prompt the user to enter a file name.
Use scanf to input the file name into the name array.
5.	Print a message indicating that the file with the specified name has been created successfully.
6.	Use fopen to open a file with the name provided by the user in write mode ("w").
-	If successful, continue to the next step.
-	If unsuccessful, print an error message and exit the program with a non-zero status.
1.	Print a message indicating that the file has been opened successfully.
2.	Use fclose to close the file.
3.	Print a message indicating that the file has been closed.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
 
Program:
```
#include <stdio.h>

int main() {
    FILE *p;             // Step 3: Declare file pointer
    char name[50];       // Step 3: Declare character array for filename

    // Step 4: Prompt user
    printf("Enter the file name: ");
    scanf("%s", name);

    // Step 5: Print creation message
    printf("File '%s' has been created successfully.\n", name);

    // Step 6: Open file in write mode
    p = fopen(name, "w");
    if (p == NULL) {
        printf("Error: Unable to create or open the file.\n");
        return 1;  // Exit with non-zero status
    }

    // Step 7: File opened successfully
    printf("File '%s' has been opened successfully.\n", name);

    // Step 8: Close file
    fclose(p);

    // Step 9: Print closing message
    printf("File '%s' has been closed.\n", name);

    // Step 10: End program
    return 0;
}
```


Output:
<img width="694" height="194" alt="image" src="https://github.com/user-attachments/assets/7d14cb83-42eb-41b9-80d6-5543b2bfb7c4" />



Result:
Thus, the program is verified successfully
 


EXP NO:4   PROGRAM TO READ A FILE NAME FROM USER, WRITE THAT FILE AND INSERT TEXT IN TO THAT FILE
Aim:
To write a C program to read, a file and insert text in that file
Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p.
Declare character arrays name and text. Declare an integer variable num.
4.	Prompt the user to enter a file name and the number of strings.
Use scanf to input the file name into the name array and the number of strings into the num variable.
5.	Use fopen to open a file with the name provided by the user in write mode ("w").
-	If successful, continue to the next step.
-	If unsuccessful, print an error message and exit the program with a non-zero status.
6.	Print a message indicating that the file has been opened successfully.
1.	Use a loop to input strings from the user and write them to the file using fputs.
2.	Use fclose to close the file.
3.	Print a message indicating that data has been added successfully.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
 
Program:

```
#include <stdio.h>

int main() {
    FILE *p;             // Step 3: File pointer
    char name[50];       // Step 3: Array for filename
    char text[100];      // Step 3: Array for text
    int num, i;

    // Step 4: Prompt user
    printf("Enter the file name: ");
    scanf("%s", name);

    printf("Enter the number of strings to insert: ");
    scanf("%d", &num);

    // Step 5: Open file in write mode
    p = fopen(name, "w");
    if (p == NULL) {
        printf("Error: Unable to open file.\n");
        return 1;  // Exit with non-zero status
    }

    // Step 6: File opened successfully
    printf("File '%s' opened successfully.\n", name);

    // Step 7: Loop to input and write strings
    for (i = 0; i < num; i++) {
        printf("Enter string %d: ", i + 1);
        scanf("%s", text);   // read string (no spaces)
        fputs(text, p);      // write string to file
        fputs("\n", p);      // add newline for readability
    }

    // Step 8: Close file
    fclose(p);

    // Step 9: Success message
    printf("Data has been added successfully to '%s'.\n", name);

    return 0;  // Step 10
}
```

Output:

<img width="833" height="278" alt="image" src="https://github.com/user-attachments/assets/78300b83-807d-4e29-a1e3-3b7942a1e0f9" />


Result:
Thus, the program is verified successfully



Ex No 5 : C PROGRAM TO DISPLAY STUDENT DETAILS USING STRUCTURE

Aim:
The aim of this program is to dynamically allocate memory to store information about multiple subjects (name and marks), input the details for each subject, and then display the stored information. Finally, it frees the allocated memory to prevent memory leaks.

Algorithm:
1.Input the number of subjects.

2.Read the integer value n from the user, which represents the number of subjects.

3.Dynamically allocate memory:

4.Use malloc to allocate memory for n subjects. Each subject has a name (array of characters) and marks (integer).

5.If memory allocation fails (i.e., the pointer s is NULL), display an error message and exit the program.

6.Input the details of each subject

7.Use a for loop to read the name and marks of each subject using scanf. For each subject, store the name as a string and marks as an integer in the dynamically allocated memory.

8.Display the details of each subject

9.Use another for loop to print the name and marks of each subject.

10.Free the allocated memory

11.After all operations are done, call free(s) to release the dynamically allocated memory.

12.Return from the main function

13.End the program by returning 0.

Program:
```
#include <stdio.h>
#include <stdlib.h>

struct subject {
    char name[50];
    int marks;
};

int main() {
    int n, i;
    struct subject *s;

    // Step 1 & 2: Input number of subjects
    printf("Enter the number of subjects: ");
    scanf("%d", &n);

    // Step 3: Dynamically allocate memory
    s = (struct subject *)malloc(n * sizeof(struct subject));

    // Step 5: Check allocation
    if (s == NULL) {
        printf("Error: Memory allocation failed.\n");
        return 1; // Exit with non-zero status
    }

    // Step 6: Input details
    for (i = 0; i < n; i++) {
        printf("\nEnter name of subject %d: ", i + 1);
        scanf("%s", s[i].name);

        printf("Enter marks for subject %d: ", i + 1);
        scanf("%d", &s[i].marks);
    }

    // Step 7: Display details
    printf("\n--- Subject Details ---\n");
    for (i = 0; i < n; i++) {
        printf("Subject: %s, Marks: %d\n", s[i].name, s[i].marks);
    }

    // Step 8: Free memory
    free(s);

    return 0; // Step 9
}

```
Output:

<img width="729" height="408" alt="image" src="https://github.com/user-attachments/assets/71d09cf7-9345-425e-b010-3bb1fd4caff3" />


Result:
Thus, the program is verified successfully
