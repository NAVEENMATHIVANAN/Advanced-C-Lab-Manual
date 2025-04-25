# Advance C LAB

## EXP NO:1 C PROGRAM FOR ARRAY OF STRUCTURE TO CHECK ELIGIBILITY FOR THE VACCINE.

### Aim:
To write a C program for array of structure to check eligibility for the vaccine person age above 6 years of age.

### Algorithm:

1.Declare structure eligible with age (integer) and n (character array)
2.Declare variable e of type eligible
3.Input age and name using scanf, store in e
4.If e.age <= 6
5.Print "Vaccine Eligibility: No" Else
6.Print "Vaccine Eligibility: Yes"
7.Print details (e.age, e.n)
8.Return 0
### Program:
```
#include <stdio.h>
#include <string.h>

struct Person {
    char name[50];
    int age;
};

int main() {
    struct Person person;

    scanf("%d", &person.age);
    scanf("%s", person.name);

    printf("Age:%d\n", person.age);
    printf("Name:%svaccine:%d\n", person.name,person.age);
    
    if (person.age > 18) {
        printf("eligibility:yes\n");
    } else {
        printf("eligibility:no\n");
    }

    return 0;
}

```
### Output:

![image](https://github.com/user-attachments/assets/2465ae1a-2fd4-464c-9b0b-c5727d6f1e65)


### Result: 
Thus, the program is verified successfully.

## EXP NO:2 C PROGRAM FOR PASSING STRUCTURES AS FUNCTION ARGUMENTS AND RETURNING A STRUCTURE FROM A FUNCTION 

### Aim: 
To write a C program for passing structure as function and returning a structure from a function

### Algorithm:

1.Define structure numbers with members a and b.
2.Declare variable n of type numbers.
3.Prompt the user to enter values for a and b.
4.Input values for a and b into n using scanf.
5.Call the add function with n as an argument.
6.Print the result returned by the add function.
7.Return 0
### Program:

```
#include <stdio.h>
#include <string.h>

// Define structure
struct Student {
    char name[50];
    int roll;
    float marks;
};

// Function to take input — structure passed by value
void displayStudent(struct Student s) {
    printf("\n--- Student Details ---\n");
    printf("Name       : %s\n", s.name);
    printf("Roll No.   : %d\n", s.roll);
    printf("Marks      : %.2f\n", s.marks);
}

// Function to return a structure
struct Student getStudent() {
    struct Student temp;

    printf("Enter student name: ");
    getchar(); // To consume newline left by previous input
    fgets(temp.name, sizeof(temp.name), stdin);
    temp.name[strcspn(temp.name, "\n")] = '\0'; // Remove newline

    printf("Enter roll number: ");
    scanf("%d", &temp.roll);

    printf("Enter marks: ");
    scanf("%f", &temp.marks);

    return temp;
}

int main() {
    struct Student s1;

    // Get student data from function
    s1 = getStudent();

    // Pass structure to function
    displayStudent(s1);

    return 0;
}


```

### Output:

![image](https://github.com/user-attachments/assets/6ba83095-2bb7-40de-9ece-cb8840fbbf77)

### Result:
Thus, the program is verified successfully

## EXP.NO:3 C PROGRAM TO READ A FILE NAME FROM USER AND WRITE THAT FILE USING FOPEN()

### Aim: 
To write a C program to read a file name from user

### Algorithm:

1.Include the necessary header file stdio.h.
2.Begin the main function.
3.Declare a file pointer p. Declare a character array name to store the file name.
4.Prompt the user to enter a file name. Use scanf to input the file name into the name array.
5.Print a message indicating that the file with the specified name has been created successfully.
6.Use fopen to open a file with the name provided by the user in write mode ("w").
7.If successful, continue to the next step.
8.If unsuccessful, print an error message and exit the program with a non-zero status.
9.Print a message indicating that the file has been opened successfully.
10.Use fclose to close the file.
11.Print a message indicating that the file has been closed.
12.End the main function.
13.Return 0 to indicate successful program execution.
### Program:
```
#include <stdio.h>

int main() {
    char filename[100];
    FILE *file;

    scanf("%s", filename);

    // Create and open the file using fopen()
    file = fopen(filename, "w");

    // Check if the file was created successfully
    if (file == NULL) {
        printf("Error! Could not create file %s\n", filename);
        return 1;
    }

    // Display messages to indicate success
    printf("%s File Created Successfully\n", filename);
    printf("%s File Opened\n", filename);

    // Close the file
    fclose(file);
    printf("%s File Closed\n", filename);

    return 0;
}
```

### Output:

![image](https://github.com/user-attachments/assets/a98e6c39-82bb-4048-a3ee-9fe9e308f5f5)


### Result: 

Thus, the program is verified successfully


## EXP NO:4 PROGRAM TO READ A FILE NAME FROM USER, WRITE THAT FILE AND INSERT TEXT IN TO THAT FILE 

### Aim:
To write a C program to read, a file and insert text in that file 

### Algorithm:
1.Include the necessary header file stdio.h.
2.Begin the main function.
3.Declare a file pointer p. Declare character arrays name and text. Declare an integer variable num.
4.Prompt the user to enter a file name and the number of strings. Use scanf to input the file name into the name array and the number of strings into the num variable.
5.Use fopen to open a file with the name provided by the user in write mode ("w").
6.If successful, continue to the next step.
7.If unsuccessful, print an error message and exit the program with a non-zero status.
8.Print a message indicating that the file has been opened successfully.
9.Use a loop to input strings from the user and write them to the file using fputs.
10.Use fclose to close the file.
11.Print a message indicating that data has been added successfully.
12.End the main function.
13.Return 0 to indicate successful program execution.

### Program:
```
#include <stdio.h>
int main(){
    FILE *h;
    char fg[100];
    scanf("%s\n",fg);
    h = fopen(fg,"w");
    printf("%s Opened",fg);
    int f,*ptr;
    scanf("%d",&f);
    int x;
    for(int i=0;i<f;i++){
        scanf("%d",&x);
        ptr = &x;
        fwrite(ptr,1,sizeof(x),h);         
    }
    printf("\nData added Successfully");
    
    fclose(h);
    
    
    
}
```
### Output:

![image](https://github.com/user-attachments/assets/c8dc6e8e-30a4-43d8-8d41-7945f9689aa1)


### Result: 
Thus, the program is verified successfully

## Ex No 5 : C PROGRAM TO DISPLAY STUDENT DETAILS USING STRUCTURE

### Aim: 
The aim of this program is to dynamically allocate memory to store information about multiple subjects (name and marks), input the details for each subject, and then display the stored information. Finally, it frees the allocated memory to prevent memory leaks.

### Algorithm:
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

### Program:

```
#include <stdio.h>

// Define structure
struct Student {
    char name[50];
    int roll;
    float marks;
};

int main() {
    struct Student s;

    // Taking input
    printf("Enter student name: ");
    fgets(s.name, sizeof(s.name), stdin);

    printf("Enter roll number: ");
    scanf("%d", &s.roll);

    printf("Enter marks: ");
    scanf("%f", &s.marks);

    // Displaying information
    printf("\n--- Student Details ---\n");
    printf("Name       : %s", s.name);
    printf("Roll No.   : %d\n", s.roll);
    printf("Marks      : %.2f\n", s.marks);

    return 0;
}


```

### Output:

![image](https://github.com/user-attachments/assets/e685ad81-9c82-4d12-a6dd-e3939dfd7281)


### Result:

Thus, the program is verified successfully
