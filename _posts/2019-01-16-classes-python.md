---
title: Clases y objetos en Python
description: Clases y objetos en Python
categories: 
  - Blog
  - Python
comments: true
---

La clase es un bloque de código fundamental en Python. Es la base de muchos programas y bibliotecas, incluso también de la biblioteca estándar de Python. Entender qué son las clases, cuándo usarlas y cómo pueden ser útiles es esencial y el objetivo de este artículo. En el proceso, explicaremos qué significa el término Programación orientada a objetos y cómo se relaciona con las clases de Python.

**Todo es un objeto ...**

¿Para qué se utiliza exactamente la palabra clave `class`? Al igual que la función `def`, se refiere a la definición de cosas. Mientras que `def` se usa para definir una función, `class` se usa para definir una clase. Y que es una clase? Simplemente una agrupación lógica de datos y funciones (los últimos a menudo se denominan "métodos" cuando se definen dentro de una clase).

¿Qué entendemos por "agrupación lógica"? Bueno, una clase puede contener cualquier información que nos gustaría, y puede tener cualquier función (método) adjunta que nos plazca. En lugar de simplemente juntar cosas aleatorias bajo el nombre de "clase", tratamos de crear clases donde hay una conexión lógica entre las cosas. Muchas veces, las clases se basan en objetos que existen en el mundo real (como ‘Cliente’ o ‘Producto’). Otras veces, las clases se basan en conceptos de nuestro sistema, como `HTTPRequest` o `Owner`.

En cualquier caso, las clases son una técnica de modelado; Una forma de pensar sobre los programas. Cuando piensa en implementar su sistema de esta manera, se dice que está realizando una programación orientada a objetos. "Clases" y "objetos" son palabras que a menudo se usan indistintamente, pero en realidad no son lo mismo. Comprender qué los hace diferentes es la clave para entender qué son y cómo funcionan.

**..Así que todo es una clase?**

Las clases se pueden considerar como planos para crear objetos. Cuando defino una clase `Customer` utilizando la palabra clave `class`, en realidad no he creado un cliente. En su lugar, lo que he creado es una especie de manual de instrucciones para construir objetos `Customer`. Veamos el siguiente código de ejemplo:

```python
class Customer(object):
    """A customer of ABC Bank with a checking account. Customers have the
    following properties:

    Attributes:
        name: A string representing the customer's name.
        balance: A float tracking the current balance of the customer's account.
    """

    def __init__(self, name, balance=0.0):
        """Return a Customer object whose name is *name* and starting
        balance is *balance*."""
        self.name = name
        self.balance = balance

    def withdraw(self, amount):
        """Return the balance remaining after withdrawing *amount*
        dollars."""
        if amount > self.balance:
            raise RuntimeError('Amount greater than available balance.')
        self.balance -= amount
        return self.balance

    def deposit(self, amount):
        """Return the balance remaining after depositing *amount*
        dollars."""
        self.balance += amount
        return self.balance
```

La clase `Customer(object)` no crea un nuevo cliente. Es decir, solo porque hemos definido un `Customer` o Cliente no significa que hayamos creado uno; Simplemente hemos delineado el plano para crear un objeto `Customer`. Para hacerlo, llamamos al método `__init__` de la clase con el número adecuado de argumentos (menos `self`, que veremos en un momento).

Entonces, para usar el "plano" que creamos al definir la clase `Customer` (que se usa para crear objetos `Customer`), llamamos al nombre de la clase casi como si fuera una función: `jeff = Customer ('Jeff Knupp', 1000.0)` . Esta línea simplemente dice "use el modelo `Customer` para crear un nuevo objeto, al que me referiré como `jeff`".

El objeto `jeff`, conocido como instancia, es la versión realizada de la clase `Customer`. Antes de llamar a `Customer()`, no existía ningún objeto `Customer`. Podemos, por supuesto, crear tantos objetos de `Customer` como se desee. Sin embargo, todavía hay una sola clase `Customer`, independientemente de la cantidad de instancias de clase que hemos creado.

**self?**

Entonces, ¿qué pasa con ese parámetro `self` para todos los métodos de `Customer`? ¿Qué es? ¡Por qué, es la instancia, por supuesto! Dicho de otra manera, un método como el retiro o `withdraw` define las instrucciones para retirar dinero de la cuenta de algún cliente abstracto. Al llamar a `jeff.withdraw (100.0)`, esas instrucciones se utilizarán en la instancia de `jeff`.

Entonces, cuando decimos def `withdraw(self, amount):` "aquí decimos cómo retirar dinero de un objeto Cliente (al que llamaremos `self`) y una cifra en dólares (a la que llamaremos `amount`). `self` es la instancia del Cliente que está solicitando el retiro. Tampoco estoy haciendo analogías. `jeff.withdraw (100.0)` es solo una abreviatura para `Customer.withdraw (jeff, 100.0)`, que es un código perfectamente válido (si no se ve a menudo).

**__init__**

`self` puede tener sentido para otros métodos, pero ¿qué pasa con `__init__`? Cuando llamamos `__init__`, estamos en el proceso de crear un objeto, entonces, ¿cómo puede haber ya un `self`? Python nos permite extender el patrón `self` cuando los objetos también se construyen, aunque no se ajuste exactamente. Solo imagine que `jeff = Customer('Jeff Knupp', 1000.0)` es lo mismo que llamar a `jeff = Customer (jeff, 'Jeff Knupp', 1000.0)`; El `jeff` que se pasa también se hace el resultado.

Es por eso que cuando llamamos `__init__`, inicializamos objetos diciendo cosas como `self.name = name`. Recuerda, dado que `self` es la instancia, esto es equivalente a decir `jeff.name = name`, que es lo mismo que `jeff.name = 'Jeff Knupp'`. Del mismo modo, `self.balance = balance` es lo mismo que `jeff.balance = 1000.0.` Después de estas dos líneas, consideramos que el objeto `Customer` está "inicializado" y listo para usar.

**Tenga cuidado con `__init__`**

Después de que `__init__` haya terminado, la persona que llama el objeto puede asumir correctamente que ya está listo para usar. Es decir, después de `jeff = Customer('Jeff Knupp', 1000.0)`, podemos comenzar a hacer llamadas de depósitos y retiros en `jeff`; `jeff` es un objeto completamente inicializado.

Imagine por un momento que habíamos definido la clase `Customer` de manera ligeramente diferente:

```python
class Customer(object):
    """A customer of ABC Bank with a checking account. Customers have the
    following properties:

    Attributes:
        name: A string representing the customer's name.
        balance: A float tracking the current balance of the customer's account.
    """

    def __init__(self, name):
        """Return a Customer object whose name is *name*.""" 
        self.name = name

    def set_balance(self, balance=0.0):
        """Set the customer's starting balance."""
        self.balance = balance

    def withdraw(self, amount):
        """Return the balance remaining after withdrawing *amount*
        dollars."""
        if amount > self.balance:
            raise RuntimeError('Amount greater than available balance.')
        self.balance -= amount
        return self.balance

    def deposit(self, amount):
        """Return the balance remaining after depositing *amount*
        dollars."""
        self.balance += amount
        return self.balance
```
Esto puede parecer una alternativa razonable; simplemente necesitamos llamar a `set_balance` antes de comenzar a usar la instancia. Sin embargo, no hay forma de comunicárselo al que llama. Incluso si lo documentamos ampliamente, no podemos obligar al que llama a llamar a `jeff.set_balance (1000.0)` antes de llamar a `jeff.withdraw (100.0)`. Dado que la instancia de `jeff` ni siquiera tiene un atributo balance hasta que se llama a `jeff.set_balance`, esto significa que el objeto no se ha inicializado "completamente".

La regla de oro es, no introduzca un nuevo atributo fuera del método `__init__`, de lo contrario estaría entregando un objeto que no está completamente inicializado. Hay excepciones, por supuesto, pero es un buen principio a tener en cuenta. Esto es parte de un concepto más amplio de consistencia de objeto: no debería haber ninguna serie de llamadas a métodos que puedan hacer que el objeto entre en un estado que no tiene sentido.

Las consistencias (por ejemplo, "el saldo siempre debe ser un número no negativo") deben mantenerse tanto cuando se ingresa un método como cuando se sale de él. Debería ser imposible para un objeto entrar en un estado no válido simplemente llamando a sus métodos. No hace falta decir, entonces, que un objeto debe comenzar también en un estado válido, por lo que es importante inicializar todo en el método `__init__`.

**Atributos y métodos de instancia**

Una función definida en una clase se llama "método". Los métodos tienen acceso a todos los datos contenidos en la instancia del objeto; Pueden acceder y modificar cualquier cosa previamente establecida en uno mismo. Como se usan a sí mismos, requieren una instancia de la clase para poder usarlos. Por esta razón, a menudo se les llama "métodos de instancia".

Si hay "métodos de instancia", entonces seguramente hay otros tipos de métodos, ¿verdad? Sí, los hay, pero estos métodos son un poco más esotéricos. Los cubriremos brevemente aquí, pero siéntase libre de investigar estos temas con mayor profundidad.

**Métodos estáticos**

Los atributos de clase son atributos que se establecen en el nivel de clase, a diferencia del nivel de instancia. Los atributos normales se introducen en el método `__init__`, pero algunos atributos de una clase se mantienen para todas las instancias en todos los casos. Por ejemplo, considere la siguiente definición de un objeto `Car`:

```python
class Car(object):

    wheels = 4

    def __init__(self, make, model):
        self.make = make
        self.model = model

mustang = Car('Ford', 'Mustang')
print mustang.wheels
# 4
print Car.wheels
# 4
```

Un `Car` siempre tiene cuatro ruedas, independientemente de la marca o modelo. Los métodos de instancia pueden acceder a estos atributos de la misma manera que acceden a los atributos regulares: a través de `self` (es decir, `self.wheels`).

Sin embargo, existe una clase de métodos, llamados métodos estáticos, que no tienen acceso a `self`. Al igual que los atributos de clase, son métodos que funcionan sin requerir que una instancia esté presente. Dado que las instancias siempre se referencian a través de `self`, los métodos estáticos no tienen un parámetro propio.

Lo siguiente sería un método estático válido en la clase `Car`:

```python
class Car(object):
    ...
    def make_car_sound():
        print 'VRooooommmm!'
```

No importa qué tipo de automóvil tengamos, siempre hace el mismo sonido. Para dejar en claro que este método no debe recibir la instancia como primer parámetro (es decir, `self` en los métodos "normales"), se utiliza el decorador `@staticmethod`, convirtiendo nuestra definición en:

```python
class Car(object):
    ...
    @staticmethod
    def make_car_sound():
        print 'VRooooommmm!'
```

**Métodos de clase**

Una variante del método estático es el método de clase. En lugar de recibir la instancia como primer parámetro, se pasa la clase. También se define utilizando un decorador:

```python
class Vehicle(object):
    ...
    @classmethod
    def is_motorcycle(cls):
        return cls.wheels == 2
```

Es posible que los métodos de clase no tengan mucho sentido ahora, pero eso se debe a que se usan con más frecuencia en relación con nuestro siguiente tema: la herencia.

**Herencia**

Si bien la programación orientada a objetos es útil como herramienta de modelado, realmente gana poder cuando se introduce el concepto de herencia. Herencia es el proceso por el cual una clase "secundaria" deriva los datos y el comportamiento de una clase "primaria". Un ejemplo definitivamente nos ayudará aquí.

Imagina que tenemos un concesionario de coches. Vendemos todo tipo de vehículos, desde motocicletas hasta camiones. Nos diferenciamos de la competencia por nuestros precios. Específicamente, cómo determinamos el precio de un vehículo en nuestro lote: 5,000 x número de ruedas que tiene un vehículo. Nos encanta comprar nuestros vehículos también. Ofrecemos una tarifa plana: 10 porciento de las millas recorridas en el vehículo. Para camiones, esa tasa es de 10,000. Para autos, 8,000. Para motocicletas, 4,000.

Si quisiéramos crear un sistema de ventas para nuestro concesionario utilizando técnicas orientadas a objetos, ¿cómo lo haríamos? ¿Cuáles serían los objetos? Es posible que tengamos una clase `Sale`, una clase `Customer`, una clase `Inventory`, etc., pero es casi seguro que tendremos una clase `Car`, `Truck` y `Motorcycle`.

¿Cómo serían estas clases? Usando lo que hemos aprendido, aquí hay una posible implementación de la clase `Car`:

```python
class Car(object):
    """A car for sale by Jeffco Car Dealership.

    Attributes:
        wheels: An integer representing the number of wheels the car has.
        miles: The integral number of miles driven on the car.
        make: The make of the car as a string.
        model: The model of the car as a string.
        year: The integral year the car was built.
        sold_on: The date the vehicle was sold.
    """

    def __init__(self, wheels, miles, make, model, year, sold_on):
        """Return a new Car object."""
        self.wheels = wheels
        self.miles = miles
        self.make = make
        self.model = model
        self.year = year
        self.sold_on = sold_on

    def sale_price(self):
        """Return the sale price for this car as a float amount."""
        if self.sold_on is not None:
            return 0.0  # Already sold
        return 5000.0 * self.wheels

    def purchase_price(self):
        """Return the price for which we would pay to purchase the car."""
        if self.sold_on is None:
            return 0.0  # Not yet sold
        return 8000 - (.10 * self.miles)

    ...
```

Entendido, eso parece bastante razonable. Por supuesto, es probable que tengamos un número de otros métodos en la clase, pero he mostrado dos de particular interés para nosotros: `sale_price` y `purchase_price`. Veremos por qué estos son importantes en un momento.

Ahora que tenemos la clase `Car`, ¿quizás deberíamos crear una clase `Truck`? Sigamos el mismo patrón que hicimos para `Car`:

```python
class Truck(object):
    """A truck for sale by Jeffco Car Dealership.

    Attributes:
        wheels: An integer representing the number of wheels the truck has.
        miles: The integral number of miles driven on the truck.
        make: The make of the truck as a string.
        model: The model of the truck as a string.
        year: The integral year the truck was built.
        sold_on: The date the vehicle was sold.
    """

    def __init__(self, wheels, miles, make, model, year, sold_on):
        """Return a new Truck object."""
        self.wheels = wheels
        self.miles = miles
        self.make = make
        self.model = model
        self.year = year
        self.sold_on = sold_on

    def sale_price(self):
        """Return the sale price for this truck as a float amount."""
        if self.sold_on is not None:
            return 0.0  # Already sold
        return 5000.0 * self.wheels

    def purchase_price(self):
        """Return the price for which we would pay to purchase the truck."""
        if self.sold_on is None:
            return 0.0  # Not yet sold
        return 10000 - (.10 * self.miles)

    ...
```
Excelente. Eso es casi idéntico a la clase `Car`. Una de las reglas más importantes de la programación (en general, no solo cuando se trata de objetos) es "DRY" o "Don't Repeat Yourself". Definitivamente nos hemos repetido aquí. De hecho, las clases `Car` y `Truck` difieren solo en Un solo caracter (aparte de los comentarios).

Entonces, ¿Donde nos equivocamos? Nuestro principal problema es: `Car` y `Truck` son cosas reales, objetos tangibles que tienen sentido intuitivo como clases. Sin embargo, comparten tantos datos y funcionalidad en común que parece que debe haber una abstracción que podamos presentar aquí. De hecho existe: la noción de Vehículos.

**Clases abstractas**

Un vehículo no es un objeto del mundo real. Más bien, es un concepto que encarnan algunos objetos del mundo real (como automóviles, camiones y motocicletas). Nos gustaría aprovechar el hecho de que cada uno de estos objetos puede considerarse un vehículo para eliminar códigos repetidos. Podemos hacer eso creando una clase de Vehículo:

```python
class Vehicle(object):
    """A vehicle for sale by Jeffco Car Dealership.

    Attributes:
        wheels: An integer representing the number of wheels the vehicle has.
        miles: The integral number of miles driven on the vehicle.
        make: The make of the vehicle as a string.
        model: The model of the vehicle as a string.
        year: The integral year the vehicle was built.
        sold_on: The date the vehicle was sold.
    """

    base_sale_price = 0

    def __init__(self, wheels, miles, make, model, year, sold_on):
        """Return a new Vehicle object."""
        self.wheels = wheels
        self.miles = miles
        self.make = make
        self.model = model
        self.year = year
        self.sold_on = sold_on


    def sale_price(self):
        """Return the sale price for this vehicle as a float amount."""
        if self.sold_on is not None:
            return 0.0  # Already sold
        return 5000.0 * self.wheels

    def purchase_price(self):
        """Return the price for which we would pay to purchase the vehicle."""
        if self.sold_on is None:
            return 0.0  # Not yet sold
        return self.base_sale_price - (.10 * self.miles)
		
    ...
```

Ahora podemos hacer que la clase `Car` y `Truck `se herede de la clase `Vehicle` reemplazando el objeto en la clase `Car(object)`. La clase entre paréntesis es la clase de la cual se hereda (objeto esencialmente significa "sin herencia". Discutiremos exactamente por qué escribimos eso en un momento).

Ahora podemos definir `Car` y `Truck` de una manera muy sencilla:

```python
class Car(Vehicle):

    def __init__(self, wheels, miles, make, model, year, sold_on):
        """Return a new Car object."""
        self.wheels = wheels
        self.miles = miles
        self.make = make
        self.model = model
        self.year = year
        self.sold_on = sold_on
        self.base_sale_price = 8000


class Truck(Vehicle):

    def __init__(self, wheels, miles, make, model, year, sold_on):
        """Return a new Truck object."""
        self.wheels = wheels
        self.miles = miles
        self.make = make
        self.model = model
        self.year = year
        self.sold_on = sold_on
        self.base_sale_price = 10000
```

Esto funciona, pero tiene algunos problemas. Primero, todavía estamos repitiendo un montón de código. En última instancia, nos gustaría deshacernos de toda repetición. Segundo, y más problemático, hemos introducido la clase `Vehicle`, pero ¿deberíamos realmente permitir que las personas creen objetos `Vehicle` (en lugar de `Car` o `Truck`)? Un `Vehicle` es solo un concepto, no una cosa real, entonces, ¿qué significa decir lo siguiente:

```python
v = Vehicle(4, 0, 'Honda', 'Accord', 2014, None)
print v.purchase_price()
```

Un `Vehicle` no tiene una `base_sale_price`, solo lo hacen las clases individuales hijos como `Car` y `Truck`. El problema es que `Vehicle` debería ser realmente una clase base abstracta. Las clases base abstractas son clases que solo deben ser heredadas de; No puedes crear una instancia de un ABC. Eso significa que, si `Vehicle` es un ABC, lo siguiente es ilegal:

```python
v = Vehicle(4, 0, 'Honda', 'Accord', 2014, None)
```

Tiene sentido rechazar esto, ya que nunca pretendemos que  `Vehicle` se utilice directamente. Solo queríamos usarlo para abstraer algunos datos y comportamientos comunes. Entonces, ¿cómo hacemos una clase de ABC? ¡Sencillo! El módulo abc contiene una metaclase llamada ABCMeta (las metaclases están un poco fuera del alcance de este artículo). Establecer la metaclase de una clase en ABCMeta y hacer que uno de sus métodos sea virtual lo convierte en un ABC. Un método virtual es uno que el ABC dice que debe existir en clases secundarias, pero que no necesariamente se implementa realmente. Por ejemplo, la clase `Vehicle` se puede definir de la siguiente manera:

```python
from abc import ABCMeta, abstractmethod

class Vehicle(object):
    """A vehicle for sale by Jeffco Car Dealership.


    Attributes:
        wheels: An integer representing the number of wheels the vehicle has.
        miles: The integral number of miles driven on the vehicle.
        make: The make of the vehicle as a string.
        model: The model of the vehicle as a string.
        year: The integral year the vehicle was built.
        sold_on: The date the vehicle was sold.
    """

    __metaclass__ = ABCMeta

    base_sale_price = 0

    def sale_price(self):
        """Return the sale price for this vehicle as a float amount."""
        if self.sold_on is not None:
            return 0.0  # Already sold
        return 5000.0 * self.wheels

    def purchase_price(self):
        """Return the price for which we would pay to purchase the vehicle."""
        if self.sold_on is None:
            return 0.0  # Not yet sold
        return self.base_sale_price - (.10 * self.miles)

    @abstractmethod
    def vehicle_type():
        """"Return a string representing the type of vehicle this is."""
        pass
```

Ahora, ya que `vehicle_type` es un método abstracto, no podemos crear directamente una instancia de `Vehicle`. Siempre y cuando `Car` y `Truck` se hereden de `Vehicle` y definan `vehicle_type`, podemos instanciar esas clases muy bien.

Volviendo a la repetición en nuestras clases `Car` y `Truck`, veamos si podemos eliminar eso al elevar la funcionalidad común a la clase base, `Vehicle`:


```python
from abc import ABCMeta, abstractmethod
class Vehicle(object):
    """A vehicle for sale by Jeffco Car Dealership.


    Attributes:
        wheels: An integer representing the number of wheels the vehicle has.
        miles: The integral number of miles driven on the vehicle.
        make: The make of the vehicle as a string.
        model: The model of the vehicle as a string.
        year: The integral year the vehicle was built.
        sold_on: The date the vehicle was sold.
    """

    __metaclass__ = ABCMeta

    base_sale_price = 0
    wheels = 0

    def __init__(self, miles, make, model, year, sold_on):
        self.miles = miles
        self.make = make
        self.model = model
        self.year = year
        self.sold_on = sold_on

    def sale_price(self):
        """Return the sale price for this vehicle as a float amount."""
        if self.sold_on is not None:
            return 0.0  # Already sold
        return 5000.0 * self.wheels

    def purchase_price(self):
        """Return the price for which we would pay to purchase the vehicle."""
        if self.sold_on is None:
            return 0.0  # Not yet sold
        return self.base_sale_price - (.10 * self.miles)

    @abstractmethod
    def vehicle_type(self):
        """"Return a string representing the type of vehicle this is."""
        pass
```

Ahora las clases `Car` y `Truck` se convierten en:

```python
class Car(Vehicle):
    """A car for sale by Jeffco Car Dealership."""

    base_sale_price = 8000
    wheels = 4

    def vehicle_type(self):
        """"Return a string representing the type of vehicle this is."""
        return 'car'

class Truck(Vehicle):
    """A truck for sale by Jeffco Car Dealership."""

    base_sale_price = 10000
    wheels = 4

    def vehicle_type(self):
        """"Return a string representing the type of vehicle this is."""
        return 'truck'
```

Esto encaja perfectamente con nuestra intuición: en lo que respecta a nuestro sistema, la única diferencia entre `Car` y `Truck` es el precio base de venta. Definir una clase `Motorcyle`, entonces, es igualmente simple:

```python
class Motorcycle(Vehicle):
    """A motorcycle for sale by Jeffco Car Dealership."""

    base_sale_price = 4000
    wheels = 2

    def vehicle_type(self):
        """"Return a string representing the type of vehicle this is."""
        return 'motorcycle'
```

**Herencia y el LSP**

Aunque parezca que usamos herencia para eliminar la duplicación, lo que realmente estábamos haciendo era simplemente proporcionar el nivel adecuado de abstracción. Y la abstracción es la clave para entender la herencia. Hemos visto cómo un efecto secundario del uso de la herencia es que reducimos el código duplicado, pero ¿qué ocurre desde la perspectiva de quien llama? ¿Cómo el uso de la herencia cambia ese código?

Un poco. Imagina que tenemos dos clases, `Dog` y `Person`, y queremos escribir una función que tome cualquier tipo de objeto e imprima si la instancia en cuestión puede hablar o no (un perro no puede, una persona puede). Podríamos escribir código como el siguiente:


```python
def can_speak(animal):
    if isinstance(animal, Person):
        return True
    elif isinstance(animal, Dog):
        return False
    else:
        raise RuntimeError('Unknown animal!')
```

Eso funciona cuando solo tenemos dos tipos de animales, pero ¿y si tenemos veinte o doscientos? Eso si ... la cadena elif va a ser bastante larga.

La idea clave aquí es que a `can_speak` no debería importarle con qué tipo de animal está tratando, la clase animal en sí misma debería decirnos si puede hablar. Al introducir una clase base común, `Animal`, que define `can_speak`, aliviamos la función de su carga de comprobación de tipos. Ahora, siempre que sepa que fue un animal que se paso, determinar si puede hablar es trivial:


```python
def can_speak(animal):
    return animal.can_speak()
```

Esto funciona porque `Person` y `Dog` (y cualquier otra clase que creamos para derivar de `Animal`) siguen el Principio de Sustitución de Liskov LSP. Esto indica que deberíamos poder usar una clase hija (como `Person` o `Dog`) donde se espera que una clase padre (`Animal`) funcione bien. Esto suena simple, pero es la base de un concepto poderoso que discutiremos en un artículo futuro: interfaces.

#### Resumen

Con suerte, has aprendido mucho sobre qué son las clases de Python, por qué son útiles y cómo usarlas. El tema de las clases y la programación orientada a objetos son increíblemente profundos. De hecho, llegan al núcleo de la informática. Este artículo no pretende ser un estudio exhaustivo de clases, ni debe ser su única referencia. Hay literalmente miles de explicaciones de OOP y clases disponibles en línea, por lo que si no encuentra esta adecuada, ciertamente un poco de búsqueda revelará una más adecuada para usted.

Las correcciones y argumentos son bienvenidos en los comentarios.
