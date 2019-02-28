# Chapter 2. Creating and Destroying Objects

## Item 1: Consider static factory methods instead of constructors
the traditional way for a class to allow the client to obtain an instance is to provide public constructor.
Another possibility is to provide *public static factory method*, which is a
simple static method that returns an instance of the class.
Pros:
unlike constructors
  * they have name
  * they're not required to create a new object each time they're invoked
  * they can return an object of any subtype of their return type
  * the class of the returned object can vary from call to call as a function
    of the input parameters
    parameters in a function
  * the class of the returned object need not to exist when the class
    containing the method is written
Cons:
  * classes without public or protected constructors cannot be subclassed
  * they are hard for programmers to find

## Item 2: Consider a builder when faced with many constructor parameters
static factories and constructor share a limitation: they do not scale well
with large numbers of parameters
Traditionally, programmers tackle this issue with the **telescoping constructor
** pattern:
``` java
// Telescoping constructor pattern - does not scale well!
 public class NutritionFacts {
   private final int servingSize; // (mL) required
   private final int servings; // (per container) required
   private final int calories; // (per serving) optional
   private final int fat; // (g/serving) optional
   private final int sodium; // (mg/serving) optional
   private final int carbohydrate; // (g/serving) optional

   public NutritionFacts(int servingSize, int servings) {
     this(servingSize, servings, 0);
   }

   public NutritionFacts(int servingSize, int servings, int calories) {
     this(servingSize, servings, calories, 0);
   }

   public NutritionFacts(int servingSize, int servings, int calories, int fat) {
     this(servingSize, servings, calories, fat, 0);
   }

   public NutritionFacts(int servingSize, int servings, int calories, int fat, int sodium) {
     this(servingSize, servings, calories, fat, sodium, 0);
   }

   public NutritionFacts(int servingSize, int servings, int calories, int fat, int sodium, int carbohydrate) {
     this.servingSize = servingSize;
     this.servings = servings;
     this.calories = calories;
     this.fat = fat;
     this.sodium = sodium;
     this.carbohydrate = carbohydrate;
   }
 }
```
the cons of this solutions are that one have to count parameters to find out
what means all the values, and if the client accidentally reverses the order of
the parameters, the compiler won't complain, but the program will misbehave at
runtime.

A second alternative could be the **JavaBeans** pattern, in which you call a
parameterless constructor to create the object and then call the setter methods
to set each required parameter and each optional parameter of interest:
```java
// JavaBeans Pattern - allows inconsistency, mandates mutability
 public class NutritionFacts {
   // Parameters initialized to default values (if any)
   private int servingSize = -1; // Required; no default value
   private int servings = -1; // Required; no default value
   private int calories = 0;
   private int fat = 0;
   private int sodium = 0;
   private int carbohydrate = 0;

   public NutritionFacts() { }
   // Setters
   public void setServingSize(int val) { servingSize = val; }
   public void setServings(int val) { servings = val; }
   public void setCalories(int val) { calories = val; }
   public void setFat(int val) { fat = val; }
   public void setSodium(int val) { sodium = val; }
   public void setCarbohydrate(int val) { carbohydrate = val; }
 }
```
The cons of this pattern are that a JavaBean may be in an inconsistent state
partway through its construction, and that it forces you to program in a way
that precludes immutability.

A third alternative is called the **Builder** pattern:
```java
public class NutritionFacts {
  private final int servingSize;
  private final int servings;
  private final int calories;
  private final int fat;
  private final int sodium;
  private final int carbohydrate;

  public static class Builder {
    // Required parameters
    private final int servingSize;
    private final int servings;

    // Optional parameters - initialized to default values
    private int calories = 0;
    private int fat = 0;
    private int sodium = 0;
    private int carbohydrate = 0;

    public Builder(int servingSize, int servings) {
      this.servingSize = servingSize;
      this.servings = servings;
    }

    public Builder calories(int val) {
      calories = val;
      return this;
    }
    public Builder fat(int val) {
      fat = val;
      return this;
     }
    public Builder sodium(int val) {
      sodium = val;
      return this;
    }
    public Builder carbohydrate(int val) {
      carbohydrate = val;
      return this;
    }

    public NutritionFacts build() {
      return new NutritionFacts(this);
    }
  }

   private NutritionFacts(Builder builder) {
     servingSize = builder.servingSize;
     servings = builder.servings;
     calories = builder.calories;
     fat = builder.fat;
     sodium = builder.sodium;
     carbohydrate = builder.carbohydrate;
   }
 }
```
Builder pattern is a good choice when we have multiples parameters


## Item 3: Enforce the singleton property with a private constructor or an enum type
Making a class a singleton can make it difficult to test its clients because it’s impossible to substitute a mock implementation for a singleton unless it implements an interface that serves as its type.
Three differents approaches:
  * public final field
  * public static factory method
  * single-element enum

## Item 4: Enforce noninstantiability with a private constructor
Sometimes you want to create a class that is not noninstantiable, just for grouping methods for utilities etc.
In that cases, *a class can be noninstantiable by including a private constructor*

## Item 5: Prefer dependency injection to hardwiring resources
Do not use a singleton or static utility class to implement a class that depends on one or more underlying resources whose behavior affects that of the class, and do not have the class create these resources directly. Instead, pass the resources, or factories to create them, into the constructor (or static factory or builder). This practice, known as dependency injection, will greatly enhance the flexibility, reusability, and testability of a class.
