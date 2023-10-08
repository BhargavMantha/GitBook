---
description: >-
  The singleton pattern ensures that a class has only one instance and provides
  a global point to access this instance. The pattern makes sure that there's
  only one object of a class that exists.
---

# Singleton Pattern

Alright! Let's tackle the singleton pattern.

#### 1. Explaining to a 5-year-old:

Imagine you have a toy box. Whenever you want a toy, you always go to this one special toy box and take a toy from there. If your friends come over and they want to play with the toy, they too go to that same toy box. There is only one toy box in the whole house for everyone to use. The toy box is unique; no other toy box in the house is like it.

This special toy box is like the Singleton. Just like there's only one toy box for everyone, in programming, sometimes we want only one instance or one copy of something. This is what the singleton pattern helps with.

#### 2. Explaining to a developer:

The singleton pattern ensures that a class has only one instance and provides a global point to access this instance. The pattern makes sure that there's only a single object of a class that exists, and it provides a way to access this object.

**Pseudocode**:

```
class Singleton {
    private static instance: Singleton;

    private constructor() {
        // Private constructor ensures that new instances can't be created from outside.
    }

    public static getInstance(): Singleton {
        if (!this.instance) {
            this.instance = new Singleton();
        }
        return this.instance;
    }
}
```

**Typescript**:

```typescript
class Singleton {
    private static instance: Singleton;

    private constructor() {
        // The constructor is private to prevent creating new instances of Singleton
    }

    public static getInstance(): Singleton {
        if (!this.instance) {
            this.instance = new Singleton();
        }
        return this.instance;
    }
}

// Usage:
const singleton1 = Singleton.getInstance();
const singleton2 = Singleton.getInstance();

console.log(singleton1 === singleton2);  // This will print 'true'
```

In the above TypeScript example, when you try to get an instance of `Singleton`, it checks if it already has one created. If it does, it returns that. If it doesn't, it creates one and then returns it. This ensures that every time you call `getInstance()`, you're always getting the same single instance of `Singleton`.

This can be especially useful when, for example, managing database connections, logging, or any situation where it's important to control access and ensure there's a single point of access.
