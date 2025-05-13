# EX-26-AREA-OF-RECTANGLE-USING- POINTER
## AIM
To write a C Program to find area of rectangle using pointer.

## ALGORITHM
1.	Start the program.
2.	Read two numbers.
3.	Calculate the area of rectangle using the formula area=(x)(*y)
4.	Display the result.
5.	Stop the program.

## PROGRAM
```
#include <stdio.h>

int main() {
    float length, width, area;
    float *ptrLength, *ptrWidth;
    ptrLength = &length;
    ptrWidth = &width;
    printf("Enter the length of the rectangle: ");
    scanf("%f", ptrLength);

    printf("Enter the width of the rectangle: ");
    scanf("%f", ptrWidth);

    area = (*ptrLength) * (*ptrWidth);

    printf("Area of the rectangle: %.2f\n", area);

    return 0;
}
```
## OUTPUT
		       	
![image](https://github.com/user-attachments/assets/d6c1e5d1-f46d-4f91-9182-2cbf2e437b9c)


## RESULT
Thus the program to find area of rectangle using pointer has been executed successfully
 
 


# EX-27-DYNAMIC-MEMORY-ALLOCATION
## AIM
To write a C Program to print 'WELCOME' using malloc() and free().

## ALGORITHM
1.	Start the program.
2.	Read a string variable.
3.	Allocate memory using malloc().
4.	Display the string.
5.	Remove the allocated memory using free().
6.	Stop the program.

## PROGRAM
```
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int main() {

    char *str = (char *)malloc(8 * sizeof(char));

    if (str == NULL) {
        printf("Memory allocation failed.\n");
        return 1;
    }
    strcpy(str, "WELCOME");

    printf("%s\n", str);

    free(str);

    return 0;
}
```
## OUTPUT

![image](https://github.com/user-attachments/assets/624fdc6d-fd15-4b81-8a24-dfa10a3dcb24)


## RESULT
Thus the program to print 'WELCOME' using malloc() and free() has been executed successfully
 
.



# EX-28-STUDENT-INFORMATION-USING-STRUCTURE

## AIM

To write a C Program to store the student information and display it using structure.

## ALGORITHM

1.	Start the program.
2.	Create a student structure with name, roll number and marks as members.
3.	Using structure variable read the structure members and print them.
4.	Stop the program.

## PROGRAM
```
#include <stdio.h>
struct Student {
    int id;
    char name[50];
    float marks;
};

int main() {
    struct Student student;
    printf("Enter student ID: ");
    scanf("%d", &student.id);

    printf("Enter student name: ");
    scanf(" %[^\n]", student.name); 
    printf("Enter student marks: ");
    scanf("%f", &student.marks);
    printf("\n--- Student Information ---\n");
    printf("ID    : %d\n", student.id);
    printf("Name  : %s\n", student.name);
    printf("Marks : %.2f\n", student.marks);

    return 0;
}
```

## OUTPUT
![image](https://github.com/user-attachments/assets/3ea2dcca-f73c-42af-8a8c-9a1bd56a5b4e)


## RESULT

Thus the program to store the student information and display it using structure has been executed successfully
 
 


# EX-29-EMPLOYEE-STRUCTURE-SALARY-CALCULATION

## AIM

To write a C Program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure.

## ALGORITHM

1.	Start the program.
2.	Create an employee structure with name, id and salary details as members.
3.	Using structure variable read the structure members.
4.	Calculate the gross salary and print the details.
5.	Stop the program.

## PROGRAM
```
#include <stdio.h>

struct Employee {
    int id;
    char name[50];
    float basicSalary;
    float grossSalary;
};

int main() {
    struct Employee emp[3];
    int i;
    for (i = 0; i < 3; i++) {
        printf("\nEnter details for Employee %d:\n", i + 1);
        printf("ID: ");
        scanf("%d", &emp[i].id);

        printf("Name: ");
        scanf(" %[^\n]", emp[i].name);

        printf("Basic Salary: ");
        scanf("%f", &emp[i].basicSalary);

        float hra = 0.20f * emp[i].basicSalary;
        float da  = 0.80f * emp[i].basicSalary;
        emp[i].grossSalary = emp[i].basicSalary + hra + da;
    }

    printf("\n--- Employee Salary Details ---\n");
    for (i = 0; i < 3; i++) {
        printf("\nEmployee %d:\n", i + 1);
        printf("ID           : %d\n", emp[i].id);
        printf("Name         : %s\n", emp[i].name);
        printf("Basic Salary : %.2f\n", emp[i].basicSalary);
        printf("Gross Salary : %.2f\n", emp[i].grossSalary);
    }
    return 0;
}
```

 ## OUTPUT

![image](https://github.com/user-attachments/assets/8be401ce-2403-4820-92e1-a86a21dbc08a)
![image](https://github.com/user-attachments/assets/45d5a0da-758f-4e80-be75-de1185814b58)



## RESULT

Thus the C program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure
 




# EX – 30 -STUDENTS MARK -TOTAL &AVERAGE USING STRUCURE

## AIM
Create a C program to calculate the total and average of student using structure.

## ALGORITHM 

Step 1: Start the program.
Step 2: Define a struct student with:
•	name: a character array (size 10) for the student's name (not used in the logic).
•	rollno: an integer for the student's roll number (also unused).
•	subject[5]: an array to store marks of 5 subjects.
•	total: an integer to store total marks.
Step 3: Declare an array s[2] of type struct student for 2 students. Also declare variables n, i, and j for input 
             and iteration.
Step 4: Input Loop (i = 0 to 1):
•	Read an integer n (but it's not used later — possibly intended for roll number or placeholder).
•	Loop j = 0 to 4:
o	Read 5 subject marks into s[i].subject[j].
Step 5: Total Marks Calculation Loop (i = 0 to 1):
•	Initialize s[i].total to 0.
•	Loop j = 0 to 4:
o	Add each subject mark to s[i].total.
Step 6: Override Total (Hardcoded):
•	Set s[0].total = 374;
•	Set s[1].total = 383;
           This step overwrites the computed totals. It seems like testing or hardcoded totals — unnecessary if you’re 
                 already calculating them.
Step 7: Output Loop (i = 0 to 1):
•	Print s[i].total for each student.
Step 8: End the program.

## PROGRAM


#include <stdio.h>
struct Student {
    int rollNo;
    char name[50];
    float marks[5]; 
    float total;
    float average;
};

int main() {
    struct Student student;
    int i;
    printf("Enter student roll number: ");
    scanf("%d", &student.rollNo);

    printf("Enter student name: ");
    student.total = 0;
    printf("Enter marks for 5 subjects:\n");
    for (i = 0; i < 5; i++) {
        printf("Subject %d: ", i + 1);
        scanf("%f", &student.marks[i]);
        student.total += student.marks[i];
    }
    student.average = student.total / 5;
    printf("\n--- Student Result ---\n");
    printf("Roll No : %d\n", student.rollNo);
    printf("Name    : %s\n", student.name);
    printf("Total   : %.2f\n", student.total);
    printf("Average : %.2f\n", student.average);

    return 0;
}


OUTPUT

 ![image](https://github.com/user-attachments/assets/ca9e99b9-47b9-475a-839f-8e7a5ddb6d71)



RESULT

Thus the C program to calculate the total and average of student using structure has been executed successfully.
	


