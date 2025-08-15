todo_list = []
def show_tasks():
    if not todo_list:
        print("\nNo tasks found.")
    else:
        print("\nYour Tasks:")
        for i, task in enumerate(todo_list, 1):
            print(f"{i}. {task}")
while True:
    print("\n--- TO-DO LIST ---")
    print("1. Add Task")
    print("2. Update Task")
    print("3. View Tasks")
    print("4. Delete Task")
    print("5. Exit")
    choice = input("Enter choice: ")
    if choice == "1":
        task = input("Enter new task: ")
        todo_list.append(task)
        print("Task added!")
    elif choice == "2":
        show_tasks()
        num = int(input("Enter task number to update: "))
        if 1 <= num <= len(todo_list):
            todo_list[num-1] = input("Enter new task: ")
            print("Task updated!")
        else:
            print("Invalid task number.")
    elif choice == "3":
        show_tasks()
    elif choice == "4":
        show_tasks()
        num = int(input("Enter task number to delete: "))
        if 1 <= num <= len(todo_list):
            todo_list.pop(num-1)
            print("Task deleted!")
        else:
            print("Invalid task number.")
    elif choice == "5":
        break
    else:
        print("Invalid choice.")
