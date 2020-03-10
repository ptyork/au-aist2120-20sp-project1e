# Project 1e: Average Grade Calculator

You have been asked to write a script that pulls in student grades from multiple assignments and provides an average for each student. Each file will contain the student ID and a grade representing a single assignment. The output should simply show a single report of each student and their average grade.

The script, `average_grades.py`, should: 

0. Create an empty dictionary called `grades_dict`, which WILL hold a student id as key and an (initially empty) list of floats as grades (again, it's just EMPTY {} to start with)
1. Ask the user for a file name (if the user presses enter, break to step 6)
2. Open the requested file 
3. Iterate over each line in the file (each line will contain a student id and a grade) 
4. For each line:
    - split the line to get separate values for the id and the grade
    - check to see if the dictionary contains the student id
    - if so, append the grade to the existing list of grades for that student (this will usually happen after the first file is processed)
    - if not, use the student id as key and store a NEW list in the dictionary with the grade as it's first value (this will usually happen only for the first file)
5. Repeat from step 1
6. When done, print a title line as shown in the example.
7. Iterate over each of the keys in your dictionary
8. For each key, retrieve the list of grades, average them, and then print out a line of the final report

Each line in any grades input file will be in the format `student_id,grade`.

When outputing the final report (i.e., line 9), you should print the id left-aligned within 25 spaces followed by the average right-aligned within 10 spaces with 1 decimal point. Total for each line should be 35 characters. Here's an example run with partial results: 
```
Enter file (blank to stop): grades-1.txt
Enter file (blank to stop): grades-2.txt
Enter file (blank to stop): grades-3.txt
Enter file (blank to stop):

STUDENT                     AVERAGE
-----------------------------------
alan.alda                      76.7
benny.barker                   82.7
chloe.carter                  100.0
...
```

## REQUIRED IMPLEMENTATION NOTES 

1. More hints on step 4: you will want to check the grades dictionary to see if the student id is `in` the dictionary. If so, you want to `append()` the grade and if not, you want to create a new list with that grade as the first item. Remember that if your student id is stored in a variable called `stu_id` and the list is in the dictionary, the entire list can be accessed using standard dictionary syntax like `grades_dict[stu_id]`. So assuming you have a new grade to add, you can append to the list of grades directly like this: `grades_dict[stu_id].append(newgrade)`. And remember that it is easy to create a list with a single value like this: `[123]`. So setting the value is likewise straightforward: `grades_dict[stu_id] = [newgrade]`

2. You MUST modify __all three__ of the grades files to add YOU and provide yourself with a grade for each assignment. JUST edit and save the files using VS code or another text editor. No Python code required here.

3. You MUST use either the format() function or an f-string to format your lines of text. In other words, you __cannot__ use the center(), ljust() and rjust() methods. Those methods are okay, but don't use them here.

When done, be sure to test the heck out of this and then submit the __project1 directory__ in Mimir.

## OPTIONAL CHALLENGES 

1. Create a second version of the script, `average_grades2.py`. Import the os module, and instead of asking for file names, use the `os.listdir()` method to iterate over ALL of the files in the current folder. If the filename begins with "grades" and ends with ".txt", then you should automatically process it. In other words, the script will have no user input and will simply output the averages report. Easier than it sounds...basically just replace the while loop and user input with a for/in loop.

2. Improve the logic so that a grades file can contain one __OR MORE__ grades per student per line. For example, you might have a line with `alan.alda,100,77,94`. If so, add all three grades to the list.
