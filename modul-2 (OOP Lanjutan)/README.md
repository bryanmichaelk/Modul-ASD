## Daftar Isi
- [Inner Class](#inner-class)
  - [Non-Static Inner Class](#non-static-inner-class)
  - [Static Nested Class](#static-nested-class)
  - [Local Class](#local-class)
  - [Private Inner Class](#private-inner-class)
- [Abstract Class](#abstract-class)
  - [Deklarasi Abstract Class](#deklarasi-abstract-class)
  - [Contoh Implementasi Abstract Class](#contoh-implementasi-abstract-class)
- [Interface](#interface)
  - [Deklarasi Interface](#deklarasi-interface)
  - [Contoh Implementasi Interface](#contoh-implementasi-interface)
  - [Perbedaan Abstract Class dan Interface](#perbedaan-abstract-class-dan-interface)
- [Class, Method, Attributes, dan Constructor](#class-method-attributes-dan-constructor)
  - [Extending a Class and Implementing an Interface](#extending-a-class-and-implementing-an-interface)
- [Practice](#practice)

---


## Inner Class

### Non-Static Inner Class
**Non-Static Inner Class** adalah class yang berada di dalam class lain dan hanya dapat diakses melalui instance dari class luarnya.

```java
class OuterClass {
	int x = 10;

	class InnerClass {
		int y = 5;
	}
}

public class Main {
	public static void main(String[] args) {
		OuterClass outer = new OuterClass();
		OuterClass.InnerClass inner = outer.new InnerClass();
		System.out.println(inner.y + outer.x); // Output: 15
	}
}
```

### Static Nested Class
**Static Nested Class** adalah class yang berada di dalam class lain tetapi bersifat static. Ini memungkinkan akses ke class tersebut tanpa perlu membuat instance dari class luar.

```java
class OuterClass {
	int x = 10;

	static class NestedClass {
		int y = 5;
	}
}

public class Main {
	public static void main(String[] args) {
		OuterClass.NestedClass nested = new OuterClass.NestedClass();
		System.out.println(nested.y);  // Output: 5
	}
}
```

### Local Class
**Local Class** adalah class yang didefinisikan di dalam metode dan hanya bisa digunakan dalam metode tersebut.

```java
class OuterClass {
	void myMethod() {
		class LocalClass {
			void printMessage() {
				System.out.println("Local Class inside method");
			}
		}
		LocalClass local = new LocalClass();
		local.printMessage();
	}
}

public class Main {
	public static void main(String[] args) {
		OuterClass outer = new OuterClass();
		outer.myMethod();  // Output: Local Class inside method
	}
}
```

Berikut adalah pengganti materi tentang **Anonymous Inner Class** dengan **Private Inner Class**:

### Private Inner Class
**Private Inner Class** adalah inner class yang memiliki aksesibilitas terbatas hanya dalam class luarnya. Ini memungkinkan class luar menyembunyikan detail implementasi dari class lainnya.

```java
class OuterClass {
	private class InnerClass {
		public void displayMessage() {
			System.out.println("This is a message from the private inner class.");
		}
	}

	public void createInnerInstance() {
		InnerClass inner = new InnerClass();
		inner.displayMessage();
	}
}

public class Main {
	public static void main(String[] args) {
		OuterClass outer = new OuterClass();
		outer.createInnerInstance();  // Output: This is a message from the private inner class.
	}
}
```

---

## Abstract Class

### Deklarasi Abstract Class
**Abstract Class** adalah class yang tidak dapat diinstansiasi dan biasanya digunakan sebagai superclass. Abstract class dapat memiliki metode abstract (tanpa implementasi) dan metode non-abstract (dengan implementasi).

```java
abstract class Animal {
	public abstract void sound();  // Metode abstract

	public void sleep() {  // Metode konkret
		System.out.println("Animal is sleeping");
	}
}
```

### Contoh Implementasi Abstract Class
Class yang mewarisi **abstract class** harus mengimplementasikan semua metode abstract.

```java
class Dog extends Animal {
	public void sound() {
		System.out.println("Woof");
	}
}

public class Main {
	public static void main(String[] args) {
		Dog dog = new Dog();
		dog.sound();  // Output: Woof
		dog.sleep();  // Output: Animal is sleeping
	}
}
```

---

## Interface

### Deklarasi Interface
**Interface** adalah blueprint dari sebuah class yang hanya dapat memiliki metode abstract (sampai Java 8). Di Java 8 dan setelahnya, interface juga dapat memiliki default methods dengan implementasi.

```java
interface Animal {
	public void sound();  // Metode abstract
	public void sleep();  // Metode abstract
}
```

### Contoh Implementasi Interface
Class yang mengimplementasikan interface harus mengoverride semua metode abstract dari interface tersebut.

```java
class Cat implements Animal {
	public void sound() {
		System.out.println("Meow");
	}

	public void sleep() {
		System.out.println("Cat is sleeping");
	}
}

public class Main {
	public static void main(String[] args) {
		Cat cat = new Cat();
		cat.sound();  // Output: Meow
		cat.sleep();  // Output: Cat is sleeping
	}
}
```

### Perbedaan Abstract Class dan Interface

| **Abstract Class** | **Interface** |
|---------------------|---------------|
| Dapat memiliki metode abstract dan non-abstract. | Hanya memiliki metode abstract (sebelum Java 8). |
| Dapat memiliki constructor. | Tidak dapat memiliki constructor. |
| Menggunakan keyword `extends` untuk diwariskan. | Menggunakan keyword `implements` untuk diimplementasikan. |
| Class hanya bisa mewarisi satu abstract class. | Class bisa mengimplementasikan lebih dari satu interface. |

--- 

## Class, Method, Attributes, dan Constructor

### Extending a Class and Implementing an Interface
Dalam Java, sebuah class dapat **mewarisi** (extend) class lain sekaligus **mengimplementasikan** (implement) satu atau lebih interface. Dengan cara ini, class dapat menggunakan fitur dari superclass yang diperluas, serta menyediakan implementasi dari metode yang ditentukan dalam interface.

- **Extending**: Class mewarisi properti dan metode dari superclass.
- **Implementing**: Class harus mengimplementasikan semua metode yang ditentukan dalam interface.

#### Contoh Extending dan Implementing:

```java
// Superclass
class Animal {
    public void eat() {
        System.out.println("Animal is eating");
    }
}

// Interface1
interface Pet {
    void play();
}

// Interface2
interface Wild {
    void hunt();
}

// Subclass that extends Animal and implements both Pet and Wild
class Dog extends Animal implements Pet, Wild {
    @Override
    public void play() {
        System.out.println("Dog is playing");
    }

    @Override
    public void hunt() {
        System.out.println("Dog is hunting");
    }
    
    public void bark() {
        System.out.println("Woof Woof");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        
        dog.eat();   // Inherited from Animal
        dog.play();  // Implemented from Pet
        dog.hunt();  // Implemented from Wild
        dog.bark();  // Dog's own method
    }
}
```
- **Extending Class**: Class `Dog` mewarisi metode `eat()` dari class `Animal`.
- **Implementing Interfaces**: Class `Dog` mengimplementasikan metode `play()` dari interface `Pet` dan metode `hunt()` dari interface `Wild`.
- **Multiple Inheritance of Behavior**: Java mendukung implementasi dari banyak interface, tetapi hanya bisa extend satu class.
---

## Practice
https://tutorialjava.tripod.com/Java%20Project/Lab%20Exercise%207.htm