# todo-list-python

Python To-Do List Application
Project Overview

This is a simple command-line To-Do List application developed using Python.

It helps users manage their daily tasks by adding, removing, completing, and displaying tasks.

Features
Add new tasks.
Remove existing tasks.
Mark tasks as completed.
Display all tasks with their status.
Exit the application.
Technologies Used
Python
Object-Oriented Programming (OOP)
Lists and Dictionaries
Functions and Loops
Conditional Statements
How to Run
Download or clone this repository.
Open the project folder.
Run the following command:
bash
python todo.py

Learning Outcomes
Understanding Python classes and objects.
Working with lists and dictionaries.
Understanding functions and loops.
Implementing basic CRUD operations.
Building a menu-driven application.
Conclusion

This project is a beginner-friendly Python application that demonstrates basic programming concepts and object-oriented programming.

# ==================================================
# PROJECT: TO-DO LIST APPLICATION
# ==================================================

# 1. Create a class called TodoList
# This class is used to manage all tasks.
class TodoList:

    # 2. Constructor method
    # It runs automatically when we create an object.
    # self.tasks = [] creates an empty list to store tasks.
    def __init__(self):
        self.tasks = []

    # 3. Add Task Function
    # This function adds a new task to the list.
    def add_task(self, task):

        # Store the task and its completion status.
        # Initially, every task is not completed.
        self.tasks.append({"task": task, "completed": False})

        # Display success message.
        print("Task added successfully!")

    # 4. Remove Task Function
    # This function removes a task from the list.
    def remove_task(self, task):

        # Check each task in the list.
        for t in self.tasks:

            # Check whether the entered task matches.
            if t["task"] == task:

                # Remove the matching task.
                self.tasks.remove(t)

                # Display success message.
                print("Task removed successfully!")
                return

        # If the task is not found.
        print("Task not found in the list.")

    # 5. Mark Completed Function
    # This function changes the task status to completed.
    def mark_completed(self, task):

        # Check each task in the list.
        for t in self.tasks:

            # Find the matching task.
            if t["task"] == task:

                # Change completed status from False to True.
                t["completed"] = True

                # Display success message.
                print("Task marked as completed!")
                return

        # If the task is not found.
        print("Task not found in the list.")

    # 6. Display Tasks Function
    # This function displays all available tasks.
    def display_tasks(self):

        # Check whether the task list is not empty.
        if self.tasks:

            # Display heading.
            print("Tasks:")

            # Display each task with its number.
            for i, t in enumerate(self.tasks, start=1):

                # Check task completion status.
                status = "Completed" if t["completed"] else "Not Completed"

                # Print task number, name and status.
                print(f"{i}. {t['task']} - {status}")

        # If there are no tasks.
        else:
            print("No tasks in the list.")


# 7. Main Function
# This is the main function of the application.
def main():

    # Create an object for the TodoList class.
    # The constructor creates an empty task list.
    todo_list = TodoList()

    # 8. Start an infinite loop.
    # The menu continues until the user selects Exit.
    while True:

        # Display the menu options.
        print("\nTODO LIST MENU:")
        print("1. Add a task")
        print("2. Remove a task")
        print("3. Mark a task as completed")
        print("4. Display tasks")
        print("5. Exit")

        # 9. Get the user's choice.
        choice = input("Enter your choice (1/2/3/4/5): ")

        # 10. If the user selects 1, add a task.
        if choice == '1':
            task = input("Enter task to add: ")
            todo_list.add_task(task)

        # 11. If the user selects 2, remove a task.
        elif choice == '2':
            task = input("Enter task to remove: ")
            todo_list.remove_task(task)

        # 12. If the user selects 3, mark a task as completed.
        elif choice == '3':
            task = input("Enter task to mark as completed: ")
            todo_list.mark_completed(task)

        # 13. If the user selects 4, display all tasks.
        elif choice == '4':
            todo_list.display_tasks()

        # 14. If the user selects 5, exit the application.
        elif choice == '5':
            print("Exiting...")
            break

        # 15. If the user enters an invalid option.
        else:
            print("Invalid choice. Please enter a valid option.")


# 16. Function Calling
# Program execution starts by calling the main function.
main()

