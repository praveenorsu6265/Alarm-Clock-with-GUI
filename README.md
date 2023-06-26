# Alarm-Clock-with-GUI
# Alarm Clock with GUI using python
import tkinter as tk
from tkinter import messagebox
import datetime
import winsound

def set_alarm():
    alarm_time = entry.get()
    current_time = datetime.datetime.now().strftime("%H:%M")
    
    if alarm_time == current_time:
        messagebox.showinfo("Alarm", "Wake up!")
        winsound.PlaySound("sound.wav", winsound.SND_ASYNC)
    else:
        messagebox.showinfo("Alarm", "Alarm set for " + alarm_time)

root = tk.Tk()
root.title("Alarm Clock")

frame = tk.Frame(root)
frame.pack(pady=20)

label = tk.Label(frame, text="Enter alarm time (HH:MM):")
label.pack()

entry = tk.Entry(frame)
entry.pack()

button = tk.Button(frame, text="Set Alarm", command=set_alarm)
button.pack()

root.mainloop()
