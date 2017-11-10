# c# properties from college video in intermediate coding

c# has clever mechanism's that allow you to encapsulate properties and code within the 'visual studio' IDE.

### using properties

```c#
public class Car {
  private string owner;
  public string GetOwner() { return owner; }
  public void SetOwner(string owner) {
    this.owner = owner;
  }
}

//client code
Car C = new Car("ford");
C.SetOwner("Lewis");
Console.WriteLine(C.GetOwner());

//a better way to do it
Car N = new Car("Ford");
C.Owner = "Lewis";
Console.WriteLine(C.Owner);
```
---

in the second version, you are accessing a method, not a property of the object Car

standard layout of a property is as follows:
```C#
Modifiers Type ProprtyName {
  modifier get {...}
  modifier ser {...}
 }
 ```
---

some key components of the property are the
..*optional modifiers for `public` or `private` ..*data type and name ..*optional accessors to `get` and `set` values

a few examples:

```C#
public class Car {
  private string owner;
  
  public string Owner {
    get { return owner; }
    ser { ............. }
  }
}

Car C = new Car();
// set owner here
// other stuff
Console.WriteLine(C.Owner);
```

breakdown of using an `accessor`
`propfull` to get the code snippet
```c#
public class Car {
  private string owner;
  public string Owner {
    get { return owner; }
    ser { owner = value; } //this is where the c.owner = "Lewis" value is stored
  }
}

Car C = new Car();
C.Owner = "Lewis";
```

another example:

```c#
public class Car {
  private int speed, maxspeed = 70;
  public int Speed {
    get { return speed; }
    set {
      if ( value >= 0 && value <= maxspeed ) { speed = value } // this code creates a safety buffer for the highsped values for cars
    }
  }
}
```
---

#### further `get accessor` code

the return value is not necessarily the value of a field. the value could be computed, 'calculated as needed', 'set' being N/A
```c#
public class Car {
  private int speed;
  private string owner;
  /// more code
  public string Details {
    get {
      return string.Format("Owned by {0} doing {1} mph", owner, speed);
    }
  }
}
```
---
  