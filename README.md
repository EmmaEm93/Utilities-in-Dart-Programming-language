# Utilities-in-Dart-Programming-language
String Manipulation:
import 'dart:io';

void stringManipulation() {
  String input = 'Hello, Dart!';
  
  // String concatenation
  String greeting = 'Welcome to ';
  String concatenated = greeting + input;
  print('Concatenated: $concatenated');
  
  // String interpolation
  String name = 'User';
  String interpolated = 'Hello, $name!';
  print('Interpolated: $interpolated');
  
  // Substring extraction
  String substring = input.substring(7, 11);
  print('Substring: $substring');
  
  // Case conversion
  String upperCase = input.toUpperCase();
  String lowerCase = input.toLowerCase();
  print('Uppercase: $upperCase');
  print('Lowercase: $lowerCase');
  
  // Reverse string
  String reversed = input.split('').reversed.join('');
  print('Reversed: $reversed');
  
  // Count length
  int length = input.length;
  print('Length: $length');
}


Implement a program that demonstrates string concatenation, interpolation, substring extraction, and case conversion (upper/lowercase).
Add functionality to reverse a string and count its length.

Collections (Lists, Sets, Maps):
void collectionUsage() {
  // List
  List<String> fruits = ['Apple', 'Banana', 'Cherry'];
  fruits.add('Date');
  fruits.remove('Banana');
  print('Fruits List:');
  for (var fruit in fruits) {
    print(fruit);
  }

  // Set
  Set<int> numbers = {1, 2, 3};
  numbers.add(2); // Duplicate will not be added
  numbers.add(4);
  print('Numbers Set:');
  numbers.forEach((number) => print(number));

  // Map
  Map<String, int> scores = {'Alice': 85, 'Bob': 90};
  scores['Charlie'] = 95; // Add new entry
  scores.remove('Alice');
  print('Scores Map:');
  scores.forEach((key, value) {
    print('$key: $value');
  });
}


Create a Dart program that demonstrates the use of lists, sets, and maps.
Include operations like adding, removing, and iterating over items.
Showcase scenarios where each collection type is most appropriate.

File Handling:
void fileHandling() async {
  String inputFilePath = 'input.txt';
  String outputFilePath = 'output.txt';
  
  try {
    // Reading from a file
    String content = await File(inputFilePath).readAsString();
    print('File Content: $content');

    // Writing to another file
    await File(outputFilePath).writeAsString('New Data: $content');
    print('Data written to $outputFilePath');
  } catch (e) {
    print('Error during file operations: $e');
  }
}


Write a Dart program that reads content from a file and writes new data into another file.
Demonstrate how to handle errors during file operations.

Date and Time:
void dateTimeUtilities() {
  DateTime now = DateTime.now();
  print('Current DateTime: $now');

  // Add days
  DateTime futureDate = now.add(Duration(days: 5));
  print('Future Date (5 days later): $futureDate');

  // Subtract days
  DateTime pastDate = now.subtract(Duration(days: 5));
  print('Past Date (5 days earlier): $pastDate');

  // Difference between two dates
  Duration difference = futureDate.difference(pastDate);
  print('Difference in days: ${difference.inDays}');
}

Develop a program that uses Dart's DateTime class.
Format, parse, and manipulate dates (e.g., add/subtract days).
Calculate the difference between two dates.

Exercise:

Combine the above utilities to build a small application. This application should:
Perform string manipulation on user input.
Store the results in a collection.
Save the data to a file.
Use the date and time utilities to log when each entry was made.

void main() async {
  // String Manipulation
  stringManipulation();
  
  // Collections
  collectionUsage();
  
  // File Handling
  await fileHandling();

  // Date and Time
  dateTimeUtilities();

  // Combine functionalities
  String userInput = 'Sample Input';
  String processedData = userInput.toUpperCase();
  await logData(processedData);
}

Future<void> logData(String data) async {
  DateTime now = DateTime.now();
  String logEntry = '$now: $data\n';
  await File('log.txt').writeAsString(logEntry, mode: FileMode.append);
  print('Logged data: $logEntry');
}
