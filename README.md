def show_menu():
    print("\nTo-Do List Menu:")
    print("1. Show To-Do List")
    print("2. Add Task")
    print("3. Remove Task")
    print("4. Exit")

def show_tasks(tasks):
    print("\nYour To-Do List:")
    if not tasks:
        print("No tasks yet!")
    else:
        for idx, task in enumerate(tasks, 1):
            print(f"{idx}. {task}")

def main():
    tasks = []
    while True:
        show_menu()
        choice = input("Enter your choice: ")
        if choice == "1":
            show_tasks(tasks)
        elif choice == "2":
            task = input("Enter the task: ")
            tasks.append(task)
            print("Task added.")
        elif choice == "3":
            show_tasks(tasks)
            try:
                num = int(input("Enter the task number to remove: "))
                if 1 <= num <= len(tasks):
                    removed = tasks.pop(num - 1)
                    print(f"Removed: {removed}")
                else:
                    print("Invalid task number.")
            except ValueError:
                print("Please enter a valid number.")
        elif choice == "4":
            print("Goodbye!")
            break
        else:
            print("Invalid choice, please try again.")

if __name__ == "__main__":
    main()
