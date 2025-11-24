##used libary tinkter as main module
import tkinter as tk
from tkinter import messagebox

# toggle password visibility
def toggle_password():
    global show
    if show:
        entry.config(show="*")
        eye_button.config(text="👁")   
        show=False
    else:
        entry.config(show="")
        eye_button.config(text="🙈")   
        show=True

# this function is used to check password 
def check_password():
    password=entry.get()

    has_upper=False
    has_lower=False
    has_digit=False
    has_special=False

    special_chars="!@#$%^&*()-_=+{}[];:'\",.<>?/\\|"  

    for ch in password:
        if ch.isupper():
            has_upper=True
        elif ch.islower():
            has_lower=True
        elif ch.isdigit():
            has_digit=True
        elif ch in special_chars:
            has_special=True

 #if else conditional are used to check the password inpputed       

    if len(password)<8:
        messagebox.showerror("password is weak","password must be at least 8 characters long")
    elif not has_upper:
        messagebox.showerror("password is weak","password must have at least 1 uppercase letter")
    elif not has_lower:
        messagebox.showerror("password is weak","password must have at least 1 lowercase letter")
    elif not has_digit:
        messagebox.showerror("password is weak","password must have at least 1 number")
    elif not has_special:
        messagebox.showerror("password is weak","password must have at least 1 special character")
    else:
        messagebox.showinfo("success","password is strong!")
        entry.delete(0,tk.END)


#this is gui window
#this adds design to the code and makes it look unique
window=tk.Tk()
window.title("password Checker")
window.geometry("420x260")
window.configure(bg="#BFEFFF")

title_label=tk.Label(window,text="password CHECKER",font=("Arial",18,"bold"),bg="#4F7684")
title_label.pack(pady=10)

frame=tk.Frame(window,bg="#BFEFFF")
frame.pack()

entry=tk.Entry(frame,width=30,show="*",font=("Arial",14))
entry.pack(side=tk.LEFT,pady=10)

show=False
eye_button=tk.Button(frame,text="👁",font=("Arial",12),command=toggle_password)
eye_button.pack(side=tk.LEFT,padx=5)

check_button=tk.Button(window,text="Check password",font=("Arial",14),
                         bg="#12E119",fg="white",command=check_password)
check_button.pack(pady=10)
#this will run the code!
window.mainloop()
