# Generics

## Defining a Generic Class

To define a Generic Class you define a class and append

```
🐚 name type
```

for each generic argument the class shall take. This structure is called *generic argument*. *name*  must be the name of the argument and *type* any type name.

*type*  is a *generic argument constraint* and types provided for this argument must be compatible with that constraint.

In the class body you can reference to the generic type arguments by its name.

See this example for a “box” that can store objects.

```
🐇 🎁 🐚 T 🔵 🍇

  🍰 content T

  🐈 ✂️ =content T 🍇
    🍮 content =content
  🍉

  🐖 🎉 ➡️ T 🍇
    🍎 content
  🍉

🍉
```

## Subclassing a Generic Class

Naturally you can subclass a generic class. Like in any other circumstance you have to provide values for the superclass’s generic arguments. For instance:

```
🐇 ☑️ 🎁 🐚 🔡 🍇

🍉
```

If the subclass itself takes a generic argument this argument can be used as argument for the superclass:

```
🐇 🌟 🐚 A 🔵 🎁 🐚 A 🍇

🍉
```

## Compatibility

A generic type *A* is compatible to a generic type *B* if their base types are compatible and all generic argument values of *A* are compatible to those of *B*.

## Runtime Typing (Casting)

>!H This is a 0.x limitation. Enhancements in the future will possibly remove this limitation.

At the moment it’s not possible to store the type information of instances of generic classes at runtime. Therefore casts to classes with specific generic arguments cannot be verified and are forbidden. You will be confronted with the following error message if you try that anyway:

> Dynamic casts involving generic type arguments are not possible yet. Please specify the generic argument constraints of the class for compatibility with future versions.

When you perform a cast you must always specify the generic argument constraint for each argument. Example:

```
🍰 box ⚪️

🔲 box 🎁🐚🔡
```

The above example will not compile. Instead you have to specify:

```
🍰 box ⚪️

🔲 box 🎁🐚🔵
```
