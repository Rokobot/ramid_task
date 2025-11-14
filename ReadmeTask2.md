# Dart Beginner Exercises

This README contains **beginner to slightly advanced Dart exercises** covering Maps, Lists, Sets, data types, nullable operators, and some Alfa Level challenges.

---

## **1) Task — Map & String**

**Question:**  
Create a Map to store a user's profile with `name`, `age`, and `city`. Print the user info in a sentence like:

Alice is 25 years old and lives in London

pgsql
Copy code

**Hint:** Use Map with keys `name`, `age`, `city`.

**Example Code:**
```dart
void main() {
  Map<String, dynamic> user = {
    'name': 'Alice',
    'age': 25,
    'city': 'London'
  };
  print('${user['name']} is ${user['age']} years old and lives in ${user['city']}');
}
Output:

pgsql
Copy code
Alice is 25 years old and lives in London
2) Task — List & Filter
Question:
Create a List of product prices. Print only the prices that are greater than 50.

Example List: [20, 55, 40, 80, 10]

Example Code:

dart
Copy code
void main() {
  List<int> prices = [20, 55, 40, 80, 10];
  for (var price in prices) {
    if (price > 50) print(price);
  }
}
Output:

Copy code
55
80
3) Task — Set & Unique Values
Question:
Create a Set to store user emails. Add some duplicate emails. Print the Set to show only unique emails.

Example: ["a@mail.com", "b@mail.com", "a@mail.com"]

Example Code:

dart
Copy code
void main() {
  Set<String> emails = {"a@mail.com", "b@mail.com", "a@mail.com"};
  print(emails);
}
Output:

css
Copy code
{a@mail.com, b@mail.com}
4) Problem — dynamic type
Code:

dart
Copy code
dynamic x = 10;
print(x.length);
Task: Fix the code so it works correctly.

5) Problem — Nullable
Code:

dart
Copy code
String? name;
print(name.length);
Task: Fix the code using nullable operator ? to avoid error.

6) Problem — late variable
Code:

dart
Copy code
late int age;
print(age);
age = 20;
Task: Explain why this throws an error and fix it.

7) Problem — List access
Code:

dart
Copy code
List<String> fruits = ["Apple", "Banana"];
print(fruits[2]);
Task: Fix the error.

8) Interview — Map usage
Question:
When would you use a Map instead of a List? Give a simple real-life example.

9) Interview — dynamic vs final
Question:
What is the difference between dynamic and final in Dart? Give an example where dynamic is useful.

10) Interview — nullable operators
Question:
Explain the difference between ?, ??, and ! in Dart. Show a small example using a nullable String.

Alfa Level — Dart Exercises
1) Alfa Task — Nested Map & List
Question:
Create a Map of students. Each student has a name and a List of grades. Print the names of students whose average grade is above 70.

Example Output:

nginx
Copy code
Alice
Bob
2) Alfa Task — Map of URLs
Question:
Create a Map where keys are image names and values are URLs like "https://example.com/image.jpeg". Loop through the Map and print only the URLs that end with .jpeg.

Example Output:

arduino
Copy code
https://example.com/image.jpeg
https://mywebsite.com/photo.jpeg
3) Alfa Task — Nullable + Conditional
Question:
You have a nullable int? score. Print "Passed" if the score is 50 or above, "Failed" if below 50, and "No score" if the value is null.

Example Output:

yaml
Copy code
Passed
No score
Failed
yaml
Copy code

---

If you want, I can also **add clickable sections and a table of contents** so it looks like a professional exercise sheet for GitHub or a course material, fully visualized with headings, code blocks, and outputs.  

Do you want me to do that next?
