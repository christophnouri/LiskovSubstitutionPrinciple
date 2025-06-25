# Liskov Substitution Principle

**LSP (Liskov Substitution Principle)** is the third principle of SOLID.  
It says:

> *If class B is a subclass of class A, then we should be able to use A’s objects and B’s objects in the same way without breaking the program.*

In other words, **child classes should behave like their parent classes**. They must **not change the expected behavior**.

---

## <a href="https://www.linkedin.com/in/soheilsadeghii/"><img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Telegram-Animated-Emojis/main/Smileys/Exploding%20Head.webp" alt="Exploding Head" width="35" height="35" /></a> Why is LSP Important?

- Helps keep the **polymorphism** working as expected
- Makes **inheritance safe** and meaningful
- Improves **code reusability** and **readability**
- Prevents **runtime bugs** and unexpected behaviors

When subclasses break the behavior of the parent class, it leads to confusing and buggy code.

---

## <a href="https://www.linkedin.com/in/soheilsadeghii/"><img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Telegram-Animated-Emojis/main/Symbols/Exclamation%20Question%20Mark.webp" alt="Exclamation Question Mark" width="35" height="35" /></a> How This Project Uses LSP

In this project, we have a base class `CollectionBase`, and two child classes: `Array` and `List`.

---

### <a href="https://www.linkedin.com/in/soheilsadeghii/"><img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Telegram-Animated-Emojis/main/Symbols/Cross%20Mark.webp" alt="Cross Mark" width="35" height="35" /></a> Violating LSP (Problem Example):
```csharp
CollectionBase array = new Array();
array.Add(2); // ❌ Throws Exception
```
Here, Array inherits from CollectionBase, but doesn’t support the Add() method.
This breaks LSP because Array cannot be used safely where CollectionBase is expected.


---

## <a href="https://www.linkedin.com/in/soheilsadeghii/"><img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Telegram-Animated-Emojis/main/Symbols/Check%20Box%20With%20Check.webp" alt="Check Box With Check" width="35" height="35" /></a> Better Way:
To follow LSP, both Array and List should either:

Inherit from a base class that defines Add(), or

Implement a common interface like IList, so they can be used interchangeably

If a subclass cannot work correctly in place of its parent, then inheritance is being used incorrectly.

---

## <a href="https://www.linkedin.com/in/soheilsadeghii/"><img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Telegram-Animated-Emojis/main/Symbols/Check%20Mark%20Button.webp" alt="Check Mark Button" width="35" height="35" /></a> Following LSP (Better Design - Commented Example)
In the commented version, all child classes properly implement the Add() method:

``` CSharp
public class CollectionBase
{
    public virtual void Add(object item) { }
}

public class Array : CollectionBase
{
    public override void Add(object item) { /* logic */ }
}

public class List : CollectionBase
{
    public override void Add(object item) { /* logic */ }
}
```
Now, any class that inherits from CollectionBase can be used without fear of exceptions or unexpected behavior. This respects the Liskov Substitution Principle.

---

## <a href="https://www.linkedin.com/in/soheilsadeghii/"><img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Telegram-Animated-Emojis/main/Symbols/Check%20Mark%20Button.webp" alt="Check Mark Button" width="35" height="35" /></a> What I Learned

LSP is not just about inheritance, but about safe and expected behavior.

I made sure all subclasses follow the same contract as the base class.

This design improves code safety and makes the system more flexible.

---

## <a href="https://www.linkedin.com/in/soheilsadeghii/"><img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Telegram-Animated-Emojis/main/Objects/File%20Folder.webp" alt="File Folder" width="35" height="35" /></a> Project Structure
```
LiskovSubstitutionPrinciple/
│
├── Program.cs             // Entry point
├── CollectionBase.cs      // Base class
├── Array.cs               // Subclass (without Add method)
├── List.cs                // Subclass implementing Add
```
---
Thanks for checking out this project!  
If you found it helpful, feel free to <a href="https://www.linkedin.com/in/soheilsadeghii/"><img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Telegram-Animated-Emojis/main/Animals%20and%20Nature/Star.webp" alt="Star" width="15" height="15" /></a> the repo or share it with others.  
Contributions, feedback, and suggestions are always welcome!
<br>
<br>
<!-- ![Visitor Badge](https://visitor-badge.laobi.icu/badge?page_id=SoheilSadeghii.LiskovSubstitutionPrinciple) -->
