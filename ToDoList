# This is first task given by CodSoft as Python Developer

#Simple ToDo List GUI App where user can easily add and save tasks and delete tasks

import tkinter as tk
from tkinter import messagebox

# Function 1 Add Task
def add_task():
    task = entry.get()
    if task:
        listbox.insert(tk.END, task)
        entry.delete(0, tk.END)
        save_tasks()
    else:
        messagebox.showwarning("Warning", "Please enter a task!")

# Function 2 Delete Task
def delete_task():
    try:
        selected_task_index = listbox.curselection()[0]
        deleted_task = listbox.get(selected_task_index)
        listbox.delete(selected_task_index)
        save_tasks()
        messagebox.showinfo("Task Deleted", f'Task "{deleted_task}" deleted successfully!')
    except IndexError:
        messagebox.showwarning("Warning", "Please select a task to delete!")

# Function 3 Save Task
def save_tasks():
    tasks = listbox.get(0, tk.END)
    with open("tasks.txt", "w") as file:
        for task in tasks:
            file.write(task + "\n")

# Function 5 Load Task
def load_tasks():
    try:
        with open("tasks.txt", "r") as file:
            tasks = file.read().splitlines()
            for task in tasks:
                listbox.insert(tk.END, task)
    except FileNotFoundError:
       print('Create text file')


# Simple GUI
root = tk.Tk()
root.title = 'Todo List - Sarfaraz CodSoft'
root.configure(bg='#1E1E1E')


headerframe = tk.Frame(root, bg="#1E1E1E")
headerframe.pack(fill="x", padx=10, pady=10)

heading = tk.Label(headerframe, text="Welcome to ToDo List", bg='#1E1E1E', fg='white', font=("Arial", 15))
heading.pack()

taskinputframe = tk.Frame(root, bg="#1E1E1E")
taskinputframe.pack(pady=10, padx=10, fill="x")

entry = tk.Entry(taskinputframe,  width=30 , bg="#333333", fg="white", font=("Arial", 12))
entry.pack(fill="both", expand=True, padx=(0, 10))

buttonframe = tk.Frame(root, bg="#1E1E1E")
buttonframe.pack(pady=10)

add_button = tk.Button(buttonframe, text="Add Task", bg="white", fg="black", font=("Arial", 12), padx=10, command=add_task)
add_button.pack()

delete_button = tk.Button(root, text="Delete Task",bg="white", fg="black", font=("Arial", 12), padx=10, command=delete_task)
delete_button.pack()

listbox = tk.Listbox(root, selectmode=tk.SINGLE, width=40)
listbox.pack(pady=10)


load_tasks()

# Run the main loop
root.mainloop()
