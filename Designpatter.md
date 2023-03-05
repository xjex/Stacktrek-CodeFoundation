# Design Patterns in JavaScript

## Introduction

Design patterns are reusable solutions to commonly occurring problems in software development. JavaScript, being a popular language, has numerous design patterns to choose from. In this article, we will explore some of the most commonly used design patterns in JavaScript with examples.

## Creational Patterns

### Singleton Pattern

The Singleton pattern is a creational pattern that ensures a class has only one instance, while providing a global point of access to that instance. Here is an example implementation of Singleton pattern:

```javascript
const Singleton = (() => {
    let instance = null;
  
    function createInstance() {
        // constructor code here
        return {
            // object properties here
        };
    }
  
    return {
        getInstance: () => {
            if (!instance) {
                instance = createInstance();
            }
            return instance;
        }
    };
})();

```

### Factory Pattern

The Factory pattern is a creational pattern that provides a way to create objects without exposing the creation logic to the client. Here is an example implementation of Factory pattern:

```javascript
class CarFactory {
    constructor() {
        this.createCar = (make, model) => {
            let car = null;
            switch (make) {
                case 'Honda':
                    car = new Honda(model);
                    break;
                case 'Toyota':
                    car = new Toyota(model);
                    break;
            }
            return car;
        }
    }
}

class Honda {
    constructor(model) {
        this.model = model;
    }
}

class Toyota {
    constructor(model) {
        this.model = model;
    }
}

```

### Builder Pattern

The Builder pattern is a creational pattern that separates the construction of a complex object from its representation. Here is an example implementation of Builder pattern:

```javascript
class HouseBuilder {
    constructor() {
        this.house = null;
    }
  
    buildHouse() {
        this.house = new House();
        this.buildWalls();
        this.buildRoof();
        this.buildDoors();
        this.buildWindows();
        return this.house;
    }
  
    buildWalls() {
        // construct walls here
    }
  
    buildRoof() {
        // construct roof here
    }
  
    buildDoors() {
        // construct doors here
    }
  
    buildWindows() {
        // construct windows here
    }
}

```

## Structural Patterns

### Decorator Pattern

The Decorator pattern is a structural pattern that adds behavior to an object dynamically without affecting the behavior of other objects from the same class. Here is an example implementation of Decorator pattern:

```javascript
class Coffee {
    getCost() {
        return 1.0;
    }
  
    getDescription() {
        return 'Coffee';
    }
}
  
class Milk extends Coffee {
    constructor(coffee) {
        super();
        this.coffee = coffee;
    }
  
    getCost() {
        return this.coffee.getCost() + 0.5;
    }
  
    getDescription() {
        return `${this.coffee.getDescription()} + Milk`;
    }
}
  
class Sugar extends Coffee {
    constructor(coffee) {
        super();
        this.coffee = coffee;
    }
  
    getCost() {
        return this.coffee.getCost() + 0.2;
    }
  
    getDescription() {
        return `${this.coffee.getDescription()} + Sugar`;
    }
}

```

### Facade Pattern

The Facade pattern is a structural pattern that provides a simplified interface to a complex subsystem. Here is an example implementation of Facade pattern:

```javascript
class Car {
	  start() {
        // start car engine
	  }
	  stop() {
	    // stop car engine
	  }

}

class MusicPlayer { 
		play() {
		 // play music 
		}   
		pause() {
		 // pause music
		}
}

class CarFacade { 
	constructor() { 
		this.car = new Car();
		this.musicPlayer = new MusicPlayer();
	}
	startCar() {
	    this.car.start();
	    this.musicPlayer.play();
	}

	stopCar() {
	    this.car.stop();
	    this.musicPlayer.pause();
	}
}


```

## Behavioral Patterns

### Observer Pattern

The Observer pattern is a behavioral pattern that defines a one-to-many dependency between objects so that when one object changes state, all its dependents are notified and updated automatically. Here is an example implementation of Observer pattern:

```javascript
class Subject {
    constructor() {
        this.observers = [];
    }
  
    addObserver(observer) {
        this.observers.push(observer);
    }
  
    removeObserver(observer) {
        const index = this.observers.indexOf(observer);
        if (index > -1) {
            this.observers.splice(index, 1);
        }
    }
  
    notifyObservers() {
        for (const observer of this.observers) {
            observer.update();
        }
    }
}
  
class Observer {
    constructor(subject) {
        this.subject = subject;
        this.subject.addObserver(this);
    }
  
    update() {
        // do something when subject state changes
    }
  
    unsubscribe() {
        this.subject.removeObserver(this);
    }
}

### Command Pattern

The Command pattern is a behavioral pattern that turns a request into a standalone object that contains all information about the request. This object can then be passed to other objects that can execute the request. Here is an example implementation of Command pattern:

```javascript
class Command {
    execute() {}
}
  
class Light {
    turnOn() {
        // turn on light
    }
  
    turnOff() {
        // turn off light
    }
}
  
class LightOnCommand extends Command {
    constructor(light) {
        super();
        this.light = light;
    }
  
    execute() {
        this.light.turnOn();
    }
}
  
class LightOffCommand extends Command {
    constructor(light) {
        super();
        this.light = light;
    }
  
    execute() {
        this.light.turnOff();
    }
}
  
class RemoteControl {
    constructor() {
        this.commands = [];
    }
  
    addCommand(command) {
        this.commands.push(command);
    }
  
    executeCommands() {
        for (const command of this.commands) {
            command.execute();
        }
    }
}

```

## Conclusion

Design patterns are an essential part of software development, and using them can greatly improve the quality and maintainability of your code. In this article, we explored some of the most commonly used design patterns in JavaScript with examples. However, it's important to note that there are many other design patterns available, and choosing the right pattern for your specific use case is crucial.

