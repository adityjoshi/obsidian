sieve of erato 
time complexity - O(N log Log N)
space complexity - O(N)

segmented sieve upper bound ka sqr root -
a) It requires a large amount of memory.
time O n , space - O(sqrt(n))

incremental sieve - works for small range only 

What is the formula for calculating the nth prime number using the Incremental Sieve algorithm?
n* n - n +1 


Sure, here's a detailed overview of the functionalities of a web server and a web client:

### Web Server

A web server is a computer system that hosts websites and delivers web pages to users' browsers upon request. Its main functionalities include:

1. **Handling Requests:**
   - **HTTP/HTTPS Requests:** A web server listens for incoming HTTP/HTTPS requests from clients. When a client requests a web page, the server processes this request and returns the appropriate response.
   - **Request Parsing:** The server parses the request to understand what the client is asking for, including the requested resource, headers, and any data sent by the client.

2. **Content Serving:**
   - **Static Content:** Serves static files such as HTML, CSS, JavaScript, images, and videos stored on the server.
   - **Dynamic Content:** Processes requests for dynamic content, often by running scripts on the server (e.g., PHP, Python, Node.js) and generating HTML on-the-fly based on these scripts.

3. **Security:**
   - **SSL/TLS Encryption:** Provides secure communication over the network by encrypting data using SSL/TLS.
   - **Authentication and Authorization:** Verifies the identity of clients (authentication) and checks their permissions to access resources (authorization).

4. **Resource Management:**
   - **Load Balancing:** Distributes incoming requests across multiple servers to ensure no single server is overwhelmed, improving performance and reliability.
   - **Caching:** Stores copies of frequently requested resources in memory or on disk to reduce response time for subsequent requests.

5. **Logging and Monitoring:**
   - **Access Logs:** Records details about incoming requests, such as the client's IP address, request time, and resource requested.
   - **Error Logs:** Records server-side errors for troubleshooting and improving server performance and reliability.

6. **Session Management:**
   - **Cookies:** Manages user sessions using cookies, allowing the server to maintain state across multiple requests from the same client.
   - **Session Storage:** Stores session data on the server to track user interactions and preferences.

### Web Client

A web client, typically a web browser, is a software application that communicates with web servers to retrieve and display web content. Its main functionalities include:

1. **Requesting Resources:**
   - **HTTP/HTTPS Requests:** Sends HTTP/HTTPS requests to web servers to fetch web pages, images, scripts, and other resources.
   - **Request Headers:** Includes additional information in requests, such as cookies, user-agent string, and preferred languages.

2. **Rendering Content:**
   - **HTML Parsing:** Parses HTML documents and constructs a Document Object Model (DOM) tree to represent the page structure.
   - **CSS Parsing:** Parses CSS files and applies styles to the DOM tree to render the visual appearance of the page.
   - **JavaScript Execution:** Executes JavaScript code to add interactivity, manipulate the DOM, and make asynchronous requests (AJAX) to the server.

3. **User Interaction:**
   - **Event Handling:** Responds to user interactions such as clicks, form submissions, and keyboard inputs by triggering appropriate actions (e.g., submitting data, navigating to a new page).
   - **Forms:** Allows users to input and submit data to the server using HTML forms.

4. **Security:**
   - **SSL/TLS:** Supports secure communication by handling SSL/TLS encryption and certificate verification.
   - **Same-Origin Policy:** Enforces security restrictions on how scripts from one origin can interact with resources from another origin.

5. **Storage:**
   - **Cookies:** Stores small pieces of data from the server to maintain session state and track user preferences.
   - **Local Storage and Session Storage:** Provides mechanisms for storing larger amounts of data locally on the client's device, accessible via JavaScript.

6. **Performance Optimization:**
   - **Caching:** Stores copies of previously fetched resources to improve load times and reduce server load.
   - **Pre-fetching and Pre-loading:** Proactively fetches resources that are likely to be needed soon, based on user behavior and navigation patterns.

7. **Networking:**
   - **DNS Resolution:** Resolves domain names to IP addresses to establish connections with web servers.
   - **Connection Management:** Manages network connections, including handling multiple simultaneous connections and reusing persistent connections to improve performance.

Understanding these functionalities is crucial for web development, as it allows developers to design efficient, secure, and user-friendly web applications.

# Question

Certainly! Here's a detailed comparison of client-side scripting and server-side scripting, along with examples:

### Client-Side Scripting

**Definition:**
Client-side scripting refers to code that is executed on the user's browser rather than on the server. This scripting is primarily used to enhance the user interface and provide interactive features.

**Key Features:**
1. **Execution Location:** Runs on the client's browser.
2. **Performance:** Generally faster because it does not require a round trip to the server.
3. **Interactivity:** Allows for dynamic content updates without reloading the page (e.g., form validation, interactive forms, animations).
4. **Security:** Exposed to the user, making it vulnerable to tampering and security risks.
5. **Languages:** Primarily JavaScript, along with HTML and CSS.

**Examples:**
- **Form Validation:** Using JavaScript to check if a form is filled out correctly before submitting it to the server.
  ```html
  <form onsubmit="return validateForm()">
    <input type="text" id="name" />
    <input type="submit" value="Submit" />
  </form>
  <script>
    function validateForm() {
      var name = document.getElementById("name").value;
      if (name == "") {
        alert("Name must be filled out");
        return false;
      }
      return true;
    }
  </script>
  ```

- **Dynamic Content Update:** Using AJAX to fetch and display new content without refreshing the page.
  ```html
  <button onclick="loadData()">Load Data</button>
  <div id="content"></div>
  <script>
    function loadData() {
      var xhr = new XMLHttpRequest();
      xhr.open("GET", "data.json", true);
      xhr.onload = function() {
        if (xhr.status == 200) {
          document.getElementById("content").innerHTML = xhr.responseText;
        }
      };
      xhr.send();
    }
  </script>
  ```

### Server-Side Scripting

**Definition:**
Server-side scripting refers to code that is executed on the server. It is primarily used to manage data, interact with databases, and generate dynamic web pages before they are sent to the client's browser.

**Key Features:**
1. **Execution Location:** Runs on the server.
2. **Performance:** Slower than client-side for individual interactions due to the need for a round trip to the server.
3. **Interactivity:** Handles data processing, database interactions, and complex logic.
4. **Security:** More secure, as the code is executed on the server and not exposed to the client.
5. **Languages:** PHP, Python, Ruby, Node.js, ASP.NET, Java, etc.

**Examples:**
- **User Authentication:** Validating user credentials against a database.
  ```php
  <?php
  $username = $_POST['username'];
  $password = $_POST['password'];
  $conn = new mysqli("localhost", "user", "password", "database");
  $sql = "SELECT * FROM users WHERE username='$username' AND password='$password'";
  $result = $conn->query($sql);
  if ($result->num_rows > 0) {
    echo "Welcome, " . $username;
  } else {
    echo "Invalid credentials";
  }
  ?>
  ```

- **Dynamic Content Generation:** Displaying data from a database in an HTML table.
  ```php
  <?php
  $conn = new mysqli("localhost", "user", "password", "database");
  $sql = "SELECT * FROM products";
  $result = $conn->query($sql);
  echo "<table>";
  while ($row = $result->fetch_assoc()) {
    echo "<tr><td>" . $row["name"] . "</td><td>" . $row["price"] . "</td></tr>";
  }
  echo "</table>";
  ?>
  ```

### Comparison

| Feature                 | Client-Side Scripting            | Server-Side Scripting             |
|-------------------------|----------------------------------|-----------------------------------|
| **Execution Location**  | Browser                          | Server                            |
| **Languages**           | JavaScript, HTML, CSS            | PHP, Python, Ruby, Node.js, ASP.NET |
| **Speed**               | Faster for individual interactions | Slower due to server round trip  |
| **Interactivity**       | Enhances UI, real-time updates   | Data processing, complex logic    |
| **Security**            | Less secure, code is exposed     | More secure, code is hidden       |
| **Usage Examples**      | Form validation, dynamic content updates | User authentication, database interactions |

### Conclusion

Both client-side and server-side scripting play crucial roles in web development. Client-side scripting is essential for creating responsive and interactive user interfaces, while server-side scripting handles data processing, business logic, and database interactions. Effective web applications often use a combination of both to provide a seamless user experience.

# Question 
URLs (Uniform Resource Locators) provide information necessary to access resources on the web. The components of a URL give details about the location and nature of the resource, as well as the method for accessing it. Here's a breakdown of the information provided by a URL:

### URL Components

1. **Scheme/Protocol**:
   - Indicates the protocol used to access the resource.
   - Common protocols include `http`, `https`, `ftp`, `mailto`, `file`, etc.
   - Example: `https://`

2. **Host/Domain**:
   - Specifies the domain name or IP address of the server hosting the resource.
   - Example: `www.example.com`

3. **Port** (Optional):
   - Specifies the port number to connect to on the server.
   - Default ports: 80 for HTTP, 443 for HTTPS.
   - Example: `:8080`

4. **Path**:
   - Specifies the specific resource within the domain.
   - Example: `/path/to/resource`

5. **Query String** (Optional):
   - Provides additional parameters to pass to the server.
   - Begins with a `?` and includes key-value pairs separated by `&`.
   - Example: `?key1=value1&key2=value2`

6. **Fragment** (Optional):
   - Points to a specific section within the resource.
   - Begins with a `#`.
   - Example: `#section1`

### Example URL

```
https://www.example.com:8080/path/to/resource?key1=value1&key2=value2#section1
```

### Breakdown of Example URL

- **Scheme/Protocol**: `https`
- **Host/Domain**: `www.example.com`
- **Port**: `8080`
- **Path**: `/path/to/resource`
- **Query String**: `key1=value1&key2=value2`
- **Fragment**: `section1`

### Information Provided by Each Component

1. **Scheme/Protocol**:
   - Specifies how the resource should be retrieved (e.g., securely over HTTPS).

2. **Host/Domain**:
   - Identifies the server hosting the resource.

3. **Port**:
   - Specifies the port to use when connecting to the server (if different from the default).

4. **Path**:
   - Directs to the specific resource on the server.

5. **Query String**:
   - Passes additional parameters to the server, often used in web applications for filtering, searching, or providing input data.

6. **Fragment**:
   - Allows for navigation to a specific part of the resource, useful in large documents or web pages.

### Usage in Web Development

- **Web Browsers**: Use URLs to navigate to web pages.
- **APIs**: Use query strings to filter and sort data.
- **Hyperlinks**: Use URLs to link to other resources.
- **File Access**: Use URLs to access files on local or network drives (e.g., `file:///C:/path/to/file`).

By dissecting a URL, you can understand how to access a specific resource, including the server to contact, the path to the resource, any parameters needed for access, and specific sections within the resource.


Here are the SQL queries based on the provided schema:

1. **Select the detail of the employee whose name start with P:**
   ```sql
   SELECT * 
   FROM employee 
   WHERE empname LIKE 'P%';
   ```

2. **How many permanent candidates take a salary more than 5000:**
   ```sql
   SELECT COUNT(*) 
   FROM empsalary 
   WHERE ispermanent = 'YES' AND salary > 5000;
   ```

3. **Select the detail of the employee whose emailId is in Gmail:**
   ```sql
   SELECT * 
   FROM employee 
   WHERE emaildid LIKE '%@gmail.com';
   ```

4. **Select the details of the employee who work either for department E-104 or E-102:**
   ```sql
   SELECT * 
   FROM employee 
   WHERE department IN ('E-104', 'E-102');
   ```

5. **What is the department name for DeptID E-102:**
   ```sql
   SELECT deptname 
   FROM empdept 
   WHERE deptid = 'E-102';
   ```

6. **What is the total salary that is paid to permanent employees:**
   ```sql
   SELECT SUM(salary) 
   FROM empsalary 
   WHERE ispermanent = 'YES';
   ```

7. **List name of all employees whose name ends with 'a':**
   ```sql
   SELECT empname 
   FROM employee 
   WHERE empname LIKE '%a';
   ```

8. **List the number of departments of employees in each project:**
   ```sql
   SELECT ep.projectid, COUNT(DISTINCT e.department) AS num_departments
   FROM empproject ep
   JOIN employee e ON ep.empid = e.empid
   GROUP BY ep.projectid;
   ```

9. **How many projects started in the year 2010:**
   ```sql
   SELECT COUNT(*) 
   FROM empproject 
   WHERE startyear = 2010;
   ```

These queries are based on the provided schema and the given requirements. If there are any additional details or constraints, further refinement of the queries may be necessary.

Here are the SQL queries for the additional statements:

10. **How many projects started and finished in the same year:**
   ```sql
   SELECT COUNT(*)
   FROM empproject
   WHERE startyear = endyear;
   ```

11. **Select the name of the employee whose name's 3rd character is 'h':**
   ```sql
   SELECT empname
   FROM employee
   WHERE SUBSTR(empname, 3, 1) = 'h';
   ```

12. **Select the department name of the company which is assigned to the employee whose employee id is greater than 103:**
   ```sql
   SELECT DISTINCT d.deptname
   FROM employee e
   JOIN empdept d ON e.department = d.deptid
   WHERE e.empid > 103;
   ```

13. **Select the name of the employee who is working under Abhishek:**
   ```sql
   SELECT e.empname
   FROM employee e
   JOIN employee h ON e.empheadid = h.empid
   WHERE h.empname = 'Abhishek';
   ```

14. **Select the name of the employee who is department head of HR:**
   ```sql
   SELECT e.empname
   FROM employee e
   JOIN empdept d ON e.empid = d.depthead
   WHERE d.deptname = 'HR';
   ```

15. **Select the name and email of the Dept Head who is not permanent:**
   ```sql
   SELECT e.empname, e.emaildid
   FROM employee e
   JOIN empdept d ON e.empid = d.depthead
   JOIN empsalary s ON e.empid = s.empid
   WHERE s.ispermanent = 'NO';
   ```

These queries are crafted based on the schema provided and the requirements stated. If there are specific naming conventions or additional constraints, they can be adjusted accordingly.