import tkinter as tk
from tkinter import ttk
import random
import string

class PasswordGenerator:
    def __init__(self, root):
        self.root = root
        self.root.title("Random Password Generator")
        
        self.length_label = ttk.Label(root, text="Password Length:")
        self.length_label.pack(pady=10)
        
        self.length_entry = ttk.Entry(root)
        self.length_entry.pack(pady=5)
        
        self.generate_button = ttk.Button(root, text="Generate Password", command=self.generate_password)
        self.generate_button.pack(pady=10)
        
        self.result_label = ttk.Label(root, text="")
        self.result_label.pack(pady=10)
        
    def generate_password(self):
        try:
            length = int(self.length_entry.get())
            if length < 4:
                self.result_label.config(text="Password length must be at least 4 characters")
            else:
                characters = string.ascii_letters + string.digits + string.punctuation
                password = ''.join(random.choice(characters) for _ in range(length))
                self.result_label.config(text=f"Generated Password: {password}")
        except ValueError:
            self.result_label.config(text="Invalid input for password length")

root = tk.Tk()
password_generator = PasswordGenerator(root)
root.mainloop()
