# Окно

```python
import tkinter as tk  
  
win = tk.Tk()  
win.title("Мой заголовок")  
win.geometry("500x300+300+100") # width x height + translateX + translateY  
win.resizable(False, False) # width height  
  
win.mainloop()
```

