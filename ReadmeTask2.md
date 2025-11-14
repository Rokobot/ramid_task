# Zero to Hero Həftəsi
![ZERO TO HERO - Muhammad Hafiz](https://github.com/user-attachments/assets/813cc93b-95ba-48a2-be98-034221a76fa4)

# Ramid Askerov

🕒 Deadline:  
![deadline](https://readme-typing-svg.demolab.com?font=Fira+Code&pause=10&color=E63946&center=true&vCenter=true&width=200&fontSize=40&lines=Bazar_günü,+24%3A00)

---



These are standard Dart programming exercises and interview questions. Here are the solutions and explanations for each task.

## 1\) Task — Map & String 🗺️

To store the user profile, a `Map<String, dynamic>` (or more specific types like `Map<String, Object>`) is used, with keys for `name`, `age`, and `city`.

```dart
Map<String, dynamic> userProfile = {
  'name': 'Alice',
  'age': 25,
  'city': 'London',
};

String name = userProfile['name'] as String;
int age = userProfile['age'] as int;
String city = userProfile['city'] as String;

print('$name is $age years old and lives in $city');
```

**Output:**

```
Alice is 25 years old and lives in London
```

-----

## 2\) Task — List & Filter 💸

We use the `where` method on the `List` to iterate and select only the elements that meet the specified condition (price $> 50$). The `forEach` method is then used to print the filtered results.

```dart
List<int> prices = [20, 55, 40, 80, 10];

List<int> filteredPrices = prices.where((price) => price > 50).toList();

filteredPrices.forEach(print);
```

**Output:**

```
55
80
```

-----

## 3\) Task — Set & Unique Values 📧

A `Set` naturally only stores unique values. Adding duplicate elements has no effect after the first addition; the set maintains its collection of unique items.

```dart
Set<String> userEmails = {};

userEmails.add("a@mail.com");
userEmails.add("b@mail.com");
userEmails.add("a@mail.com"); // Duplicate, ignored by the Set

print(userEmails);
```

**Output:**

```
{a@mail.com, b@mail.com}
```

-----

## 4\) Problem — dynamic type (Fix) 🔄

The error occurs because `x` is assigned an `int` (`10`). The `int` type in Dart does **not** have a `length` property. While `dynamic` allows the code to compile, it fails at runtime.

**Fix:** Assign `x` a type that **does** have a `.length` property, such as a `String` or `List`.

```dart
dynamic x = "Hello"; // Changed to a String
print(x.length);
```

**Output:**

```
5
```

*(Alternatively, you could change `x.length` to a valid operation for an integer, but the problem usually intends to demonstrate the type mismatch with `dynamic`.)*

-----

## 5\) Problem — Nullable (Fix) ❓

The variable `name` is a nullable `String?` and is currently `null`. Accessing a property (`.length`) on a `null` variable throws a runtime error.

**Fix:** Use the **null-aware access operator `?`** to only access `.length` if `name` is not `null`. If `name` is `null`, the entire expression evaluates to `null`.

```dart
String? name;
print(name?.length); // Using the null-aware access operator
```

**Output:**

```
null
```

-----

## 6\) Problem — late variable (Fix) ⏳

### Explanation

The code throws an **`LateInitializationError`** because a `late` variable must be initialized **before** its first read. In the provided code, `print(age);` attempts to read the variable *before* it has been assigned the value `20` (`age = 20;`).

### Fix

The variable must be assigned a value before it is accessed.

```dart
late int age;
age = 20; // Initialization happens before the variable is read
print(age);
```

**Output:**

```
20
```

-----

## 7\) Problem — List access (Fix) 🍎

Dart lists are **zero-indexed**. For a list with 2 elements:

  * Index 0 is "Apple"
  * Index 1 is "Banana"

Attempting to access `fruits[2]` throws a **`RangeError`** because index 2 is out of bounds.

**Fix:** Access the elements at a valid index (0 or 1).

```dart
List<String> fruits = ["Apple", "Banana"];
print(fruits[1]); // Accessing the second element (Banana)
```

**Output:**

```
Banana
```

-----

## 8\) Interview — Map usage 🤔

You would use a **Map** when you need to look up data by a specific, unique **key** rather than by its numeric position. A List is for ordered collections accessed by an integer index.

| Feature | List | Map |
| :--- | :--- | :--- |
| **Primary Access** | Numeric index (0, 1, 2, ...) | Unique Key (String, int, etc.) |
| **Best For** | Ordered sequences, simple collections | Associating data, configurations, records |

### Simple Real-Life Example

  * **List Example:** A **shopping list** of items: `["Milk", "Eggs", "Bread"]`. You usually iterate through the items in order.
  * **Map Example:** A **user record** or **configuration settings**: You want to quickly find the `username` or the `API_KEY`.
    ```dart
    Map<String, String> userRecord = {
      'userID': 'A100',
      'username': 'john_doe',
      'email': 'john@example.com'
    };
    // Accessing the username directly by its key is O(1)
    print(userRecord['username']); // Output: john_doe
    ```

-----

## 9\) Interview — dynamic vs final ✨

| Keyword | Purpose | Mutability | Reassignment | Performance |
| :--- | :--- | :--- | :--- | :--- |
| **`dynamic`** | Declares a variable whose **type is not checked** at compile-time. The variable can hold any value (int, String, etc.). | Can be mutated (contents changed) AND reassigned (new value/type assigned). | Yes | Slower, as type checks must happen at **runtime**. |
| **`final`** | Declares a variable that **can only be set once**. Its value is fixed after initialization. | Can be mutated **if** it's a collection (like a List or Map), but the variable itself **cannot be reassigned**. | No | Faster, as the type is known and enforced at **compile-time**. |

### Example where `dynamic` is useful

`dynamic` is often useful when dealing with data coming from external sources (like JSON decoding) where the structure might be flexible or unknown until runtime.

```dart
// Data parsed from a JSON API call
dynamic apiResponse = {
  'status': 'success',
  'data': 42
};

// Later, the API might change, and 'data' could be a string
// apiResponse = '{"status": "success", "data": "The Answer"}';

// You can access 'data' without knowing its type beforehand,
// deferring type checking until runtime.
if (apiResponse['status'] == 'success') {
  print('Data received: ${apiResponse['data']}');
}
```

-----

## 10\) Interview — nullable operators 🤯

The three main nullable operators in Dart are used to handle variables that might hold a `null` value (`Type?`).

| Operator | Name | Purpose |
| :--- | :--- | :--- |
| **`?`** | Null-aware Access (`?.`) / Nullable Type (`String?`) | **Checks if the value is null** before accessing a property or method. If the value is `null`, the expression evaluates to `null`. |
| **`??`** | Null Coalescing Operator | Provides a **default value** if the expression on the left is `null`. |
| **`!`** | Non-nullable Assertion Operator | **Tells the compiler** to treat a nullable type as non-nullable, asserting that the value is **definitely not null**. If the value *is* null at runtime, it will crash (throw an error). |

### Example with `String?`

```dart
String? nullableName1 = 'Alice';
String? nullableName2 = null;

// 1. Null-aware Access Operator (?.)
// Safely calls .toUpperCase() only if nullableName1 is not null.
print(nullableName1?.toUpperCase()); // Output: ALICE 
print(nullableName2?.toUpperCase()); // Output: null (no error)

// 2. Null Coalescing Operator (??)
// Prints nullableName2, OR "Guest" if it's null.
print(nullableName2 ?? 'Guest'); // Output: Guest 

// 3. Non-nullable Assertion Operator (!)
// Asserts that nullableName1 is NOT null. Safe here.
print(nullableName1!.length); // Output: 5

// **DANGEROUS**: Asserts that nullableName2 is NOT null, but it IS null.
// print(nullableName2!.length); // This would crash at runtime!
```

-----

# Alfa Level — Dart Exercises

## 1\) Alfa Task — Nested Map & List 🎓

We use a nested structure: a `Map` where the key is the student's name (`String`) and the value is a `List<int>` of their grades. We iterate through the Map, calculate the average, and check the condition.

```dart
Map<String, List<int>> students = {
  'Alice': [80, 75, 90],
  'Bob': [65, 80, 75],
  'Charlie': [50, 60, 65],
  'David': [95, 85, 90],
};

print('Students with an average grade above 70:');

students.forEach((name, grades) {
  // Calculate sum of grades
  int totalSum = grades.reduce((sum, grade) => sum + grade);
  
  // Calculate average
  double average = totalSum / grades.length;
  
  // Check condition
  if (average > 70) {
    print(name);
  }
});
```

**Output:**

```
Students with an average grade above 70:
Alice
Bob
David
```

-----

## 2\) Alfa Task — Map of URLs 🖼️
![_ (2)](https://github.com/user-attachments/assets/b5b15932-af22-45f3-8831-2116386aaf04)



We iterate over the Map's values (the URLs) and use the `endsWith` `String` method to check if the URL string ends with the desired suffix `.jpeg`.

```dart
Map<String, String> imageLibrary = {
  'profile': 'https://example.com/profile.png',
  'homepage_banner': 'https://example.com/image.jpeg',
  'icon': 'https://storage.net/icon.svg',
  'gallery_photo': 'https://mywebsite.com/photo.jpeg',
};

print('JPEG URLs:');

imageLibrary.forEach((imageName, url) {
  if (url.endsWith('.jpeg')) {
    print(url);
  }
});
```

**Output:**

```
JPEG URLs:
https://example.com/image.jpeg
https://mywebsite.com/photo.jpeg
```

-----

## 3\) Alfa Task — Nullable + Conditional 💯

This task requires handling three conditions: score is high (\>= 50), score is low (\< 50), or score is null. The **null coalescing operator (`??`)** is a clean way to handle the `null` case first.

```dart
void checkScore(int? score) {
  // Use ?? to default to a value (e.g., -1) if score is null,
  // then check conditions on the resulting value.
  
  String result = score == null 
      ? "No score"
      : score >= 50 
          ? "Passed"
          : "Failed";
          
  print(result);
}

// Example calls
checkScore(80); // Passed
checkScore(null); // No score
checkScore(45); // Failed
checkScore(50); // Passed
```

**Output:**

```
Passed
No score
Failed
Passed
```
