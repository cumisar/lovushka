#ii
- Упражнение 1.1
	*10 12 8 3 6 19 False 4 16 6 16*
- Упражнение 1.2
```
(/ (+ 5 4 (- 2 (- 3 (+ 6 (/ 4 5)))))
		(* 3 (- 6 2) (- 2 7)))
```
- Упражнение 1.3
```
(define (sum-square a b) 
	(+ (* a a) (* b b)))

(define (max-square a b c) 
	(if (and (< a b) (< a c)) 
		(sum-square b c))
	(if (and (< b a) (< b c)) 
		(sum-square a c))
	(else 
		(sum-square b c))
	) 
```
- Упражнение 1.4
```
(define (a-plus-abs-b a b)
	((if (> b 0) + -) a b)
)
```

*Если  b>0 (+ a b), иначе (- a b)*
- Упражнение 1.5
*Если порядок аппликативный, то программа выдаст 0, иначе зациклиться*

#iii
Дизассемблирование 
- Builtin 
```
type(int)
```
![[Pasted image 20241229190319.png]]
- Класс 
```
	class Person:

    def __init__(self, name, age, money):

        self.name = name

        self.age = age

        self.money = money

    def spend(self, amount):

        self.money-=amount

    def change_name(self, new_name):

        self.name= new_name
```
![[Pasted image 20241229200605.png]]
#iv
```
def example_function(a, b, c=10, *args, d=20, e, **kwargs):
	pass

#Получение параметров:
inspect.signature(example_function)
<Signature (a, b, c=10, *args, d=20, e, **kwargs)>
```
#v
#vi
Конспект: [[1.0]]]
#vii
1. 
```
class Empty:
    pass

dir(Empty)
['__class__', '__delattr__', '__dict__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getstate__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__le__', '__lt__', '__module__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__', '__weakref__']
```
2. 
```
Empty == 0
False

Empty == Empty
True
```
#viii
- Стандартный
``` 
	import math
	dis.dis(math)
```
#ix
- Внешняя
```
inspect.getsource(inspect.getsource)

lines, lnum = getsourcelines(object)\n  return \'\'.join(lines)\n'

```
- Внутренняя 
```
inspect.getsource(inspect.getsourcelines)

object = unwrap(object)    
lines, lnum = findsource(object)

if istraceback(object):
	object = object.tb_frame
	
	   # for module or frame that corresponds to module, return all source lines
	if (ismodule(object) or\n        (isframe(object) and object.f_code.co_name == "<module>")):
	        return lines, 0
	else:
	     return getblock(lines[lnum:]), lnum + 1\n'
```
#x
1. 
``` 
"strin" + "g" is "string"

don't know how to disassemble bool objects
```
![[Pasted image 20241229190116.png]]
2.```
```
x = "strin"
x + 'g' is 'string'
```
![[Pasted image 20241229185924.png]]
 
#xi
``` type(len)
<class 'builtin_function_or_method'>
```
#xii
- **CPython**: Основная и наиболее широко используемая реализация Python, написанная на языке C.
- **expression (выражение)**: Комбинация значений и операторов, которая вычисляется в одно значение.

- **statement (инструкция)**: Наименьшая автономная единица выполнения в языке Python, такая как присваивание, цикл или вызов функции.

- **function (функция)**: Определённая блоком *def* или *lambda* часть кода, которую можно вызвать с аргументами для выполнения определённой задачи и возврата значения.

- **parameter (параметр)**: Переменная, указанная в определении функции, которая принимает значение аргумента при вызове функции.

- **argument (аргумент)**: Значение, передаваемое функции при её вызове.

- **garbage collection (сборка мусора)**: Механизм автоматического управления памятью, который освобождает память, занятую объектами, на которые больше нет ссылок.

- **reference count (счётчик ссылок)**: Число, показывающее, сколько ссылок указывает на объект; используется для управления временем жизни объекта.

- **type (тип)**: Категория данных, определяющая, какие значения объект может принимать и какие операции с ним допустимы.

- **virtual machine (виртуальная машина)**: Абстрактная вычислительная среда, в которой выполняется байт-код Python.

- **bytecode (байт-код)**: Низкоуровневое представление исходного кода Python, которое интерпретируется виртуальной машиной Python.