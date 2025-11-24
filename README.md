Password Strength Checker

  Project Overview

The Password Checker is a GUI-based desktop application built with Python and Tkinter. 
It helps users verify if their passwords meet standard security criteria 
(length, uppercase, lowercase, numbers, and special character) before using them.

  Features

Real-time Validation: Checks password against 5 security rules.

Visual Feedback: Uses pop-up message boxes to tell the user exactly what is missing.

Visibility Toggle: Includes an "Eye" button to show/hide the password while typing.

Secure Input: Characters are masked with * by default for privacy.

  Technologies Used

Language: Python3

Library: Tkinter  (Standard GUI toolkit)

   How to Run

Make sure Python is installed.

Clone the repository or download main.py.

Run the command:

python main.py

  
  Testing Instructions

Weak Test: Type "abcd" -> Click Check. Result: Error (Too short).

Medium Test: Type "Password123" -> Click Check. Result: Error (No special char).

Strong Test: Type "P@ssword123" -> Click Check. Result: Success Message.
