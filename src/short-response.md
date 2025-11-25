# Section 2 — Short Response

Write your responses directly in this file. Follow markdown formatting guidelines. Check the rubric.md file to see how your short responses will be graded.

As a quick guide, check the following before submitting:

- [] Answered all parts of every question
- [] No typos or grammar mistakes (use grammarly!)
- [] Accurately uses relevant technical terminology
- [] Uses markdown to enhance readability (preview in VS Code with Command/Control + Shift + V)
- [] Responses are concise and easy to comprehend

---

## Question 1

In your own words, explain what does _encapsulation_ refer to? Why is this concept beneficial when programming?

Provide a code snippet to illustrate _encapsulation_.

## Response 1

--- Encapsulation is when you keep the data inside an object private and only allow access to it through specific methods. It ensures the object’s data is managed properly and accessed only through the intended methods. Encapsulation is beneficial because it keeps your data safe, reduces bugs, and makes your code easier to maintain. By controlling how data is accessed and updated, you avoid accidental changes and create a cleaner, more reliable structure in your program. An Example of 'encapsulation' is shown below:

```js
class BankAccount {
  #balance = 0; // private variable

  deposit(amount) {
    this.#balance += amount;
  }

  getBalance() {
    return this.#balance;
  }
}

const account = new BankAccount();
account.deposit(50);
console.log(account.getBalance()); // 50

// account.#balance = 100, can't change it directly
```

Here, balance is private and can only be accessed or changed
through the class methods, which shows encapsulation.

## Question 2

Explain what the `this` keyword is. Why is the `this` keyword useful?

In the code snippet below, what does `this` refer to?

```js
class Counter {
  constructor() {
    this.count = 0;
  }
  increment() {
    this.count++;
  }
}

const counterA = new Counter();
const counterB = new Counter();

counterA.increment();
counterA.increment();
counterA.increment();

counterB.increment();

console.log(counterA.count);
console.log(counterB.count);
```

## Response 2

--- The this keyword refers to the current object that is using the method or property. It’s useful because it lets you access or modify properties of the object from inside its class or function, without hardcoding the object name.

Inside the Counter class, this.count refers to the count property of the specific object that calls the method. When counterA.increment() runs, this refers to counterA. When counterB.increment() runs, this refers to counterB.

## Question 3

In your own words, explain what **polymorphism** means in OOP. Provide an example in code that demonstrates polymorphism.

## Response 3

--- Polymorphism in OOP means different objects can respond to the same method in their own way. It allows us to write code that works with different types of objects, without worrying about the exact class, each object can have its own behavior for the same method. An example that demonstrates 'Polymorphism' is shown below:

```js
class BankAccount {
  deposit(amount) {
    console.log(`Deposited $${amount}`);
  }
}

class SavingsAccount extends BankAccount {
  deposit(amount) {
    console.log(`Deposited $${amount} with 5% interest`);
  }
}

class CheckingAccount extends BankAccount {
  deposit(amount) {
    console.log(`Deposited $${amount} with no interest`);
  }
}

const savings = new SavingsAccount();
const checking = new CheckingAccount();

savings.deposit(100); // Deposited $100 with 5% interest
checking.deposit(100); // Deposited $100 with no interest
```

This demonstrates polymorphism because all the account classes use the same method name, deposit(), but each class defines its own behavior. Calling deposit() on a SavingsAccount adds interest, while calling it on a CheckingAccount behaves differently.

## Question 4

You're building a game where players can raise different digital pets: Cats, Dogs, and Birds. All pets have have a `name`, `energy` level, and `happiness` level and can all `sleep`. Cats have the ability to `hunt`, dogs have the ability to `chase`, and birds have the ability to `fly`.

**Part A:** Describe in words how you would use inheritance to organize these classes.

**Part B:** Explain one advantage of using inheritance here instead of creating three completely separate classes.

## Response 4

**Part A:** I would create a parent class called Pet that contains the shared properties name, energy, and happiness, along with the common method sleep(). Then, I would create subclasses Cat, Dog, and Bird that extend Pet, each with its own unique method for its special ability (hunt for Cat, chase for Dog, and fly for Bird). This structure allows all pets to inherit the common behavior from Pet, while still supporting their individual behavior.

**Part B:** One advantage of using inheritance is that it reduces code duplication. Instead of rewriting the shared properties and sleep method in each class, they are defined once in the Pet superclass. This makes the code easier to maintain, more organized, and flexible if we later add more types of pets.