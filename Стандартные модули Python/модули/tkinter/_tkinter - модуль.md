# Первое знакомство

```python
import tkinter as tk  
  
win = tk.Tk()  
win.title("Мой первый эксперимент")  
  
# Изображение иконки  
photo = tk.PhotoImage(file="src/img/icon.png")  
win.iconphoto(None, photo)  
  
# Параметры конфигурации окна  
win.config(bg="#BAE873")  
  
# Начальный размер окна  
win.geometry("500x300+300+100") # width x height + translateX + translateY  
  
# Минимальный размер  
win.minsize(400, 250) # width height  
  
# Максимальный размер окна  
win.maxsize(600, 400) # width height  
  
# Возвожность интерактивного изменения размера окна  
win.resizable(True, True) # width height  
  
win.mainloop()
```

## [Размещение на форме](Размещение%20на%20форме.md)

## [Виджеты](Виджеты.md)

