tasks = []

def show_tasks():
    if len(tasks) == 0:
        print("No tasks available.")
    else:
        print("Your tasks:")
        for i, task in enumerate(tasks):
            print(i + 1, "-", task)

while True:
    print("\nTo-Do List Menu")
    print("1. Add Task")
    print("2. View Tasks")
    print("3. Remove Task")
    print("4. Mark Task as Completed")
    print("5. Exit")

    choice = input("Choose an option: ")

    if choice == "1":
        task = input("Enter a new task: ")
        tasks.append(task)
        print("Task added!")

    elif choice == "2":
        show_tasks()

    elif choice == "3":
        show_tasks()
        num = int(input("Enter task number to remove: "))
        if 0 < num <= len(tasks):
            tasks.pop(num - 1)
            print("Task removed!")
        else:
            print("Invalid number")

    elif choice == "4":
        show_tasks()
        num = int(input("Enter task number completed: "))
        if 0 < num <= len(tasks):
            tasks[num - 1] = tasks[num - 1] + " ✔"
            print("Task marked as completed!")
        else:
            print("Invalid number")

    elif choice == "5":
        print("Goodbye!")
        break

    else:
        print("Invalid choice")
