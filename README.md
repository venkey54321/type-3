class TodoList:
    def _init_(self):
        self.tasks = []

    def add_task(self, task):
        self.tasks.append(task)

    def remove_task(self, task):
        if task in self.tasks:
            self.tasks.remove(task)
        else:
            print("Task not found.")

    def list_tasks(self):
        if not self.tasks:
            print("No tasks in the list.")
        else:
            print("Tasks:")
            for index, task in enumerate(self.tasks, start=1):
                print(f"{index}. {task}")

def main():
    todo_list = TodoList()

    while True:
        print("\nOptions:")
        print("1. Add Task")
        print("2. Remove Task")
        print("3. List Tasks")
        print("4. Quit")

        choice = input("Enter your choice (1/2/3/4): ")

        if choice == "1":
            task = input("Enter the task: ")
            todo_list.add_task(task)
            print("Task added.")
        elif choice == "2":
            task = input("Enter the task to remove: ")
            todo_list.remove_task(task)
        elif choice == "3":
            todo_list.list_tasks()
        elif choice == "4":
            print("Exiting the To-Do List application. Goodbye!")
            break
        else:
            print("Invalid choice. Please choose a valid option.")

if _name_ == "_main_":
    main()
