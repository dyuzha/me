
# \_\_new__
---
>[!Note] Sample
```python
__new__(cls, [...])
```
- Это первый метод, который будет вызван при инициализации объекта. Он принимает в качестве параметров класс и потом любые другие аргументы, который переданы в  `__init__`

*P.S. Хорошо описан в документации*

# \_\_init__
---
>[!Note] Sample
```python
__init__(self, [...])
```
- Инициализатор класса. Ему передается все, с чем был вызыван первоначальный конструктор. 

>[!Example]
```python
class FileObject:
    def __init__(self, filepath='puth/to/file', filename='sample.txt'):
        self.file = open(join(filepath, filename), 'r+')

    def __del__(self):
    self.file.close()
    del self.file
```



# \_\_del__ 
---
>[!Note] Sample
```python
__del__(self)
```
- Деструктор объекта. 
>[!Info] `__del__` всегда вызывается по завершении работы интерпритатора



