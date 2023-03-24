# Reto_6
Aqui podran encontrar todos los puntos del reto 6

## Punto 1

![image](https://user-images.githubusercontent.com/124615019/227581696-35f1d2cb-31ed-4f32-98d8-3caddde50efe.png)

Para este punyo busque las formulas de el volumen de una esfera y de un cono, la suma me daria el volumen total, asi mismo busque las formulas de el area superficial de una esfera y el cono, sumarlas. Para utilizar pi, imporyte math y para multiplicar por pi utilice math.pi

### Código

```
import math
def volumenFigura(r1:float, r2:float, h:float) ->float:
    volFigura = (4/3*math.pi*r1**3)+(1/3*h*math.pi*r2**2)
    return volFigura
def areaSuperficial(r1:float, r2:float, h:float) ->float:
    areaSuper= (4*math.pi*r1**2)+((math.pi*r2**2)+(math.pi*r2*h))
    return areaSuper

if __name__ == "__main__":
    r1 = float(input("Ingrese el radio de la esfera: "))
    r2 = float(input("Ingrese el radio del cono: "))
    h = float(input("Ingrese la altura del cono: "))

    volumen = volumenFigura(r1,r2,h)
    print("El volumen de la figura es "+ str(volumen))

    area = areaSuperficial(r1,r2,h)
    print("El area superficial de la figura es "+ str(area))
```
    
## Punto 2
    
![image](https://user-images.githubusercontent.com/124615019/227582037-7e2e9d11-08c9-41d6-8c20-105d2d2887c3.png)
    
Definí las dos funciones para el perimetro y el area, se buscaron las formulas, la de un circulo x2 y se le sumaban las del rectangulo, como el anterior punto utilice math.pi

### Código
```
import math 
def calcularArea(a:float, b:float, r:float) -> float:
    areaDelCriculo = (math.pi * r**2)*2
    areaDelRectangulo = a * b
    areaTotal = areaDelCriculo + areaDelRectangulo
    return areaTotal
def calcularPerimetro(a:float, b:float, r:float) -> float:
    perimetroCircular = (2*math.pi*r)*2
    perimetroRectangulo = a*2 + b*2
    perimetroTotal = perimetroCircular + perimetroRectangulo
    return perimetroTotal

if __name__ == '__main__':
   a = float(input("Ingrese la base del rectangulo: "))
   b = float(input("Ingrese la altura del rectangulo: "))
   r = float(input("Ingrese el radio de los circulos: "))
   area = calcularArea(a, b, r)
   print("El area total de la figura es "+ str(round(area, 5))+"")

   perimetro = calcularPerimetro(a, b, r)
   print("El perimetro total de la figura es "+ str(perimetro)+"")
```

## Punto 3

Diseñe una función que calcule la cantidad de carne de aves en kilos si se tienen N gallinas, M gallos y K pollitos cada uno pesando 6 kilos, 7 kilos y 1 kilo respectivamente.

Para este definí una función y así con esa función, dada la cantidad de gallinas, gallos y pollitos, el código me diera el total de carne

### Código
```
def cantidadCarne(gallinas:float, gallos:float, pollitos:float) -> float:
    cantidadTotal = (gallinas*6) + (gallos*7) + (pollitos)
    return cantidadTotal

if __name__ == '__main__':
    gallinas = float(input("Ingrese la cantidad de gallinas: "))
    gallos = float(input("Ingrese la cantidad de gallos: "))
    pollitos = float(input("Ingrese la cantidad de pollitos: "))
    cantidadTotal1 = cantidadCarne(gallinas, gallos, pollitos)
    print("la cantidad de carne es "+ str(cantidadTotal1))
```

## Punto 4

Mi mamá me manda a comprar P panes a 300 cada uno, M bolsas de leche a 3300 cada una y H huevos a 350 cada uno. Hacer un programa que me diga las vueltas (o lo que quedo debiendo) cuando me da un billete de B pesos.

Para se definio la funcion que calculara dada la cantidad de panes, bolsas de leche y huevos por el precio, la persona ingresa con cuanto va a pagar y si le sobra cuanto le sobra o si debe con un - y lo que deba para comprar todo lo que quiere.

### Código
```
def calcularVueltas(P:float, M:float, H:float, B:float) -> float:
    calcularDevueltas = B-((P*300)+(M*3300)+(H*350))
    return calcularDevueltas
if __name__ == '__main__':
    P = float(input("Ingrese la cantidad de panes que va comprar: "))
    M = float(input("Ingrese la cantidad de bolsas de leche que va a comprar: "))
    H = float(input("Ingrese la cantidad de huevos que va a comprar: "))
    B = float(input("Ingrese el valor del billete con el que va a pagar: "))
    devueltasTotales = calcularVueltas(P, M, H, B)
    if devueltasTotales >= 0 :
       print("Sus devueltas son "+ str(devueltasTotales) +" pesos")
    elif devueltasTotales < 0 :
       print("Le faltan "+ str(devueltasTotales) +" pesos")
```

## Punto 5

Haga un programa que utilice una función para calcular el valor de un préstamo Cusando interés compuesto del i por nmeses.

Busque la formula del interes compuesto, después definí la función; una persona ingresa el monto que quiere que le presten, así mismo ingresa cuanto es el interes por mes y a cuantos meses hizo el prestamo. El código le dira cuanto es el total que debe devolver al banco con el prestamo y los interes.

### Código
```
def prestamo(c:float, i:float, n:float) -> float:
    return c*(1+(i/100))**n

if __name__ == "__main__":
    c = float(input("Ingrese el monto del prestamo: "))
    i = float(input("Ingrese el interes: "))
    n = float(input("Ingrese el número de meses: "))

    prest = prestamo(c,i,n)
    print("El interes compuesto es "+str(prest))
```

## Punto 6

El número de contagiados de Covid-19 en el país de NuncaLandia se duplica cada día. Hacer un programa que diga el número total de personas que se han contagiado cuando pasen D días a partir de hoy, si el número de contagiados actuales es C.

Para este problema defini una función dada la cantidad de contagiados y se elevava a los días que habian transcurrido desde el día cero.

### Código
```
def cantidadContagios(d:int) -> float:
    c = 4*(2**d) # 4 es la cantidad de contagiados hoy
    return c
if __name__ == '__main__':
    d = int(input("Ingrese la cantidad de días que han pasado: "))
    contagiados = cantidadContagios(d)
    print("Al trasncurrir "+str(d)+" días la cantidad de contagiados de Covid-19 en NuncaLandia es "+ str(contagiados))
```

## Punto 7

Escriba un programa que pida 5 números reales y calcule las siguientes usando una función para cada una:

El promedio

La mediana

El promedio multiplicativo (multiplica todos y luego calcula la raíz de la cantidad de operadores)

Ordenar los números de forma ascendente

Ordenar los numeros de forma descendente

La potencia del mayor número elevado al menor número

La raíz cúbica del menor número

Para este punto importe las funciones que realice y las guarde, las llame ecuaciones y con esto, las traje al código y que me imprimiera los datos que necesitaba.

### Código
```
import ecuaciones 
    
    
if __name__ == '__main__':
    a = float(input("Ingrese el primer número: "))
    b = float(input("Ingrese el segundo número: "))
    c = float(input("Ingrese el tercer número: "))
    d = float(input("Ingrese el cuarto número: "))
    e = float(input("Ingrese el quinto número: "))
    m1, m2, m3, m4, m5 = ecuaciones.ordenarCinco(a,b,c,d,e)

    promedio = ecuaciones.calcularPromedio(a, b, c, d, e)
    print("El promedio de los números ingresados es "+str(promedio))
    
    Mediana = ecuaciones.ordenarCinco(a, b, c, d, e)
    print("La mediana de los números ingresados es "+str(m3))

    potencia = ecuaciones.promedioMultiplicativo(a, b, c, d, e)
    print('El promedio multiplicativo es '+str(potencia)+'')

    ordenarAscendente = ecuaciones.ordenarCinco(a, b, c, d, e)
    print("Se ordeno de forma ascendente: "+str(ordenarAscendente))
    
    ordenarDesendete= ecuaciones.ordenarCinco(a,b,c,d,e)
    print("Se ordeno de forma desendente "+ str(m5)+","+ str(m4)+","+ str(m3)+","+ str(m2)+","+ str(m1)+"" )

    potencia = ecuaciones.potencia(m1,m5)
    print("El resultado del número mayor elevado el menor es: "+ str(potencia))

    raiz = ecuaciones.raiz(m1)
    print("La raiz cubica del número menor es: "+ str(raiz) )
```

## Punto 8 

Para el punto anterior incluir las funciones en un archivo independiente e importarlas para su uso.

Busque las formulas y para organizar me guie con lo que publico el profesor en slack, asi defni todas las funciones la llame "escuaciones" y las importe a el punto 7.

```
def calcularPromedio(a:float, b:float, c:float, d:float, e:float) ->float:
    return (a + b + c + d + e) / 5
def ordenarDos(b,c):
  if b <= c:
    m2, m3 = b, c
  else:
    m2, m3 = c, b
  return m2, m3
def ordenarTres(a,b,c):
  m1 , m2, m3 = a, b, c
  if a <= b and a <= c:
    m1 = a
    m2, m3 = ordenarDos(b,c)
  elif b <= a and b <= c:
    m1 = b
    m2, m3 = ordenarDos(a,c)
  elif c <= b and c <= a:
    m1 = c
    m2, m3 = ordenarDos(b,a)
  return m1, m2, m3
def ordenarCuatroNums(a,b,c,d):
  m1, m2, m3, m4 = a, b, c, d
  if a <= b and a <= c and a<=d:
    m1 = a
    m2, m3, m4= ordenarTres(b,c,d)
  elif b <= a and b <= c and b <= d:
    m1 = b
    m2, m3, m4 = ordenarTres(a,c,d)
  elif c <= b and c <= a and c <= d:
    m1 = c
    m2, m3, m4 = ordenarTres(b,a,d)
  elif d <= a and d <= b and d <= c:
    m1 = d
    m2, m3, m4 = ordenarTres(a,b,c)
  return m1, m2, m3, m4
def ordenarCinco(a,b,c,d,e):
  m1, m2, m3, m4, m5 = a, b, c, d , e
  if a <= b and a <= c and a<=d and a<=e:
    m1 = a
    m2, m3, m4, m5= ordenarCuatroNums(b,c,d,e)
  elif b <= a and b <= c and b<=d and b<=e:
    m1 = b
    m2, m3, m4, m5= ordenarCuatroNums(a,c,d,e)
  elif c <= a and c <= b and c<=d and c<=e:
    m1 = c
    m2, m3, m4, m5= ordenarCuatroNums(a,b,d,e)
  elif d <= a and d <= b and d<=c and d<=e:
    m1 = d
    m2, m3, m4, m5= ordenarCuatroNums(a,b,c,e)
  elif e <= a and e <= b and e<=c and e<=d:
    m1 = e
    m2, m3, m4, m5= ordenarCuatroNums(a,b,c,d)
  return m1, m2, m3, m4, m5

def promedioMultiplicativo(a:float,b:float,c:float,d:float,e:float):
   return (a*b*c*d*e)**(1/5)

def potencia(m1:float, m5:float):
   return m5**m1

def raiz(m1:float):
   return m1**1/3
```

## Punto 9

¿Qué es pip?

Es un sistema de paquetes con los cuales administramos paquetes de sofware  en python, viene instalado en python desde la version 3.4 . Cuando tienes un modulo y quieres solo importarlo al código poniendo pip al princio ya quedara sin necesidad de ir y buscarlo.

¿Cómo funciona?

Pip es usado como soporte en la nube 
Se pone en el código "pip install (el modulo)"[1]

## Punto 10

Para instalar los modulos en windos solo necesitas desde python poner "pip install (el modulo)", para Mac y linux necesitas poner al principio sudo "sudo pip install (el modulo)". [2]

### Modulos

Colletions

CSV

Random

Tkinter

Requests

BeautifulSoup4 

Numpy

Pandas

Matplotlib

Django [3]

### Referencias y citas de los puntos 9 y 10

[1] Pip (Administrador de Paquetes) (no date) Wikipedia. Wikimedia Foundation. Available at: https://es.wikipedia.org/wiki/Pip_(administrador_de_paquetes)#:~:text=pip%20es%20un%20sistema%20de,pip3%20para%20Python3)%20por%20defecto. (Accessed: March 24, 2023). 

[2] Gibbs, F. (2013) Instalar Módulos de Python con Pip, Programming Historian. Available at: https://programminghistorian.org/es/lecciones/instalar-modulos-python-pip (Accessed: March 24, 2023). 

[3] Shaik, H.K. (2020) 11 bibliotecas y Módulos de Python que todo desarrollador debería conocer, Geekflare. Available at: https://geekflare.com/es/popular-python-libraries-modules/ (Accessed: March 24, 2023). 

## !Graciasss espero sea de su agrado el repo¡, esten pendientes al siguiente repo programadores
