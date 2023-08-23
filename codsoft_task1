import tkinter as tk
from tkinter import messagebox

class ToDoListApp:
    def __init__(self, root):
        self.root = root
        self.root.title("To-Do List App")
        
        self.tasks = []
        
        self.task_label = tk.Label(root, text="Task:")
        self.task_label.pack(pady=10)
        
        self.task_entry = tk.Entry(root)
        self.task_entry.pack(pady=5)
        
        self.add_button = tk.Button(root, text="Add Task", command=self.add_task)
        self.add_button.pack(pady=5)
        
        self.update_button = tk.Button(root, text="Update Task", command=self.update_task)
        self.update_button.pack(pady=5)
        
        self.remove_button = tk.Button(root, text="Remove Task", command=self.remove_task)
        self.remove_button.pack(pady=5)
        
        self.clear_button = tk.Button(root, text="Clear List", command=self.clear_list)
        self.clear_button.pack(pady=10)
        
        self.task_listbox = tk.Listbox(root, selectmode=tk.SINGLE)
        self.task_listbox.pack(padx=10, pady=10)
        
    def add_task(self):
        task = self.task_entry.get()
        if task:
            self.tasks.append(task)
            self.update_task_listbox()
            self.task_entry.delete(0, tk.END)
    
    def update_task(self):
        selected_index = self.task_listbox.curselection()
        if selected_index:
            selected_index = selected_index[0]
            new_task = self.task_entry.get()
            if new_task:
                self.tasks[selected_index] = new_task
                self.update_task_listbox()
                self.task_entry.delete(0, tk.END)
    
    def remove_task(self):
        selected_index = self.task_listbox.curselection()
        if selected_index:
            selected_index = selected_index[0]
            self.tasks.pop(selected_index)
            self.update_task_listbox()
    
    def clear_list(self):
        self.tasks = []
        self.update_task_listbox()
    
    def update_task_listbox(self):
        self.task_listbox.delete(0, tk.END)
        for task in self.tasks:
            self.task_listbox.insert(tk.END, task)

root = tk.Tk()
todo_app = ToDoListApp(root)
root.mainloop()
