1) Task — Map & String

Question: Create a Map to store a user's profile with name, age, and city. Print the user info in a sentence like:

Alice is 25 years old and lives in London


Hint: Use Map with keys name, age, city.

2) Task — List & Filter

Question: Create a List of product prices. Print only the prices that are greater than 50.
Example List: [20, 55, 40, 80, 10]
Output:

55
80

3) Task — Set & Unique Values

Question: Create a Set to store user emails. Add some duplicate emails. Print the Set to show only unique emails.
Example: ["a@mail.com", "b@mail.com", "a@mail.com"]
Output:

{a@mail.com, b@mail.com}

4) Problem — dynamic type

Code:

dynamic x = 10;
print(x.length);


Task: Fix the code so it works correctly.

5) Problem — Nullable

Code:

String? name;
print(name.length);


Task: Fix the code using nullable operator ? to avoid error.

6) Problem — late variable

Code:

late int age;
print(age);
age = 20;


Task: Explain why this throws an error and fix it.

7) Problem — List access

Code:

List<String> fruits = ["Apple", "Banana"];
print(fruits[2]);


Task: Fix the error.

8) Interview — Map usage

Question: When would you use a Map instead of a List? Give a simple real-life example.

9) Interview — dynamic vs final

Question: What is the difference between dynamic and final in Dart? Give an example where dynamic is useful.

10) Interview — nullable operators

Question: Explain the difference between ?, ??, and ! in Dart. Show a small example using a nullable String.






Alfa Level — Dart Exercises
1) Alfa Task — Nested Map & List

Question:
Create a Map of students. Each student has a name and a List of grades. Print the names of students whose average grade is above 70.

Hint: Use Map + List + simple average calculation.

Example Output:

Alice
Bob

2) Alfa Task — Map of URLs

Question:
Create a Map where keys are image names and values are URLs like "https://example.com/image.jpeg". Loop through the Map and print only the URLs that end with .jpeg.

Example Output:

https://example.com/image.jpeg
https://mywebsite.com/photo.jpeg

3) Alfa Task — Nullable + Conditional

Question:
You have a nullable int? score. Print "Passed" if the score is 50 or above, "Failed" if below 50, and "No score" if the value is null.

Hint: Use ?? or conditional operators.

Example Output:

Passed
No score
Failed
