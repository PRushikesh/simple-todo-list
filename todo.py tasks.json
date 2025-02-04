import json

TODO_FILE = "tasks.json"

def load_tasks():
    try:
        with open(TODO_FILE, "r") as file:
            return json.load(file)
    except FileNotFoundError:
        return []

def save_tasks(tasks):
    with open(TODO_FILE, "w") as file:
        json.dump(tasks, file, indent=4)

def add_task(task):
    tasks = load_tasks()
    tasks.append(task)
    save_tasks(tasks)
    print(f"✅ Task '{task}' added!")

def view_tasks():
    tasks = load_tasks()
    if not tasks:
        print("📭 No tasks found.")
    else:
        print("\n📝 To-Do List:")
        for i, task in enumerate(tasks, 1):
            print(f"{i}. {task}")

def remove_task(index):
    tasks = load_tasks()
    if 0 <= index < len(tasks):
        removed = tasks.pop(index)
        save_tasks(tasks)
        print(f"❌ Task '{removed}' removed!")
    else:
        print("⚠ Invalid task number.")

def main():
    while True:
        print("\nOptions: [1] Add [2] View [3] Remove [4] Exit")
        choice = input("Enter choice: ")

        if choice == "1":
            task = input("Enter task: ")
            add_task(task)
        elif choice == "2":
            view_tasks()
        elif choice == "3":
            view_tasks()
            try:
                index = int(input("Enter task number to remove: ")) - 1
                remove_task(index)
            except ValueError:
                print("⚠ Please enter a valid number.")
        elif choice == "4":
            print("👋 Exiting... Bye!")
            break
        else:
            print("⚠ Invalid choice, try again.")

if name == "__main__":
    main()
