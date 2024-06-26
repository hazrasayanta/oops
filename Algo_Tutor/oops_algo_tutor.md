# Day 1: Start with an introduction to Object-Oriented Programming (OOP) concepts.

**=>** Sure! Here’s a brief introduction to Object-Oriented Programming (OOP) concepts in JavaScript:

### 1. **Classes and Objects**

- **Class**: A blueprint for creating objects. It defines properties and methods.
- **Object**: An instance of a class.

### Example:

```javascript
class Animal {
  constructor(name, species) {
    this.name = name;
    this.species = species;
  }

  makeSound() {
    return "Some generic sound";
  }
}

const dog = new Animal("Buddy", "Dog");

console.log(dog.name); // Output: Buddy
console.log(dog.species); // Output: Dog
console.log(dog.makeSound()); // Output: Some generic sound
```

### 2. **Encapsulation**

- Encapsulation bundles the data and methods that operate on the data within one unit (class) and restricts direct access to some of the object’s components.

### Example:

```javascript
class Animal {
  constructor(name, species) {
    this._name = name;  // Conventionally using _ to indicate private properties
    this._species = species;
  }

  getName() {
    return this._name;
  }

  getSpecies() {
    return this._species;
  }

  makeSound() {
    return "Some generic sound";
  }
}

const dog = new Animal("Buddy", "Dog");

console.log(dog.getName()); // Output: Buddy
console.log(dog.getSpecies()); // Output: Dog
console.log(dog.makeSound()); // Output: Some generic sound
```

### 3. **Abstraction**

- Abstraction hides the complex implementation details and shows only the essential features of the object.

### Example:

```javascript
class Animal {
  constructor(name, species) {
    this._name = name;
    this._species = species;
  }

  makeSound() {
    return "Some generic sound";
  }

  getDetails() {
    return `${this._name} is a ${this._species}`;
  }
}

const dog = new Animal("Buddy", "Dog");

console.log(dog.getDetails()); // Output: Buddy is a Dog
console.log(dog.makeSound()); // Output: Some generic sound
```

### 4. **Inheritance**

- Inheritance allows a class to inherit properties and methods from another class.

### Example:

```javascript
class Animal {
  constructor(name, species) {
    this.name = name;
    this.species = species;
  }

  makeSound() {
    return "Some generic sound";
  }
}

class Dog extends Animal {
  constructor(name, breed) {
    super(name, "Dog");
    this.breed = breed;
  }

  makeSound() {
    return "Woof!";
  }
}

const beagle = new Dog("Max", "Beagle");

console.log(beagle.name); // Output: Max
console.log(beagle.species); // Output: Dog
console.log(beagle.breed); // Output: Beagle
console.log(beagle.makeSound()); // Output: Woof!
```

### 5. **Polymorphism**

- Polymorphism allows objects to be treated as instances of their parent class rather than their actual class.

### Example:

```javascript
class Animal {
  constructor(name, species) {
    this.name = name;
    this.species = species;
  }

  makeSound() {
    return "Some generic sound";
  }
}

class Dog extends Animal {
  constructor(name, breed) {
    super(name, "Dog");
    this.breed = breed;
  }

  makeSound() {
    return "Woof!";
  }
}

class Cat extends Animal {
  constructor(name, breed) {
    super(name, "Cat");
    this.breed = breed;
  }

  makeSound() {
    return "Meow!";
  }
}

const animals = [
  new Dog("Max", "Beagle"),
  new Cat("Whiskers", "Siamese")
];

animals.forEach(animal => {
  console.log(`${animal.name} says ${animal.makeSound()}`);
});

// Output:
// Max says Woof!
// Whiskers says Meow!
```

In this example:

- `Animal` is a base class.
- `Dog` and `Cat` are derived classes that override the `makeSound` method.
- `animals` is an array of `Dog` and `Cat` objects, demonstrating polymorphism by calling the overridden `makeSound` method on each object.

These examples illustrate the fundamental OOP concepts in JavaScript, providing a solid foundation for developing modular and maintainable code.
