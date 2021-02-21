# Casting

**Casting** is a method of forcing the compile-time type of any expression. 

```java
//Assuming that there is some bethod
public Weapon maxWeapon(Weapon firstWeapon, Weapon secondWeapon);

//We can cast to a subclass if we know that the resultant weapon will have 
//the type we want.

Polearm maxPole = (Polearm) maxWeapon(new Polearm(13), new Polearm(34));
```

Note, however, that casting can run into some issues at runtime. For example, the following

```java
Polearm maxPole = (Polearm) maxWeapon(new Claymore(445), new Catalyst(45));
```

would run into issues at runtime, although it would be fine at compile time.

