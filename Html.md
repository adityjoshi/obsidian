``` xml
<?xml version="1.0" encoding="UTF-8"?>
<Students>
    <Student>
        <St_id>1001</St_id>
        <Stname>Ram</Stname>
        <Dept>CSE</Dept>
        <totalmarks>500</totalmarks>
        <Grades>F</Grades>
    </Student>
    <Student>
        <St_id>1002</St_id>
        <Stname>Ravi</Stname>
        <Dept>Mech</Dept>
        <totalmarks>700</totalmarks>
        <Grades>P</Grades>
    </Student>
    <Student>
        <St_id>1003</St_id>
        <Stname>John</Stname>
        <Dept>CSE</Dept>
        <totalmarks>650</totalmarks>
        <Grades>P</Grades>
    </Student>
    <Student>
        <St_id>1004</St_id>
        <Stname>Charith</Stname>
        <Dept>Civil</Dept>
        <totalmarks>350</totalmarks>
        <Grades>F</Grades>
    </Student>
    <Student>
        <St_id>1005</St_id>
        <Stname>Sam</Stname>
        <Dept>Mech</Dept>
        <totalmarks>500</totalmarks>
        <Grades>F</Grades>
    </Student>
</Students>

for $student in /Students/Student
where $student/Grades = 'F'
return $student/Stname

for $student in /Students/Student
where xs:integer($student/totalmarks) > 500
return $student/Stname

for $student in /Students/Student
where $student/Dept = 'CSE'
return $student/Stname

```


**Regex**

```php
<?php
$string = "Hello World! Welcome to the World!";
$pattern = "/World/";
$replacement = "Universe";

$new_string = preg_replace($pattern, $replacement, $string);
echo $new_string; // Outputs: Hello Universe! Welcome to the Universe!
?>
```

``` js
const string = "Hello World! Welcome to the World!";
const pattern = /World/g;
const replacement = "Universe";

const newString = string.replace(pattern, replacement);
console.log(newString); // Outputs: Hello Universe! Welcome to the Universe!


const string = "My phone number is 123-456-7890.";
const pattern = /\d/g; // \d matches any digit, 'g' flag for global replacement
const replacement = "#";

const newString = string.replace(pattern, replacement);
console.log(newString); // Outputs: My phone number is ###-###-####.

```

Pattern Matching 
```js 
const email = "example@example.com";
const pattern = /^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/;

if (pattern.test(email)) {
    console.log("Valid email address.");
} else {
    console.log("Invalid email address.");
}

```

# Plsql Factorial and all 

Here are PL/SQL programs for calculating the factorial, generating the Fibonacci series, reversing a number, and checking if a number is an Armstrong number.

### 1. Factorial of a Number

The factorial of a number \( n \) is the product of all positive integers less than or equal to \( n \).

```plsql
DECLARE
    n NUMBER := 5; -- Input number
    factorial NUMBER := 1;
BEGIN
    FOR i IN 1..n LOOP
        factorial := factorial * i;
    END LOOP;
    DBMS_OUTPUT.PUT_LINE('Factorial of ' || n || ' is ' || factorial);
END;
/
```

### 2. Fibonacci Series

The Fibonacci series is a sequence of numbers where each number is the sum of the two preceding ones, usually starting with 0 and 1.

```plsql
DECLARE
    n NUMBER := 10; -- Number of Fibonacci terms to generate
    a NUMBER := 0;
    b NUMBER := 1;
    temp NUMBER;
BEGIN
    DBMS_OUTPUT.PUT_LINE('Fibonacci Series:');
    DBMS_OUTPUT.PUT_LINE(a);
    DBMS_OUTPUT.PUT_LINE(b);
    FOR i IN 3..n LOOP
        temp := a + b;
        a := b;
        b := temp;
        DBMS_OUTPUT.PUT_LINE(temp);
    END LOOP;
END;
/
```

### 3. Reverse a Number

This program reverses a given number.

```plsql
DECLARE
    n NUMBER := 12345; -- Input number
    reverse_number NUMBER := 0;
    remainder NUMBER;
BEGIN
    WHILE n > 0 LOOP
        remainder := MOD(n, 10);
        reverse_number := reverse_number * 10 + remainder;
        n := FLOOR(n / 10);
    END LOOP;
    DBMS_OUTPUT.PUT_LINE('Reversed Number is ' || reverse_number);
END;
/
```

### 4. Armstrong Number

An Armstrong number (also known as a narcissistic number) is a number that is equal to the sum of its own digits each raised to the power of the number of digits.

For example, 153 is an Armstrong number because \( 1^3 + 5^3 + 3^3 = 153 \).

```plsql
DECLARE
    n NUMBER := 153; -- Input number
    temp NUMBER;
    sum NUMBER := 0;
    remainder NUMBER;
    digits NUMBER := 0;
BEGIN
    temp := n;
    
    -- Calculate the number of digits
    WHILE temp > 0 LOOP
        digits := digits + 1;
        temp := FLOOR(temp / 10);
    END LOOP;
    
    temp := n;
    
    -- Calculate the sum of digits raised to the power of the number of digits
    WHILE temp > 0 LOOP
        remainder := MOD(temp, 10);
        sum := sum + POWER(remainder, digits);
        temp := FLOOR(temp / 10);
    END LOOP;
    
    IF sum = n THEN
        DBMS_OUTPUT.PUT_LINE(n || ' is an Armstrong number.');
    ELSE
        DBMS_OUTPUT.PUT_LINE(n || ' is not an Armstrong number.');
    END IF;
END;
/
```

### Summary

- **Factorial**: Multiplies all integers from 1 to the given number.
- **Fibonacci**: Generates a series where each number is the sum of the two preceding ones.
- **Reverse Number**: Reverses the digits of a given number.
- **Armstrong Number**: Checks if the sum of digits each raised to the power of the number of digits equals the original number.

These PL/SQL blocks can be executed in any Oracle database environment that supports PL/SQL.


# session 
Session
A session is a way to store information (in variables) to be used across multiple pages.
Unlike a cookie, the information is not stored on the users computer.
A session is started with the session_start() function.
Session variables are set with the PHP global variable: $_SESSION.
```php 
<?php
// Start the session
session_start();
?>
<!DOCTYPE html>
<html>
<body>
<?php
// Set session variables
$_SESSION["name"] = "session";
$_SESSION["number"] = "1";
echo "Session variables are set." . "<br>";
echo $_SESSION["name"] . $_SESSION["number"];
?>
</body>
</html>
```

# cookie 
A cookie is often used to identify a user. A cookie is a small file that the server embeds on the
user's computer. Each time the same computer requests a page with a browser, it will send the
cookie too. With PHP, you can both create and retrieve cookie values.

Create Cookies With PHP
A cookie is created with the setcookie() function.
Syntax
setcookie(name, value, expire, path, domain, secure);

- **name**:
    
    - **Description**: Used to specify the name of the cookie. This is a mandatory argument.
    - **Details**: The name of the cookie must be a string. This name is used as the key to retrieve the cookie value.
    - **Example**: `userid`
- **value**:
    
    - **Description**: Used to store any value in the cookie. It is saved as a key-value pair with the cookie's name.
    - **Details**: The value can be any string or data you want to store. For example, if the name is `userid` and the value is `7007`, the cookie would store the user's ID.
    - **Example**: `7007`
- **expire**:
    
    - **Description**: Used to set the expiration time for the cookie.
    - **Details**: If you don't set an expiration time, the cookie will be treated as a session cookie and will expire when the browser is closed. You can set a specific expiration time using a timestamp (typically calculated as `time() + X`, where `X` is the number of seconds you want the cookie to last).
    - **Example**: `time() + 86400` (expires in 1 day)
- **path**:
    
    - **Description**: Used to set the path on the server where the cookie is accessible.
    - **Details**: If set, the cookie will be accessible only from that path or URL. To make the cookie accessible throughout the entire domain, set `'/'` as the path.
    - **Example**: `'/'`
- **domain**:
    
    - **Description**: Used to specify the domain where the cookie is accessible.
    - **Details**: This parameter can be used to limit access to the cookie across subdomains. For example, if the domain is set to `www.vitbhopal.com`, the cookie will not be accessible from `blog.vitbhopal.com`.
    - **Example**: `'www.vitbhopal.com'`
- **secure**:
    
    - **Description**: If set to `true`, the cookie will only be sent over HTTPS connections.
    - **Details**: This enhances security by ensuring that the cookie is transmitted securely. If this is set to `true` (or `1`), the cookie will only be available over a secure HTTPS connection.
    - **Example**: `true`


```php
<?php
$cookie_name = "vitbhopal";
$cookie_value = "vitb";
setcookie($cookie_name, $cookie_value, time() + (86400 * 30), "/"); // 86400 = 1 day
?>
<html>
<body>
<?php
if(!isset($_COOKIE[$cookie_name])) {
echo "Cookie named '" . $cookie_name . "' is not set!";
} else {
echo "Cookie '" . $cookie_name . "' is set!<br>";
echo "Value is: " . $_COOKIE[$cookie_name];
}
?>
</body>
</html>
<?php
setcookie("name", "John Watkin", time()+3600, "/","", 0);
setcookie("age", "36", time()+3600, "/", "", 0);
?>
<html>

<head>
<title>Setting Cookies with PHP</title>
</head>
<body>
<?php echo "Set Cookies"?>
</body>
</html>
```

To find the transpose of a matrix in JavaScript, you can follow these steps:

1. **Define the Matrix**: Create a 2D array representing the matrix.
2. **Initialize the Transposed Matrix**: Create an empty 2D array to hold the transposed matrix.
3. **Fill the Transposed Matrix**: Loop through the original matrix and assign the rows to columns in the new matrix.

#  Transpose of a Matrix

Here's a JavaScript code example to transpose a matrix:

```javascript
function transposeMatrix(matrix) {
    let transposed = [];

    // Iterate over the columns of the original matrix
    for (let i = 0; i < matrix[0].length; i++) {
        transposed[i] = [];
        
        // Iterate over the rows of the original matrix
        for (let j = 0; j < matrix.length; j++) {
            transposed[i][j] = matrix[j][i];
        }
    }

    return transposed;
}

// Example matrix
let matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
];

let transposedMatrix = transposeMatrix(matrix);

console.log("Original Matrix:");
console.log(matrix);
console.log("Transposed Matrix:");
console.log(transposedMatrix);
```

### Explanation

- **Input Matrix (`matrix`)**:
  ```javascript
  [
      [1, 2, 3],
      [4, 5, 6],
      [7, 8, 9]
  ]
  ```
- **Transposed Matrix (`transposedMatrix`)**:
  ```javascript
  [
      [1, 4, 7],
      [2, 5, 8],
      [3, 6, 9]
  ]
  ```

### How it Works

1. **Outer Loop (`i`)**: Iterates over the columns of the original matrix.
2. **Inner Loop (`j`)**: Iterates over the rows of the original matrix.
3. **Assignment (`transposed[i][j] = matrix[j][i]`)**: This statement flips the row and column indices, effectively transposing the matrix.

### Output

When you run the code, you'll get the following output:

```javascript
Original Matrix:
[ [ 1, 2, 3 ], [ 4, 5, 6 ], [ 7, 8, 9 ] ]
Transposed Matrix:
[ [ 1, 4, 7 ], [ 2, 5, 8 ], [ 3, 6, 9 ] ]
```

This is the transpose of the original matrix, where the rows have become columns and vice versa.

# XML SCHEMA
```XML
<?xml version="1.0" encoding="UTF-8"?>
<bookstore xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xsi:noNamespaceSchemaLocation="bookstore.xsd">
<book>
<title>Effective XML</title>
<author>Elliotte Rusty Harold</author>
<year>2004</year>
<price>39.95</price>
</book>
<book>
<title>Learning XML</title>
<author>Erik T. Ray</author>
<year>2003</year>
<price>34.95</price>

</book>
</bookstore>
<?xml version="1.0" encoding="UTF-8"?>
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">
<xs:element name="bookstore">
<xs:complexType>
<xs:sequence>
<xs:element name="book" maxOccurs="unbounded">
<xs:complexType>
<xs:sequence>
<xs:element name="title" type="xs:string"/>
<xs:element name="author" type="xs:string"/>
<xs:element name="year" type="xs:int"/>
<xs:element name="price" type="xs:float"/>
</xs:sequence>
</xs:complexType>
</xs:element>
</xs:sequence>
</xs:complexType>
</xs:element>
</xs:schema>
```
It seems there are some errors in the explanation you provided. Below is the corrected and more detailed explanation of each part of the XML Schema:

1. **`<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">`**:
   - This line declares that the document is an XML Schema and uses the XML Schema namespace. The `xs` prefix is associated with the `http://www.w3.org/2001/XMLSchema` namespace, which defines the standard for XML Schema definitions.

2. **`<xs:element name="bookstore">`**:
   - This declares the root element `bookstore` for the XML document. This element will contain the entire content of the XML document.

3. **`<xs:complexType>`**:
   - This indicates that the `bookstore` element contains complex content, meaning it has child elements (in this case, `book` elements).

4. **`<xs:sequence>`**:
   - This specifies that the child elements of `bookstore` must appear in a specific sequence. The order of elements as defined in the schema must be followed in the XML document.

5. **`<xs:element name="book" maxOccurs="unbounded">`**:
   - This defines the `book` element as a child of the `bookstore` element. The `maxOccurs="unbounded"` attribute means that the `book` element can appear an unlimited number of times within the `bookstore` element.

6. **`<xs:complexType>`**:
   - This indicates that the `book` element also contains complex content, meaning it will have its own child elements (like `title`, `author`, `year`, and `price`).

7. **`<xs:sequence>`**:
   - This specifies that the child elements of the `book` element must also appear in a specific sequence. The order defined here should be followed in the XML document.

8. **`<xs:element name="title" type="xs:string"/>`**:
   - This declares that the `title` element is a child of `book` and is of type `string`. This means the content of the `title` element should be textual.

9. **`<xs:element name="author" type="xs:string"/>`**:
   - This declares that the `author` element is a child of `book` and is of type `string`. Like `title`, the content of the `author` element should also be textual.

10. **`<xs:element name="year" type="xs:int"/>`**:
    - This declares that the `year` element is a child of `book` and is of type `int`. The content of the `year` element should be an integer value, representing the year of publication.

11. **`<xs:element name="price" type="xs:float"/>`**:
    - This declares that the `price` element is a child of `book` and is of type `float`. The content of the `price` element should be a floating-point number, representing the price of the book.


# DTD
A Document Type Definition (DTD) is a set of declarations that defines the structure and legal elements and attributes of an XML document. It specifies the rules for the markup, including the allowed elements, their attributes, and how they can be nested. DTDs can be used to validate XML documents, ensuring that they conform to the specified structure.

### Types of DTDs

There are two types of DTDs:

1. **Internal DTD**: The DTD is included within the XML document itself.
2. **External DTD**: The DTD is defined outside the XML document and is referenced by the XML document.




# File upload
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Simple File Upload</title>
</head>
<body>
    <h2>Upload a File</h2>
    <form action="upload.php" method="post" enctype="multipart/form-data">
        <input type="file" name="file" required>
        <button type="submit">Upload</button>
    </form>
</body>
</html>

```
```php
<?php
// Directory where files will be uploaded
$target_dir = "uploads/";
$target_file = $target_dir . basename($_FILES["file"]["name"]);

// Ensure the uploads directory exists
if (!file_exists($target_dir)) {
    mkdir($target_dir, 0777, true);
}

// Move the uploaded file to the target directory
if (move_uploaded_file($_FILES["file"]["tmp_name"], $target_file)) {
    echo "File uploaded successfully!";
} else {
    echo "Error uploading file.";
}
?>
```

Here’s a simple PHP script that connects to a MySQL database, creates a table for student details, inserts data into the table, and retrieves the data.

### 1. Database Connection

First, set up the database connection parameters.

```php
<?php
$servername = "localhost"; // Change to your server name if different
$username = "root"; // Your MySQL username
$password = ""; // Your MySQL password
$dbname = "school"; // Database name

// Create connection
$conn = new mysqli($servername, $username, $password, $dbname);

// Check connection
if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}
echo "Connected successfully<br>";
?>
```

### 2. Create Table for Student Details

Next, create a table for storing student details.

```php
<?php
// SQL query to create the students table
$sql = "CREATE TABLE IF NOT EXISTS students (
    id INT(6) UNSIGNED AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(50) NOT NULL,
    age INT(3) NOT NULL,
    grade VARCHAR(10) NOT NULL,
    reg_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
)";

if ($conn->query($sql) === TRUE) {
    echo "Table students created successfully<br>";
} else {
    echo "Error creating table: " . $conn->error . "<br>";
}
?>
```

### 3. Insert Data into the Table

You can insert data into the `students` table using an SQL `INSERT` query.

```php
<?php
// SQL query to insert data into the students table
$sql = "INSERT INTO students (name, age, grade)
VALUES ('John Doe', 18, '12th Grade')";

if ($conn->query($sql) === TRUE) {
    echo "New record created successfully<br>";
} else {
    echo "Error: " . $sql . "<br>" . $conn->error;
}
?>
```

### 4. Retrieve and Display Data from the Table

Finally, retrieve and display the data from the `students` table.

```php
<?php
// SQL query to select all data from the students table
$sql = "SELECT id, name, age, grade FROM students";
$result = $conn->query($sql);

if ($result->num_rows > 0) {
    // Output data of each row
    while($row = $result->fetch_assoc()) {
        echo "ID: " . $row["id"]. " - Name: " . $row["name"]. " - Age: " . $row["age"]. " - Grade: " . $row["grade"]. "<br>";
    }
} else {
    echo "0 results";
}

// Close the connection
$conn->close();
?>
```

### Full Script Example

Here’s the complete script in one file:

```php
<?php
$servername = "localhost";
$username = "root";
$password = "";
$dbname = "school";

// Create connection
$conn = new mysqli($servername, $username, $password, $dbname);

// Check connection
if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}
echo "Connected successfully<br>";

// Create table
$sql = "CREATE TABLE IF NOT EXISTS students (
    id INT(6) UNSIGNED AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(50) NOT NULL,
    age INT(3) NOT NULL,
    grade VARCHAR(10) NOT NULL,
    reg_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
)";

if ($conn->query($sql) === TRUE) {
    echo "Table students created successfully<br>";
} else {
    echo "Error creating table: " . $conn->error . "<br>";
}

// Insert data
$sql = "INSERT INTO students (name, age, grade)
VALUES ('John Doe', 18, '12th Grade')";

if ($conn->query($sql) === TRUE) {
    echo "New record created successfully<br>";
} else {
    echo "Error: " . $sql . "<br>" . $conn->error;
}

// Retrieve data
$sql = "SELECT id, name, age, grade FROM students";
$result = $conn->query($sql);

if ($result->num_rows > 0) {
    // Output data of each row
    while($row = $result->fetch_assoc()) {
        echo "ID: " . $row["id"]. " - Name: " . $row["name"]. " - Age: " . $row["age"]. " - Grade: " . $row["grade"]. "<br>";
    }
} else {
    echo "0 results";
}

// Close the connection
$conn->close();
?>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Student Details Form</title>
    <script>
        function validateForm() {
            let name = document.forms["studentForm"]["name"].value;
            let age = document.forms["studentForm"]["age"].value;

            if (name === "" || age === "" || isNaN(age) || age <= 0) {
                alert("Please enter a valid name and age.");
                return false;
            }
            return true;
        }
    </script>
</head>
<body>
    <h2>Student Details</h2>
    <form name="studentForm" action="submit.php" onsubmit="return validateForm()" method="post">
        <input type="text" name="name" placeholder="Name"><br><br>
        <input type="text" name="age" placeholder="Age"><br><br>
        <input type="submit" value="Submit">
    </form>
</body>
</html>


```


Here’s a concise JavaScript example to insert, delete, and update data in an array, all without using HTML:

```javascript
// Initialize an empty array
let studentList = [];

// Insert a new student
function insertStudent(name) {
    studentList.push(name);
    console.log(`${name} has been added. Current list: ${studentList}`);
}

// Delete a student by name
function deleteStudent(name) {
    const index = studentList.indexOf(name);
    if (index > -1) {
        studentList.splice(index, 1);
        console.log(`${name} has been removed. Current list: ${studentList}`);
    } else {
        console.log(`${name} not found.`);
    }
}

// Update a student's name
function updateStudent(oldName, newName) {
    const index = studentList.indexOf(oldName);
    if (index > -1) {
        studentList[index] = newName;
        console.log(`${oldName} has been updated to ${newName}. Current list: ${studentList}`);
    } else {
        console.log(`${oldName} not found.`);
    }
}

// Example usage
insertStudent("John Doe");
insertStudent("Jane Smith");
updateStudent("Jane Smith", "Jane Doe");
deleteStudent("John Doe");
```

A web application architecture is like a blueprint that shows how the different parts of a web app work together. It depends on how the tasks are divided between the client (the user's device) and the server (where the app is hosted).

Technically, it’s like the framework or backbone of the app, including all its pieces like databases, systems, servers, and interfaces, as well as how they communicate with each other. In simpler terms, it explains how the app responds when a user or a server makes a request.

From a business perspective, web application architecture is important for building web apps and making sure they are fast, can handle growth, and are secure.

``` html
<h3>using audio tag</h3>

<audio controls autoplay muted>

<source src="SHIKWA - Talhah Yunus Prod. By Jokhay [music].mp3" type="audio/mpeg">

</audio>

<h3>using video tag</h3>

<video width="420" height="240" controls>

<source src="Basic Topics in Systems Design - Course (1).mp4" type="video/mp4">

</video>
```