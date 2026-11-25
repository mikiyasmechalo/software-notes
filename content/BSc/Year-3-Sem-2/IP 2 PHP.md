---
title: Internet Programming 2 (PHP)
---
# CH 1: Introduction to Server-Side Development

## Understanding Backend Development
B.D is the foundation of web applications, focusing on the logic, database, and server operations that run behind the scenes. It involves building the server-side of an application responsible for handling requests from the frontend and returning the necessary data efficiently.

Backend developers manage databases, create and optimize application logic, design APIs, and configure server architecture.
Establishing seamless communication between the frontend and the database, enabling the application to perform essential operations.

Popular languages for Backend include PHP (with Laravel), JavaScript (with Node.js), Python (with Django), and Java (with Spring).

Optimizing database queries, implementing caching mechanisms, and structuring APIs properly are crucial for maintaining speed and reliability.

## Client-Server Architecture
A computing model in which multiple clients request and receive services from a centralized server.

This model ensures that resources and data processing are efficiently managed, allowing multiple users to interact with a system simultaneously.

It is widely used in various applications, such as web browsing, mobile applications, cloud computing, and enterprise solutions. It provides scalability, security, and centralized control over data and resources.

#### Components
**Client**
A user interface that facilitates interaction with a system, sending requests to a server via web technologies like HTML, CSS, and JavaScript. it handles user inputs and dynamically updating content.
Frameworks such as Angular, React, and Vue.js improve responsiveness and usability across various devices.

e.g. Each action in an e-commerce website triggers an HTTP request to the server, which processes the request and returns relevant data. The frontend then updates in real time seamlessly.

**Server**
a backend system that processes requests from clients and sends responses, handling application logic, authentication, and authorization.

They can be built using various technologies such as PHP, Node.js, Python, or Java, and often interact with databases to retrieve and store information.

For example, in a PHP-based web server, Apache receives a request from a user's browser and passes it to a PHP interpreter, which processes the request, interacts with a database if needed, and generates an HTML response. In a Node.js environment, the server directly handles requests using its built-in HTTP module, processing them asynchronously and sending responses efficiently without relying on a separate interpreter.

**Database**
A structured system for storing and managing data that the server retrieves and manipulates based on client requests. NoSQL databases like MongoDB and Firebase, store data in flexible formats such as documents or key-value pairs.

Databases Ensure data integrity, security, and efficient access.

**Network**
Enables communication between clients and servers using HTTP/HTTPS protocols for communication over the internet.

Relies on hardware such as routers, switches and cloud services to ensure efficient routing & connectivity.

Security measures like SSL/TLS encryption protect sensitive information during transmission, preventing unauthorized access and ensuring data integrity.

**Workflow** 
1. **Client Request**: client sends an HTTP/S request, requesting a webpage, data, or service.
2. **Server Processing**: The server processes the request, executes backend logic, and interacts with the database if necessary.
3. **Database**: If required, the server fetches, updates, or deletes data from the database.
4. **Response Generation**: The server constructs an appropriate response (HTML, JSON, XML) and sends it back to the client.
5. **Client Rendering**: The client receives the response and renders the data accordingly for user interaction.

On Client: DNS Look Up -> DNS IP response -> TCP/IP connection -> HTTP Request -> HTTP Response

**Advantages of Client-Server Architecture** 
- Multiple clients simultaneously
- Centralized authentication and authorization
- Efficient data storage and retrieval through dedicated DB servers
- Allow use of shared resources without redundancy/ duplication.

## Role of a Backend Developer
Backend development refers to the creation and maintenance of server-side logic that powers applications. The backend handles business rules, user authentication, database operations, and server interactions.

It enables functionalities such as user login systems, payment gateways, real-time notifications, and API interactions.

Backend developers focus on optimizing server performance, enhancing security, and ensuring efficient data handling to support high-traffic applications.

#### Key Responsibilities
- Handling Business Logic and Application Workflows: how an application operates, including calculations, automation, and decision-making.
- Managing Databases and Data Processing: Storing, retrieving, and modifying data efficiently.
- Authenticating Users and Securing Data: authentication and data encryption to prevent unauthorized access.
- Ensuring Application Scalability and Reliability: ensuring smooth uptime with failover strategies.
- Serving Dynamic Content Based on User Requests: Processing user inputs and returning relevant content in various formats, such as HTML, JSON, or XML.

**Backend vs. Frontend**

| Feature       | Frontend (Client-Side)                | Backend (Server-Side)                                |
| ------------- | ------------------------------------- | ---------------------------------------------------- |
| Language      | HTML, CSS, JavaScript                 | PHP, Python, Node.js, Java                           |
| Role          | UI/UX design, interaction             | Logic, database management, authentication           |
| Runs On       | Browser, user’s device                | Web server, cloud services                           |
| Primary Focus | User experience, styling, interaction | Data processing, server response, security           |
| Frameworks    | React, Angular, Vue.js                | Laravel, Django, Express.js, Spring Boot, `ASP.Net`. |

## Comparison of Server-Side Languages

| Language | Features                                                                                                                                        |
| -------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| PHP      | Easy to integrate with databases, widely used in web development (WordPress, Laravel). Frameworks: Laravel, CodeIgniter, Symfony orks: Laravel, |
| Python   | Clean syntax, powerful frameworks (Django, Flask), used in AI, automation, and data science.                                                    |
| Node.js  | JavaScript-based, handles asynchronous requests efficiently, ideal for APIs and real-time applications.                                         |
| Java     | Highly secure, scalable, and widely used in enterprise and banking applications.                                                                |
| Ruby     | Known for developer-friendly syntax and rapid development with Ruby on Rails.                                                                   |
| C#       | Cross-platform support and rich libraries, mainly used for ASP.NET applications.                                                                |

![[Pasted image 20250225231015.png]]
![[Pasted image 20250225231030.png]]

**Choosing the Right Language** 
Here are some guidelines:
- For CMS and traditional web development → PHP (e.g., WordPress, Drupal, Joomla). 
- For data-heavy applications, AI, and automation → Python (e.g., AI-driven applications, scientific computing). 
- For real-time applications (e.g., chat apps, streaming services, IoT) → Node.js. 
- For large-scale enterprise applications and banking systems → Java. 
- For startups and rapid development → Ruby (e.g., small business applications, prototyping)

## Web Servers
In Client Server Arch., a server processes client requests and delivers web pages or data to users. It is responsible for handling HTTP/HTTPS requests, processing them, and responding with the appropriate content.

They enable users to access websites and web applications over the internet or an intranet.

They can serve static files directly or act as intermediaries that forward requests to backend applications for further processing.
Additionally, web servers often include features such as load balancing, caching, and access control mechanisms to optimize web performance and security.

**Popular Web Servers** 

| Server      | Description                                                                                                                                               |
| ----------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Apache      | Open-source, supports PHP, widely used in shared hosting environments. Offers modular architecture and extensive customization options.                   |
| Nginx       | High-performance, event-driven architecture that efficiently handles concurrent requests. Ideal for high-traffic websites and reverse proxy applications. |
| `LiteSpeed` | Optimized for speed and security, providing an alternative to Apache with better performance in handling large-scale traffic.                             |
| Tomcat      | Specialized for running Java-based applications, commonly used in enterprise environments and web services.                                               |

#### How a Web Server Works
It follows a structured process to handle client requests and deliver responses:
1. **Client Request**: an HTTP or HTTPS request to the web server, specifying the required resource (e.g., a webpage, image, or API response).
2. **Request Processing**: If it is a static file (HTML, CSS, JavaScript), it serves the file directly. If it requires dynamic processing, it forwards it to the backend application (e.g., PHP, Python, Node.js, or Java). 
3. **Backend Communication (if required):** If the request requires interaction with a database or additional processing, the web server communicates with the backend application or database server.
4. **Response Generation**: The requested resource or generated content is packaged into an HTTP response and sent back to the client.
5. **Client Rendering**: The client (browser) receives the response and displays the content accordingly, enabling user interaction

#### Features of a Web Server
They can serve both static and dynamic content.
To enhance performance and availability, many also implement load balancing, distributing incoming traffic across multiple servers to prevent overloads and ensure smooth operation.

- **SSL/TLS encryptions**, authentication protocols and firewall rules to protect sensitive data.
- **Logging and monitoring** : allow us to track requests, errors and performance metrics.
- **Caching** to enhance speed and efficiency. by reducing strain on the server.
- **Virtual hosting**, allowing multiple websites to be hosted on the seme server. while maintaining separate configurations, security settings, and resources.
- **Compression** algorithms like `Gzip` or `Brotli`. It improves load speeds & bandwidth usage.
- **Proxy functionality**, forwarding client requests to backend servers and returning responses. This improves security by hiding the backend infrastructure, enables load balancing, and enhances performance through features like SSL termination and caching.
- **HTTP/2 and HTTP/3 support** allows web servers to handle requests more efficiently with multiplexing, reduced latency, and better connection management.
- **Rate limiting** and **request throttling** to protect against DDoS attacks and abusive traffic. restricting the number of requests from a single IP address.

### Security Considerations and Performance Optimization
#### Security Considerations
Proper authentication, authorization, and input validation techniques help defend against common vulnerabilities.

**Authentication & Authorization**
Authentication - identity, Authorization - level of access. Implementations include:-

- **Username and Password-based authentication:** web servers store passwords using strong hashing algorithms like `bcrypt` or `Argon2`
- **Multi-factor authentication (MFA):** This can include OTPs sent via email or SMS, biometric authentication, or hardware security keys
- **Role-based access control (RBAC):** assigning roles/ level of access based on responsibilities within a system.  
- **OAuth and JSON Web Tokens(JWT):** widely used authentication methods for secure API access. 
	- OAuth allows users to log in via third-party providers like Google or Facebook without exposing credentials, while JWT enables stateless authentication by securely transmitting user information between the client and server in a compact, encrypted format.


**SQL Injection Prevention**
SQL injection exploits vulnerabilities in database queries by injecting malicious SQL statements.
Protection measures include:

- **Prepared statements:** use parameterized queries to prevent SQL injection attacks by ensuring user inputs are treated as data rather than executable code.
- **Input validation:** rules such as character limits, data types, and regular expressions.
- **Least privilege principle**: limits database access rights, ensuring users and applications have only the permissions necessary to perform their tasks.
- **Web Application Firewalls (WAFs)**: monitor and filter HTTP traffic to detect and block potential threats. protect from XSS, SQL injection and DoS attacks by analyzing requests in real time.
- **Escaping user input**: ensures that special characters in user-provided data are treated as plain text rather than executable SQL code.
 

**Cross-Site Scripting (XSS)**
Occur when attackers inject malicious scripts into web applications, executed in users’ browsers.
Prevention methods include:

- **Input Sanitization**: ensuring that user-provided data is properly filtered and escaped before being rendered on a webpage.
- **Content Security Policy (CSP)**: by restricting the execution of inline scripts and controlling which external sources can load scripts, styles, and other resources. This works even if an attacker successfully bypasses input sanitization measures.
- **HTTP-only and secure cookies**: preventing JavaScript from accessing cookies, reducing the risk of session hijacking. Marking cookies as "Secure" ensures they are only transmitted over encrypted HTTPS connections, preventing exposure to attackers intercepting network traffic.
- **Framework security features**: Modern frameworks like Django, Angular, and React include automatic output escaping and input validation, making it easier to prevent malicious script execution.


#### Performance Optimizations
To enhance UX and reduce server load, Key strategies include caching, load balancing, and asynchronous processing.

**Caching Strategies**
It improve speed and efficiency by storing frequently accessed data.

- **Client-side caching**: storing static assets such as CSS, JavaScript, and images in the user's browser for faster load times.
- **Server-side caching**: uses tools like *Redis or Memcached* to store database query results and precomputed/ Dynamic responses. Reduce processing time and handle higher traffic efficiently.
- **Content Delivery Networks (CDNs)**: distributing cached resources across multiple servers worldwide. improving load times and reducing latency.
- **Object caching**: stores frequently used data structures in memory, reducing the need for redundant computations. useful for applications that repeatedly process the same complex calculations or API responses.
- **Page caching**: saves entire rendered web pages to serve them quickly without regenerating content for each request. Especially effective for high-traffic websites with mostly static content.
- **Database query caching**: stores the results of common queries. This speeds up database operations and decreases load on database servers.
- **Opcode caching**: improves performance by storing compiled PHP or other interpreted code in memory, eliminating the need for scripts to be recompiled on every request. Tools like `Opcache`.

**Load Balancing** 
distributing incoming traffic across multiple servers, preventing overloads and ensuring smooth performance. help maintain application stability and responsiveness, especially in high traffic.

- **Round Robin:** a simple method that sequentially assigns requests to servers in a rotating order. Ensuring even distribution of traffic but does not account for server load variations.
- **Least Connections:** directs requests to the server with the fewest active connections. Particularly effective for applications with varying request durations, ensuring no single server becomes overloaded.
- **Application-level load balancing:** leverages reverse proxies like `Nginx` or `HAProxy` to intelligently route requests based on factors such as server health, traffic load, and response times. Also additional features like caching, SSL termination, and security enhancements.

**Asynchronous Processing**
Improves efficiency by handling multiple requests simultaneously, preventing performance bottlenecks and ensuring smooth application execution.

- **Event-driven architecture**: leverages frameworks like Node.js to manage non-blocking operations. By using an event loop and asynchronous callbacks, applications can handle multiple I/O operations, such as database queries and API requests.
- **Message queues**: facilitate background task processing by asynchronously handling workloads with systems like RabbitMQ or Kafka. Offload time-consuming tasks, such as email notifications or data processing, ensuring that critical requests are not delayed.
- **Worker threads**: utilizing multithreading capabilities. Useful for CPU-intensive operations, allowing applications to perform complex calculations without impacting responsiveness.
- **Promises and Async/Await**: simplify handling asynchronous operations in JavaScript by avoiding callback hell. Promises represent a future value, while async/await syntax makes asynchronous code more readable and easier to manage, especially when dealing with multiple dependent operations.
- **`WebSockets`**: provide real-time, full-duplex communication between clients and servers. Unlike  HTTP's request-response pattern, `WebSockets` maintain an open connection, allowing instant data transmission for applications like chat apps, live notifications, and financial dashboards.
- **Batch Processing**: groups and executes multiple tasks together asynchronously at scheduled intervals. Useful for handling large data operations, such as generating reports or processing bulk transactions.
- **Serverless Functions (`FaaS`)**:, such as AWS Lambda, execute asynchronous tasks in response to specific triggers. These functions run independently in a cloud environment, automatically scaling based on demand while reducing infrastructure management overhead. 
- **Deferred Execution**: schedules background tasks to run later, often using job scheduling libraries like `Celery` for Python or `Sidekiq` for Ruby.


## Future Trends in Server-Side Development
**Serverless Computing** 
A cloud computing execution model where developers can run applications without provisioning or managing servers. Cloud providers handle infrastructure, scaling, and maintenance.
- main benefit is dynamic scalability. w/c enhances efficiency particularly for event driven apps.
- Disadvantages: 
	1. Cold start delays: invoking a function after a period of inactivity.
	2. Possible Vendor Lock-ins making migration difficult.
- Examples: AWS Lambda, GC Functions, Azure Functions.

**Microservices Architecture** 
It structures applications as a collection of small, independent services, each responsible for a specific function. unlike traditional where the entire app is a single entity.

- it promotes modularity, flexibility, and scalability
- A major benefit of microservices is their ability to scale independently. for better Resource utilization.
- flexible to use d/t programming languages and frameworks for different services w/c suit them.
- Complexities: managing inter-service communication, monitoring, and security.
- Tools such as Docker and Kubernetes simplify deployment and management of microservices, ensuring seamless coordination among distributed services.
- Adoption is prevalent in large-scale applications such as streaming services, banking systems, and healthcare platforms. These require modular architectures that can evolve and scale over time without disrupting core functionalities.

**AI-Powered Backends** 
Enabling applications to analyze data, make predictions, and automate decision-making processes., enhancing automation and efficiency. e.g.
- Real-time Fraud detection systems in banking
AI-driven personalization enhances user experience by tailoring content to individual users.
Another critical area is predictive maintenance.

Frameworks like `TensorFlow`, `PyTorch`, and `OpenAI GPT` APIs facilitate AI model deployment in backend systems. with capabilities like NLP, Image recognition and real-time analytics.


# CH 2: PHP
## What is PHP?
PHP stands for "Hypertext Preprocessor" and is a server-side language.
PHP files can contain text, HTML tags and scripts.
PHP files are returned to the browser as plain HTML and it has a file extension of `".php"`, `".php3"`, or `".phtml"`.

**Why PHP?** 
- Accessibility: You can reach the internet from any browser, any device, anytime, anywhere.
- Manageability: It does not require distribution of application code and it is easy to change code.
- Security: The source code is not exposed. Once user is authenticated, can only allow certain actions. It also allows encryption.
- Scalability: Web-based 3-tier architecture can scale out.

#### Characteristics of PHP
- Versatile File Structure: mix of HTML, CSS, JS and PHP
- Dynamic Content Generation
- Database Connectivity
- User Authentication and role-based Access Control
- File Handling Capabilities: built-in functions for reading, writing, modifying and deleting
- Cross-Platform Compatibility
- Dynamic Typing and Flexibility
- Security Features - built-in encryption, data validation, session management, and protection against SQL injection and XSS attacks.
- Fast and Efficient
- Active Community and Documentation - open-source


## PHP Basic Syntax
`<?php echo "Hello" ?>` - recommended for maximum compatibility
`<? echo "Hello" ?>`
`<% echo "Hello" %>` 
```html
<script language="PHP">
    // Your PHP code here
</script>
```
Each code line in PHP must end with a semicolon.


**PHP Output Statement**
*echo and print* 
echo has no return value whereas print has a return value {true if succeeded}.
echo can take multiple parameters (although such usage is rare) but print can only take one argument. `echo outputitem1,outputitem2,outputitem3, ...;`
echo is marginally faster than print.

**Multi-lines printing:**
```php
<?php
	# First Example, "END" can be anything
	print <<<END
		This uses the "here document" syntax to output multiple lines with
		$variable interpolation. Note that the here document terminator must 
		appear on a line with just a semicolon no extra whitespace!
		END;
	# Second Example
	print "This spans multiple lines. The newlines will be
		output as well";
?>
```


**Variables**
```php
$pi= 3.14;
$version=1.12;
$my_var = NULL;
$string_1 = "This is a string in double quotes";
```

PHP provides a large number of predefined variables to all scripts. called `Superglobals`.

```php
//Superglobals - Superglobals are built-in variables that are always available in all scopes
$_GLOBALS // References all variables available in global scope
$_SERVER // Server and execution environment information
$_GET // HTTP GET variables
$_POST // HTTP POST variables
$_FILES // HTTP File Upload variables
$_REQUEST // HTTP Request variables, and can replace $_POST, $_GET and $_COOKIE variables
$_SESSION // Session variables
$_COOKIE // HTTP Cookies
$php_errormsg //The previous error message
$HTTP_RAW_POST_DATA // Raw POST data
$http_response_header // HTTP response headers
$argc // The number of arguments passed to script
$argv // Array of arguments passed to script
```

Removing Variables
We can uncreated the variable by using this statement: `unset(VariableName);`

How PHP Works
1. User Request
2. Server Processing
3. PHP Script Execution (data from database, user input, logical operations, dynamic content)
4. HTML Output Generation
5. Client-Side Display

**PHP Data Types** 
- String, Integer, Float, Boolean, Array, Object, NULL, 
- Resource - A special type that holds references to external resources such as database connections.

PHP Constants
- `define("SITE_NAME", "MyWebsite");` 

**Variable Scope:** 
- Local variables 
- Function parameters
- Global variables 
- Static variables 

Global variables: 
- can be accessed in any part of the program.
- However, in order to be modified, a global variable must be explicitly declared to be global in the function in which it is to be modified.
```php
<?php
$somevar = 15;
function addit() {
	GLOBAL $somevar;
	$somevar++;
	print "Somevar is $somevar";
}
addit();
?>
```

**Static Variables**
a static variable will not lose its value when the function exits and will still hold that value should the function be called again.

```php
function keep_track() {
	STATIC $count = 0;
	$count++;
	print $count; 
	print " "; 
} 
keep_track();
keep_track();
keep_track();
```


**Work with constants**
To define a constant you have to use define() function and to retrieve the value of a constant, you have to simply specifying its name.
can also use the function constant() to read a constant's value if you wish to obtain the constant's name dynamically.
```php
<?php
define("MINSIZE", 50);
echo MINSIZE;
echo constant("MINSIZE"); // same thing as the previous line
?>
```

Only scalar data (Boolean, integer, float and string) can be contained in constants.
- Constants may be defined and accessed anywhere without regard to variable scoping rules.


**Manipulate Numbers**
PHP breaks numbers down into two groups: integers and floating-point numbers.
Conversion between the two is done automatically, so 3/2 = 1.5 not 1.
PHP also automatically converts from strings to numbers and back. For instance, 1+"1" is 2.

```php
<?php
// Checking validity
if (is_numeric('five')) { /* false */ }
if (is_numeric('5')) { /* true */ }
// Rounding
round(2.4); // Round to nearest integer
ceil(2.4);  // Round up
floor(2.4); // Round down

foreach (range($start, $end) as $i) { // Generating a range
    // Loop through range from $start to $end
}
// Random numbers
$random_number = mt_rand($lower, $upper); // Generate random number in between
// Exponents
exp(2);         // Raise e to the power of 2
pow(2, 10);     // Raise 2 to the power of 10 (results in 1024)
// Formatting numbers
print number_format(1234.56);      // Prints 1,234
print number_format(1234.56, 2);  // Prints 1,234.56
?>
```


#### **Manipulate Strings**
- Concatenation -> using (`.`) e.g. `echo $string1 . " " . $string2;`
- `Substr()` -> Syntax: `variable = substr(string, start [, length ]);` 
```php
$name = "Fred Flintstone"; 
$fluff = substr($name, 6, 4);// $fluff is "lint" i.e copy strings from 6th about 4 
							// chars consecutively 
$sound = substr($name, 11); // $sound is "tone"
```

- `substr_count()`:- uses to count how many times a smaller string occurs in a larger one.
	- `$number = substr_count(big_string, small_string);` -> returns int
- `substr_replace()`:- syntax 
	- `$string = substr_replace(original_string, new_string, start [, length ]);`
	- start is the index of the first character that we need to replace.
	- The length parameter uses to indicate how many characters we need to replace from original characters.
```php
$greeting = "good morning citizen";
$farewell = substr_replace($greeting, "bye", 5, 7);
// $farewell is "good bye citizen"
$well = substr_replace($farewell, "now it's time to say ", 0, 0);
// now it is time to say goodbye
```
	- Use a length value of 0 to insert without deleting the original strings
	- Use a replacement of "" to delete without inserting
	- negative start value to start from the back
- `strrev()` function:- takes a string and returns a reversed copy of it.
- `str_repeat()` - takes a string and a count and returns argument string repeated count times.
	- `echo str_repeat('-', 40);` // for a horizontal rule
- `str_pad()` - pads one string with another i.e. left blank space.
	- `$padded = str_pad(to_pad, length [, with [, pad_type ]]);`
```php
$string = str_pad('Fred Flintstone', 30); // default is pad right
echo "$string:35:Wilma"; 
// Fred Flintstone            :35:Wilma
``` 
	- The optional third argument is the string to pad with
	- $string = str_pad('Fred Flintstone', 30, '. ');
	- The optional fourth argument can be either STR_PAD_RIGHT (the default), STR_PAD_LEFT, or STR_PAD_BOTH (to center).

```php
strpos() //-> bool: to search for a string or character within a string
strrpos() //-> returns a position
strstr() and strchr() // -> return the string they find
strspn() and strcspn()  //-> return how much of the start of the string matches a mask
strstr()  //-> finds the first occurrence of a small string in a larger string and returns from that small string on
strrpos(), strrchr()  //-> searches backward in the string, but only for a character, not for an entire string
strlen()  //-> length of a string
```


# Unit 3: PHP Forms and Statements
## PHP Forms
Any form element will automatically be available to your PHP scripts.
```html
<form action='url to submit the form filled' method='get' or 'post'>
	<!–- form contents -->
</form>
```
If the method is `GET` the data is passed in the `url` string, if the method is `POST` it is passed as a separate file.
The form variables are available to PHP in the page to which they have been submitted.
The variables are available in three `superglobal` arrays created by PHP called `$_POST`, `$_GET` and `$_REQUEST`.
- GET can't be used to send binary data, like images or word documents, to the server because GET method sends the encoded user information. 
- The data sent by GET method can be accessed using QUERY_STRING environment variable.

```php
<?php
if( $_GET["name"] || $_GET["age"] )	{
	echo "Welcome ". $_GET['name']. "<br />";
	echo "You are ". $_GET['age']. " years old.";
	exit();
}?>
<html><body>
	<form action="<?php $_PHP_SELF ?>" method="GET">
		Name: <input type="text" name="name" />
		Age: <input type="text" name="age" />
		<input type="submit" />
</form></body></html>
```
The above code’s action attribute value can be represented as the filename itself like:-
`<form action="info.php" method="GET">` 

##### The POST Method:
The POST method transfers information via HTTPs headers. The information is encoded as described in case of GET method and put into a header called QUERY_STRING.
- no size limit
- more secure
- ASCII as well as binary data.
- `$_POST` associative array to access all the information sent using POST method.

##### The `$_REQUEST` variable
`$_REQUEST` contains the contents of ` $_GET`, `$_POST`, and `$_COOKIE` variables
```php
<?php // welcome.php
	echo "Welcome to the homepage";
?>
```
```php
<html><body>
	<form action="" method="post">
		Username: <input type="text" name="username"><br>
		Password: <input type="password" name="password"><br>
		<input type="submit" value="Login">
	</form>
</body></html>
<?php // other.php
	$una="abc";
	$pwd="abc1234";
	$username=$_REQUEST['username'];
	$password=$_REQUEST['password'];
	if($username==$una&&$password==$pwd)
		header("location:welcome.php");
	else
		echo "Please enter valid username/password";
?>
```
The PHP header() function supplies raw HTTP headers to the browser and can be used to redirect it to another location.

### The foreach loop Statement
```php
foreach (array as value) {
	// code to be executed;
}
$array = array( 1, 2, 3, 4, 5 );
echo "Values of the array:";
foreach( $array as $value ) echo "$value ";
?>
```

### Arrays
- Numeric array - An array with a numeric index. Values are stored and accessed in linear fashion 
- Associative array - An array where each ID key is associated with a value
- Multidimensional array - An array containing one or more arrays and values are accessed using multiple indices

```php
$numbers = array( 1, 2, 3, 4, 5 ); // Numeric Arrays - regular arrays
// Associative Arrays - a string index (avoid double quotes when printing )
$credit_hour = array("AIP"=>3, "AP"=>3, "DCN"=>4, "CMT"=>4, "EDP"=>4); 
$grade= array("Abebe"=>array("AIP"=>'A',"AP"=>'B'),"Ermias"=>array("AIP"=>'B', "AP"=>'C')); // MD arrays - each element in the array can be an array and so on
```

**Adding and Removing Array Elements** 
```php
$movies = array('The Lion King', 'Cars', 'A Bug\'s Life');
array_shift($movies); // remove element from beginning of array
array_pop($movies); // remove element from end of array
array_push($movies, 'Ratatouille'); // add element to end of array
array_unshift($movies, 'The Incredibles'); // add element to beginning of array
print_r($movies); // print array
// output: ('The Incredibles', 'Cars', 'Ratatouille')
```
These functions should be used only with numerically indexed arrays and not with associative arrays.

**Sorting Arrays** 
- `sort()` -  to sort numerically indexed arrays alphabetically or numerically, from lowest to highest value. numeric and alphabetical order. 
- `rsort()` : sorts the elements in the reverse order. %%Reverse Sort %%
- `asort()` : sorts the elements in the array without changing the indices. %%As is Sort %%
- `ksort()` : sorts the arrays by key. %%Key Sort %%
```php
$data = array(15,81,14,74,2); // changed to Associative array to indicies
asort($data);
print_r($data);// Array ( [4] => 2 [2] => 14 [0] => 15 [3] => 74 [1] => 81 )
echo "<br/>";
ksort($data); //array has numeric keys (0, 1, 2, 3, 4), which are already in ascending order.
print_r($data);// Array ( [0] => 15 [1] => 81 [2] => 14 [3] => 74 [4] => 2 )
echo "<br/>";
sort($data);
print_r($data);// Array ( [0] => 2 [1] => 14 [2] => 15 [3] => 74 [4] => 81 )
```

**PHP Functions**
- Functions MUST be defined before they called.
- Unlike variables, function names are not case sensitive `(foo(…) == Foo(…) == FoO(…))`
```php
function writeMessage() {
	echo "You are really a nice person, Have a nice time!";
}
writeMessage();
// Other examples
function writeMessage($a, $b) {/*...*/} // pass by value
function writeMessage(&$a, &$b) {/*...*/} // pass by reference
function writeMessage($a=1, $b=2) {/*...*/} // default values
```

**Dynamic Function Calls**: It is possible to assign function names as strings to variables and then treat these variables exactly as the function name itself.
```php
function sayHello()
	echo "Hello<br />";
$function_holder = "sayHello";
$function_holder();
```


### Files

When a user uploads a file using an HTML form with `enctype="multipart/form-data"`, PHP stores information about the uploaded file in the `$_FILES` `superglobal` array. This array contains:

| Key                           | Description                                 |
| ----------------------------- | ------------------------------------------- |
| `$_FILES['file']['name'] `    | Original filename                           |
| `$_FILES['file']['type']`     | MIME type of the file                       |
| `$_FILES['file']['tmp_name']` | Temporary location where the file is stored |
| `$_FILES['file']['error']`    | Error code associated with the upload       |
| `$_FILES['file']['size']`     | Size of the uploaded file (in bytes)        |
**Uploading Files Using `move_uploaded_file()`** 
To store an uploaded file permanently, use the `move_uploaded_file()` function, which moves the file from its temporary location to a specified directory.

```php
if ($_SERVER['REQUEST_METHOD'] == 'POST' && isset($_FILES['file'])) {
	$uploadDir = 'uploads/';
	$uploadFile = $uploadDir . basename($_FILES['file']['name']);

	if (move_uploaded_file($_FILES['file']['tmp_name'], $uploadFile)) {
		echo "File uploaded successfully.";
	} else { echo "File upload failed."; } }
```

**Setting File Restrictions** 
*Allowed File Types*: Restrict uploads to specific file types using MIME types or file extensions.
```php
$allowedTypes = ['image/jpeg', 'image/png', 'image/gif'];
if (!in_array($_FILES['file']['type'], $allowedTypes)) { exit; }
```
*Maximum File Size*: Limit file size to prevent large uploads
```php
$maxSize = 2 * 1024 * 1024; // 2MB
if ($_FILES['file']['size'] > $maxSize) { exit; }
```
*Preventing Malicious Uploads*: To prevent malicious file uploads, store files outside the web root, rename files to avoid executing scripts, and verify file content using `finfo_file()`.
```php
$finfo = finfo_open(FILEINFO_MIME_TYPE);
$mimeType = finfo_file($finfo, $_FILES['file']['tmp_name']);
if (!in_array($mimeType, $allowedTypes)) {
 echo "Potentially dangerous file detected."; exit; }
finfo_close($finfo);
```

### Regular expressions 
Regular expressions (regex) are powerful tools for pattern matching and manipulation in strings.
They can be used for validation, searching, and replacing text. Regular expressions are a versatile tool for string manipulation and validation.
**Metacharacters**: Special characters that have specific meanings in regex

| Character | Meaning                                       |
| --------- | --------------------------------------------- |
| $.$       | Matches any single character (except newline) |
| $*$       | Matches zero or more occurrences              |
| $+$       | Matches one or more occurrences               |
| $?$       | Matches zero or one occurrence                |
| $[~]$     | Character sets                                |
| ^         | Start of string                               |
| $\$$      | End of string                                 |
| \         | Escape character                              |
**Character Classes**: Define sets of characters to match

| Classes   | Meaning                              |
| --------- | ------------------------------------ |
| $[a-z]$   | Matches any lowercase letter         |
| $[0-9]$   | Matches any digit                    |
| \[^a- z\] | Matches any character not in the set |
**Predefined character classes**:

| Class | Meaning                                       |
| ----- | --------------------------------------------- |
| \d    | Digits                                        |
| \D    | non-Digits                                    |
| \w    | Word characters (letters, digits, underscore) |
| \W    | Non-word characters                           |
| \s    | Whitespace                                    |
| \S    | Non-whitespace                                |
**Quantifiers**: Specify how many times a character or group should occur.

| Quantifier | Meaning               |
| ---------- | --------------------- |
| $\{n\}$    | Exactly n times       |
| $\{n,\}$   | n or more times       |
| $\{n,m\}$  | Between n and m times |
**Modifiers (Flags)**: Modify the behavior of the regex.

| Flag | Meaning                       |
| ---- | ----------------------------- |
| i    | Case-insensitive              |
| m    | Multiline                     |
| s    | Dotall (dot matches newlines) |
| u    | UTF-8                         |
Common uses :

##### Form Validation
Browser validation is faster and reduces the server load. You should consider server validation if the user input will be inserted into a database. 
A good way to validate a form on the server is to post the form to itself, instead of jumping to a different page. The user will then get the error messages on the same page as the form.

`preg_match()` :
**Syntax**: `int preg_match(string $pattern, string $subject, array &$matches = null)` 
`$matches` (optional): If provided, this variable will be filled with the matches found in the subject string.
**Common Validations** 
```php
if(!isset($value)||empty($value)) {} // Presence Validation
if(strlen($password)<$min||strlen($password)>$max) {} // String Length
if(!is_numeric($value)) {} // Type Validation
if(!in_array($value, $set)) {} // Inclusion in Set Validation
if(in_array($username, $usernamefromdb)) {} // Uniqueness Validation
if(!preg_match($regexp, $subject)) {} // REGEX Validation
if(!preg_match("/^[.0-9]*$/", $value)) {} // Digits 0-9 only Validation
if(!preg_match("/^[a-zA-Z]*$/", $value)) {} // Letters only Validation
if(!filter_var($value, FILTER_VALIDATE_EMAIL)) {} // E-mail Address Validation
if(!preg_match("/\b(?:(?:https?|ftp):\/\/|www\.)[-a-z0-9+&@#\/%?=~_|!:,.;]*[-a-z0-9+&@#\/%=~_|]/i", $value)) {} // URL Address Validation
```



# CH-4: PHP-MySQL INTEGRATION

## 4.1. Connecting PHP with MySQL
PHP provides two primary ways to interact with MySQL databases: `MySQLi` (MySQL Improved) and PDO (PHP Data Objects).

| `MySQLi`                     | PDO (PHP Data Objects)                                                                                                     |
| ---------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| Only MySQL                   | Supports multiple databases (MySQL, PostgreSQL, SQLite, etc.) More flexible (switching databases requires minimal changes) |
| Supports prepared statements | Fully supports prepared statements                                                                                         |
| Both Procedural and OOP      | Only OOP                                                                                                                   |
| Slightly faster for MySQL    | Minor performance hit                                                                                                      |
#### Connecting to MySQL
```php
<?php
// MySQLi procedural
$server = "localhost";
$username = "root";
$password = "";
$database = "test_db";
// Create connection
$conn = mysqli_connect($server, $username, $password, $database);
// Check connection
if (!$conn) die("Connection failed: " . mysqli_connect_error());
echo "Connected successfully"; // else

// MySQLi OOP
$conn = new mysqli($server, $username, $password, $database);
if ($conn->connect_error) die("Connection failed: " . $conn->connect_error);
echo "Connected successfully"; // else

// PDO
try {
  $conn = new PDO("mysql:host=$server;dbname=$database", $username, $password);
  // Set error mode to exceptions
  $conn->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
  echo "Connected successfully"; //if we reach here there were no exceptions
} catch (PDOException $e) { echo "Connection failed: " . $e->getMessage(); }
?>
```
The `setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION)` method ensures that errors are thrown as exceptions, making them easier to handle.

**DSN (Data Source Name) in PDO** 
defines the database connection settings in PDO.
`dsn = "mysql:host=HOSTNAME;dbname=DATABASE_NAME;charset=UTF8"`
`$conn = new PDO($dsn, $username, $password);`
##### Closing a connection
Not needed in small projects but necessary in large projects.
```php
//mysqli procedural
mysqli_close($conn);
//mysqli OOP
$conn->close();
//PDO
$conn = null;
```

#### Creating Database
```php
$sql = "CREATE DATABASE test_db"; // after connection is made

//MySQLi procedural
if (mysqli_query($conn, $sql)){ echo "Database created successfully";}
else { echo "Error creating database: " . mysqli_error($conn); }
//mysqli OOP
if ($conn->query($sql) === TRUE) { echo "Database created successfully";}
else { echo "Error creating database: " . $conn->error;}
//PDO
try {
 $conn->exec($sql);
 echo "Database created successfully";
} catch (PDOException $e) {
 echo "Error creating database: " . $e->getMessage();
}
```

#### Creating Table
```php
// connction
$conn = mysqli_connect($servername, $username, $password, $dbname);
$conn = new mysqli($servername, $username, $password, $dbname);
$conn = new PDO("mysql:host=$servername;dbname=$dbname", $username, $password);

// table
$sql = "CREATE TABLE IF NOT EXISTS Users (
 id INT(6) UNSIGNED AUTO_INCREMENT PRIMARY KEY,
 name VARCHAR(50) NOT NULL,
 email VARCHAR(50) NOT NULL
)";
//mysqli procedural
if (mysqli_query($conn, $sql)) { echo "Table Users created successfully";}
//mysqli OOP
if ($conn->query($sql) === TRUE) { echo "Table Users created successfully";}
//PDO // in try catch
$conn->exec($sql); echo "Table Users created successfully"; // if no exception
```

#### CRUD Operation
**CREATE (INSERT Data)** 
```php
$sql = "INSERT INTO users (name, email) VALUES ('John Doe', 'john@example.com')";
// MySQLi procedural
if (mysqli_query($conn, $sql)) { echo "New record created successfully";}
// MySQLi OOP
if ($conn->query($sql) === TRUE) { echo "New record created successfully"; }
//PDO //Optional binding for optimization and sequrity // in try catch
// Prepare SQL statement
 $stmt = $conn->prepare("INSERT INTO users (name, email) VALUES 
 (:name, :email)");
 // Bind parameters
 $stmt->bindParam(':name', $name);
 $stmt->bindParam(':email', $email);
 // Assign values and execute
 $name = "Alice Doe";
 $email = "alice@example.com";
 $stmt->execute();
 echo "New record created successfully";
```
**READ (SELECT Data)** 
```php
$sql = "SELECT id, name, email FROM users";
// MySQLi procedural
$result = mysqli_query($conn, $sql);
if (mysqli_num_rows($result) > 0) {
 while ($row = mysqli_fetch_assoc($result)) {
	 echo "ID: " . $row["id"] . " - Name: " . $row["name"] . " - Email: " . $row["email"] . "<br>"; }}

// MySQLi OOP
$result = $conn->query($sql);
if ($result->num_rows > 0) {
 while ($row = $result->fetch_object()) {
 echo "ID: " . $row->id . " - Name: " . $row->name . " - Email: ". $row->email . "<br>"; }}
//PDO
$stmt = $conn->prepare("SELECT id, name, email FROM users");
$stmt->execute();
$result = $stmt->fetchAll(PDO::FETCH_ASSOC);
foreach ($result as $row) {
 echo "ID: " . $row["id"] . " - Name: " . $row["name"] . " - Email: " . $row["email"] . "<br>"; }
```
**UPDATE (UPDATE Data)** 
```php
$sql = "UPDATE users SET email='newemail@example.com' WHERE id=1";
// Procedural
if (mysqli_query($conn, $sql)) { echo "Record updated successfully"; }

///PDO
$stmt = $conn->prepare("UPDATE users SET email=:email WHERE id=:id");
$stmt->bindParam(':email', $email);
$stmt->bindParam(':id', $id);
$email = "updated@example.com";
$id = 1;
$stmt->execute();
```
**DELETE (DELETE Data)** 
```php
$sql = "DELETE FROM users WHERE id=1";
// Procedural
if (mysqli_query($conn, $sql)) { echo "Record deleted successfully";}
//PDO
$stmt = $conn->prepare("DELETE FROM users WHERE id=:id");
$stmt->bindParam(':id', $id);
$id = 1;
$stmt->execute();
```


#### Why Prepared Statements?
allow you to execute the same SQL query multiple times with different inputs.
Benefits:
- Security - prevents SQL injection by insuring inputs are treated as data not Query.
- Performance - The database parses and compiles the query only once.
- Readability & Maintenance - cleaner and more manageable.

**SQL Injection Prevention**
`SELECT * FROM users WHERE username = 'admin' -- ' AND password = 'password'`
e.g. if a user inputs username as "'admin' --", all code after '--' will be commented and will break out code.
This logs in without a password check! Prepared statements mitigate this by treating user input strictly as data.

**Using `bind_param()` with `MySQLi`**
```php
$stmt = $mysqli->prepare("SELECT * FROM users WHERE username = ? AND password = ?");
$stmt->bind_param("ss", $username, $password);
$stmt->execute();
$result = $stmt->get_result();
```
- ?: Placeholder for data. 
- "ss": Specifies the types (s for string) corresponding to each placeholder

| Type Code | Description                                 |
| --------- | ------------------------------------------- |
| i         | Integer                                     |
| d         | Double                                      |
| s         | String                                      |
| b         | Blob (binary data, must be sent in packets) |


**Using `bindValue()` and `bindParam()` with PDO**
a more flexible approach
```php
$stmt = $pdo->prepare("SELECT * FROM users WHERE username = :username
AND password = :password");

//bindValue
$stmt->bindValue(':username', $username, PDO::PARAM_STR);
$stmt->bindValue(':password', $password, PDO::PARAM_STR);
$stmt->execute();
//bindParam
$stmt->bindParam(':username', $username, PDO::PARAM_STR);
$stmt->bindParam(':password', $password, PDO::PARAM_STR);
// Set values to the variables 
$username = "john_doe"; 
$password = "securepassword";
$stmt->execute();
```
	- :username and :password are named placeholders.
	- bindValue() binds the value immediately.
	- bindParam() binds a variable by reference, useful if the variable's value changes before execution.

| Data Type    | PDO Constant      | Description                                |
| ------------ | ----------------- | ------------------------------------------ |
| String       | `PDO::PARAM_STR`  | For any string or textual data.            |
| Integer      | `PDO::PARAM_INT`  | For integers (whole numbers)               |
| Boolean      | `PDO::PARAM_BOOL` | For boolean values (true or false)         |
| Null         | `PDO::PARAM_NULL` | For NULL values                            |
| Large Object | `PDO::PARAM_LOB`  | For large binary data (e.g. images, files) |


### Handling Errors & Exceptions
**`MySQLi`: `mysqli_error()` & `mysqli_errno()`** 
```php
$query = "SELECT * FROM non_existing_table";
$result = $mysqli->query($query);

// Check for query error
if (!$result) {
    echo "Error No: " . mysqli_errno($mysqli) . "<br>";
    echo "Error Message: " . mysqli_error($mysqli);
}
```
`mysqli_errno()` returns the corresponding error code, which can be helpful for more detailed debugging or when implementing custom error handling based on specific error numbers.

PDO: try-catch with `PDOException` 
PDO (PHP Data Objects) provides a more elegant way to handle errors using exceptions.
```php
try {
 $pdo = new PDO("mysql:host=localhost;dbname=database", "username","password");
 $pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
 $sql = "SELECT * FROM non_existing_table";
 $pdo->query($sql);
} catch (PDOException $e) {
 echo "Error: " . $e->getMessage();
}
```
`PDO::ERRMODE_EXCEPTION` triggers an exception whenever a database error occurs, allowing the program to handle errors more cleanly and avoid silent failures.

##### **Logging vs. Displaying Errors**

**Displaying Errors**
helpful during development : easier to spot and fix issues.
However, it's dangerous in a production environment since the error messages might reveal sensitive information, like file paths or database details.
To enable error display, you can use:
```php
ini_set('display_errors', 1);
error_reporting(E_ALL);
```

**Logging Errors** 
Safer to log errors instead of displaying them to users.
Still keep track of issues without exposing sensitive data.
```php
ini_set('log_errors', 1);
ini_set('error_log', 'errors.log');
error_log("Error occurred on " . date('Y-m-d H:i:s'));
```
`error_log()` allows you to write custom error messages, including timestamps for easier tracking.


### Database Environment, Transactions and Performance
**Environment Variables for DB Credentials (.env)** 
Storing database credentials directly in your PHP files is unsafe. A better approach is to use environment variables, typically stored in a `.env` file.
Example .env file:
```php
DB_HOST=localhost
DB_NAME=mydb
DB_USER=username
DB_PASS=password
```
PHP configuration
```php
$host = getenv('DB_HOST');
$db = getenv('DB_NAME');
$user = getenv('DB_USER');
$pass = getenv('DB_PASS');
try {
	 $pdo = new PDO("mysql:host=$host;dbname=$db", $user, $pass);
	 $pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
} catch (PDOException $e) {
	 die("Connection failed: " . $e->getMessage());
}
```

**Using Transactions for Data Integrity (commit(), rollback())** 
A **transaction** ensures a group of SQL statements either all succeed or all fail; maintaining data consistency.
```php
try {
  $pdo->beginTransaction();
  $pdo->exec("INSERT INTO accounts (user, balance) VALUES ('John', 1000)");
  $pdo->exec("UPDATE accounts SET balance = balance - 500 WHERE user ='John'");
  $pdo->commit();
} catch (PDOException $e) {
  $pdo->rollback();
  echo "Transaction failed: " . $e->getMessage();
}
```
- `beginTransaction()` starts the transaction.
- `commit()` saves the changes if everything is successful.
- `rollback()` reverts all changes if an error occurs.


**Performance: Indexes & Query Optimization** 
1. Indexes: Indexes speed up searches by creating a lookup table for faster access.
```sql
CREATE INDEX idx_username ON users(username);
-- This helps queries like:
SELECT * FROM users WHERE username = 'JohnDoe';
-- run significantly faster.
```
	Tip: Don't overuse indexes — they speed up reads but slow down inserts/updates.
2. Query Optimization:
- Avoid `SELECT *` Select only the columns you need.
- Use JOINs efficiently Fetch related data in a single query instead of multiple queries.
- Limit results:
	`SELECT * FROM orders ORDER BY date DESC LIMIT 10;`
- Cache results For data that doesn’t change often, caching reduces repetitive queries.


---
# CH-5 Managing State, Time, Password and Code Reusability
### Sessions and Cookies
**State Management**
HTTP is stateless, meaning each request is independent and the server doesn't remember past interactions. To maintain user-specific data like login status or shopping carts, web apps use **state management** techniques such as **sessions** and **cookies**.

**Sessions**
A session stores data on the server linked to a session ID (kept in a cookie) on the client. It's more secure than cookies since sensitive data isn't stored on the client.

To start a session in PHP, use the `session_start()` function at the beginning of your script:
Once a session is started, data can be stored in the `$_SESSION` `superglobal` array:
```php
session_start();
$_SESSION['username'] = 'JohnDoe';
$_SESSION['role'] = 'admin';
//To access session data, simply use: // on other pages
session_start(); echo "Welcome, " . $_SESSION['username'];
```
If you need to remove a specific session variable, use `unset()`, and to completely destroy a session, use `session_destroy()`:
```php
unset($_SESSION['username']); // Remove only the username variable
session_destroy(); // Destroy all session data
```

**Cookies** 
A **cookie** is a small file stored on a user's device, used to remember preferences, login info, and browsing history across sessions.
**Set a cookie in PHP:**
```php
setcookie("username", "JohnDoe", time() + (86400 * 30), "/");
```
This creates a cookie named `username` with the value `JohnDoe` that expires in 30 days.
A path of `"/"` means the cookie will be available throughout the entire domain (i.e., any page).
**Read a cookie:**
```php
if(isset($_COOKIE['username'])) echo "Hello, " . $_COOKIE['username'];
else echo "Welcome, guest!";
```
**Delete a cookie:**
```php
setcookie("username", "", time() - 3600, "/");
```
This expires the cookie by setting its expiration to a past date.

e.g. 
```php
// "Remember me option"
if(isset($_POST['remember_me'])) { setcookie("auth_token", md5($_POST['username'] . time()), time() + (86400 * 30), "/"); }
// theme
setcookie("theme", "dark", time() + (86400 * 30), "/");
// usage
if(isset($_COOKIE['theme']) && $_COOKIE['theme'] == 'dark')
 echo "<link rel='stylesheet' href='dark-theme.css'>";
```


### PHP Date and Time

**Get Current Date/Time**
The `date()` function in PHP fetches the current date and time. It takes two parameters: the **format** and an optional **timestamp**.

|Task|Code Example|Output Example|
|---|---|---|
|Current date|`echo date("Y-m-d");`|`2025-03-20`|
|Current time|`echo date("H:i:s");`|`14:35:23`|
|Full date/time|`echo date("Y-m-d H:i:s");`|`2025-03-20 14:35:23`|

**Get a Time:**

| Character | Description                                  | Example Output |
| --------- | -------------------------------------------- | -------------- |
| H         | 24-hour format of an hour (00 to 23)         | `14`           |
| h         | 12-hour format with leading zeros (01 to 12) | `02`           |
| i         | Minutes with leading zeros (00 to 59)        | `35`           |
| s         | Seconds with leading zeros (00 to 59)        | `23`           |
| a         | Ante meridiem or Post meridiem (am or pm)    | `pm`           |

**Get a Date:**

| Character | Description                 | Example Output |
| --------- | --------------------------- | -------------- |
| d         | Day of the month (01 to 31) | `20`           |
| m         | Month (01 to 12)            | `03`           |
| Y         | Year (4 digits)             | `2025`         |
| l         | Day of the week             | `Thursday`     |

Other separators like `/`, `.`, or `-` can be used to format the output.

**Examples:**
```php
echo date("d/m/Y");           // Output: 20/03/2025
echo date("m-d-Y");           // Output: 03-20-2025
echo date("l, F j, Y");       // Output: Thursday, March 20, 2025
```

---

**Get Timestamps** 
A **timestamp** is the number of seconds since January 1, 1970 (Unix Epoch). PHP uses it for date manipulation.

|Task|Code Example|Output Example|
|---|---|---|
|Get current timestamp|`echo time();`|`1710942923`|
**Convert Timestamp to Date**
You can convert a timestamp to a readable date:
```php
$timestamp = time();
echo date("Y-m-d H:i:s", $timestamp); // Output: 2025-03-20 14:35:23
```
**Date Manipulation**
Use `strtotime()` to add or subtract time from a date.

|Operation|Code Example|Output Example|
|---|---|---|
|Add 7 days|`echo date("Y-m-d", strtotime("+7 days"));`|`2025-03-27`|
|Subtract 1 month|`echo date("Y-m-d", strtotime("-1 month"));`|`2025-02-20`|
|Add 1 year, 2 months, 3 days|`echo date("Y-m-d", strtotime("+1 year 2 months 3 days"));`|`2026-05-23`|
**Calculate Date Difference**
Use `DateTime` objects to calculate the difference between two dates.
```php
$date1 = new DateTime("2025-03-20");
$date2 = new DateTime("2025-04-05");
$interval = $date1->diff($date2);
echo $interval->days; // Output: 16
```
Access other parts of the difference:
```php
echo $interval->y . ' years, '; // Output: 0 years
echo $interval->m . ' months, '; // Output: 0 months
echo $interval->d . ' days'; // Output: 16 days
```
**Time zones**
Handle time zones for global applications.
**Set and Get Time zone**
```php
// Set timezone
date_default_timezone_set("America/New_York");
// Display date in the new timezone
echo date("Y-m-d H:i:s"); // Output: 2025-03-20 09:35:23
// Get current timezone
echo date_default_timezone_get(); // Output: America/New_York
```
**Convert Between Timezones**
```php
$date = new DateTime("now", new DateTimeZone("UTC"));
$date->setTimezone(new DateTimeZone("Asia/Tokyo"));
echo $date->format("Y-m-d H:i:s"); // Output: 2025-03-21 01:35:23
```


### Include and Require
In PHP, `include` and `require` help with code reuse, making scripts cleaner and more maintainable. These functions allow you to write code once and reuse it, promoting modularity and simplifying updates (e.g., changing a shared navigation bar in one place).
Example:
**`header.php`:**
```php
echo "<h1>Welcome to My Website</h1>";
```

**Main Script:**
```php
include 'header.php';
echo "<p>Homepage content goes here.</p>";
```

**Output:**
```
Welcome to My Website
Homepage content goes here.
```

Both `include` and `require` work similarly, but `require` causes a fatal error if the file is missing, while `include` only produces a warning.

**Include Vs Require**
Both include and require bring in content from another file, but they behave differently when the file is missing or has **an error**.

| Function  | Behavior when missing a file                    | Typical Use Case                     |
| --------- | ----------------------------------------------- | ------------------------------------ |
| `include` | Issues a warning and continues script execution | Non-critical parts (e.g., ads)       |
| `require` | Throws a fatal error and stops script execution | Essential parts (e.g., config files) |

**`include_once()` /` require_once()`** 
Sometimes, you only want a file to load once — especially for configuration files or classes.


### Password Hashing and Security
Hashing transforms the password into a fixed-length string, making it difficult to reverse-engineer, ensuring that even if data is leaked, the original password remains protected.

**Hashing Methods Overview**
**MD5 and SHA1:**
Fast and widely supported hashing algorithms that produce 128-bit and 160-bit hashes, respectively. However, both suffer from collision attacks, where different inputs can result in the same hash. 
Their **speed**, once an advantage, now allows attackers to brute-force passwords quickly with modern hardware.

Example of MD5 (not recommended):
```php
$password = "mypassword";
$hash = md5($password);
echo $hash; // Outputs a hashed string, but it's insecure!
```

Modern secure hashing uses PHP's `password_hash()` function, which automatically generates a salt(a random string added to the password before hashing) to prevent rainbow table attacks, making the hash stronger.
*Example*:
```php
$password = "my_secure_password";
$hashedPassword = password_hash($password, PASSWORD_DEFAULT);
echo $hashedPassword; // Outputs a secure, salted hash
// manual salting before PHP 5.5
$salt = bin2hex(random_bytes(22));
$hashedPassword = hash('sha256', $salt . $password);
```

- **PASSWORD_DEFAULT** uses the strongest available algorithm (currently `bcrypt`)
- You can also specify **PASSWORD_BCRYPT** or **PASSWORD_ARGON2I/ID** for more control.


**Verifying Passwords**  
`password_verify()` checks if the provided password matches the stored hash:

```php
$storedHash = password_hash("securepass123", PASSWORD_DEFAULT);
if (password_verify($password, $storedHash)) {
    echo "Password is correct!";
} else {
    echo "Invalid password.";
}
```
---

**Hashing Algorithms**
- **`bcrypt`**: Uses Blowfish cipher and includes salting with an adjustable cost (work factor).

```php
$bcryptHash = password_hash($password, PASSWORD_BCRYPT, ['cost' => 10]);
```

- **argon2**: A newer, memory-hard algorithm resistant to brute-force and GPU attacks. PHP supports **PASSWORD_ARGON2I** and **PASSWORD_ARGON2ID**.

```php
$argonHash = password_hash($password, PASSWORD_ARGON2ID, [
    'memory_cost' => 1<<12, 'time_cost' => 4, 'threads' => 2
]);
```

```php
'memory_cost' => 1 << 12 // bit shift operator
```

This means "allocate 4096 KB of memory for the Argon2 hashing process."
`1 << 12` is a shorthand for **4096** (or 2^12), which is often used to configure memory costs in algorithms like Argon2.
bit shifting is a more efficient way to represent powers of 2, which is the way memory is typically allocated in binary systems.



# CH - 6 : APIs and External Data Handling
Intro
API (Application Programming Interface) is a set of rules and protocols that allows different software applications to communicate with each other. 
APIs define how requests and responses should be structured so that one system can interact with another seamlessly.

Key features
- Interoperability - across various platforms
- Reusability 
- Abstraction - only necessary functionalities
- Security - access to data

### Types of APIs
Depending on how they handle data and communication. 

##### Representational State Transfer (REST)
- Relies on standard HTTP methods like GET, POST, PUT, DELETE to perform operations.
- work with data formats like JSON and XML.
- Follows stateless approach -> each client request must contain all necessary information without depending on previous interactions. 

##### Simple Object Access Protocol
- Highly structured API protocol that strictly adheres to predefined standards.
- uses XML form message formatting and supports advanced security features as WS-Security.
- Used commonly in banking and financial systems where data integrity and security are critical.

##### `GraphQL`
- Provides a flexible approach to data retrieval. Unlike REST w/c returns fixed data structures, `GraphQL` allows clients to request exactly the data they need.
- It uses a single endpoint, for efficiency and reducing over or under fetching.
- It allow us to optimize our data queries and improve performance.

### RESTful API Principles
REST is an architectural style designed for networked applications, w/c relies on stateless communication between client and servers.
- Statelessness
- Client-Server Separation - clear separation of concern
- Uniform interface - consistent way to interact with resources using standard HTTP methods.
- Everything is treated as a resource, defined by a unique URL.
- The layered system principle allows the system to have multiple intermediary layers, such as for security, caching, or load balancing.
- Cache-ability - responses must indicate whether they are cacheable to optimize performance.


##### HTTP Methods (CRUD Operations)

| HTTP Method | Operation | Description                                | Example                                                              |
| ----------- | --------- | ------------------------------------------ | -------------------------------------------------------------------- |
| GET         | Retrieve  | Fetches data                               | GET /users → Fetch all users.<br>GET /users/1 → Fetch user with ID 1 |
| POST        | Create    | Creates a new resource                     | POST /users with JSON body → Creates a new user.                     |
| PUT         | Update    | Updates an existing resource on the server | PUT /users/1 with updated data → Updates user with ID 1.             |
| DELETE      | Delete    | Removes a resource from the server         | DELETE /users/1 → Deletes user with ID 1.                            |


##### Status Codes
HTTP status codes indicate the result of a client’s request.

| Status Code               | Description                                                             |
| ------------------------- | ----------------------------------------------------------------------- |
| 200 OK                    | The request was successful, and the response contains the expected data |
| 201 Created               | A new resource was successfully created.                                |
| 400 Bad Request           | The request is invalid or malformed.                                    |
| 404 Not Found             | The requested resource does not exist.                                  |
| 500 Internal Server Error | A generic error indicating a problem on the server.                     |

##### Data Formats: JSON vs. XML
JSON(JavaScript Object Notation)'s structure, based on key-value pairs, allows for easy parsing and processing, making it highly suitable for modern software development.

```json
{
	"id": 1,
	"name":"Jhon Doe",
	"email":"jhon@example.com",
}
```

XML(extensible Markup Language) - more complex and verbose.
- used in older systems and enterprise applications for high level of structure and flexibility.
```xml
<user>
	 <id>1</id>
	 <name>John Doe</name>
	 <email>john@example.com</email>
</user>
```


## Building and Consuming APIs in PHP
##### Handling Requests and Sending JSON Responses
PHP provides built-in functionalities to work with HTTP requests and responses efficiently.

**Receiving Requests**
PHP APIs handle HTTP requests using $_GET, $_POST, $_REQUEST, or by reading the request body

```php
//GET
if ($_SERVER['REQUEST_METHOD'] === 'GET') {
 $id = isset($_GET['id']) ? intval($_GET['id']) : null;
 echo json_encode(["message" => "Received GET request", "id" => $id]);
}
// POST
if ($_SERVER['REQUEST_METHOD'] === 'POST') {
 $data = json_decode(file_get_contents("php://input"), true);
 echo json_encode(["message" => "Received POST request", "data" => $data]);
}
//others
switch ($_SERVER['REQUEST_METHOD']) {
	case 'PUT': //
	case 'DELETE': //
	default: //
```

**Sending JSON Responses**
1. Set the appropriate Content-Type header to indicate that the response is in JSON format.
2. Use `json_encode()` to convert PHP arrays or objects into JSON.
3. Additionally, set response codes using `http_response_code()` to ensure proper status indication.
```php
header("Content-Type: application/json");
http_response_code(200);
$response = [
 "status" => "success",
 "message" => "Data retrieved successfully",
 "data" => ["id" => 1, "name" => "Sample"]
];
echo json_encode($response);
```

**Sending Error Responses**
```php
function sendErrorResponse($message, $code = 400) {
	http_response_code($code);
	echo json_encode(["status" => "error", "message" => $message]);
	exit;
}
if ($_SERVER['REQUEST_METHOD'] !== 'GET') {
 sendErrorResponse("Only GET requests are allowed", 405);
}
```

##### Making External API Requests in PHP
PHP provides different methods to perform API requests, such as `file_get_contents()` for simple requests and `cURL` for advanced operations.

**Using `file_get_contents()` for Simple Requests**
way to make GET requests to an API.
```php
$url = "https://api.example.com/data";
$response = file_get_contents($url);
if ($response === FALSE) {
	die("Error occurred while fetching data.");
}
$data = json_decode($response, true);
print_r($data);
```
Limitations
- only supports simple GET requests
- Does not allow setting headers or handling authentication
- It offers limited error handling capabilities.

**Using `cURL` for Advanced Requests**
`cURL` provides more flexibility and supports multiple HTTP methods, headers, authentication, and error handling.

Making a GET Request with `cURL`
```php
$url = "https://api.example.com/data";
$ch = curl_init($url);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
$response = curl_exec($ch);
if (curl_errno($ch)) {
	die("cURL error: " . curl_error($ch));
}
curl_close($ch);
$data = json_decode($response, true);
print_r($data);
```

**Making a POST Request with `cURL`**
```php
$url = "https://api.example.com/create";
$data = ["name" => "John", "email" => "john@example.com"];
$ch = curl_init($url);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_POST, true);
curl_setopt($ch, CURLOPT_POSTFIELDS, json_encode($data)); 
curl_setopt($ch, CURLOPT_HTTPHEADER, ['Content-Type: application/json']);
$response = curl_exec($ch);
if (curl_errno($ch)) {
 die("cURL error: " . curl_error($ch));
}
curl_close($ch);
$data = json_decode($response, true);
print_r($data);
```


**Handling API Responses & Errors**
Checking HTTP Status Codes
```php
$url = "https://api.example.com/data";
$ch = curl_init($url);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_HEADER, true);
curl_setopt($ch, CURLOPT_NOBODY, false);
$response = curl_exec($ch);
$httpCode = curl_getinfo($ch, CURLINFO_HTTP_CODE);
curl_close($ch);
if ($httpCode !== 200) {
 die("API request failed with status code: " . $httpCode);
}


$ch = curl_init("https://api.example.com/data");
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
$response = curl_exec($ch);
if ($response === false) {
	die("cURL Error: " . curl_error($ch));
}
$data = json_decode($response, true);
if (json_last_error() !== JSON_ERROR_NONE) {
	die("JSON decoding error: " . json_last_error_msg());
}
curl_close($ch);
print_r($data);
```

#### Fetching & Displaying External API Data
Fetching Data from Public APIs
```php
$apiKey = "your_api_key";
$city = "Addis Ababa";
$url =
"https://api.openweathermap.org/data/2.5/weather?q=$city&appid=$apiKe
y&units=metric";
$ch = curl_init($url);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
$response = curl_exec($ch);
curl_close($ch);
$weatherData = json_decode($response, true); echo "Temperature in $city: " . $weatherData["main"]["temp"] . "°C";
```


# CH - 7: File Handling
Without file handling, web applications would rely solely on databases, which might not be practical for all types of data storage.

Key reasons for file handling include:
- **Data Persistence**: Store information like user preferences between sessions.
- **Logging**: Track user actions, errors, and events for debugging and monitoring.
- **Configuration Management**: Save settings in files for flexibility and customization.
- **Content Management**: Store and serve dynamic content efficiently, such as blogs or news sites and store images.

### Reading & Writing Files
Opening a File - `$file = fopen("visits.log", "a+");`

| Mode | Description                                                                  |
| ---- | ---------------------------------------------------------------------------- |
| r    | Read-only. Starts at the beginning of the file.                              |
| r+   | r + Write.                                                                   |
| w    | Write-only. Erases content or creates a new file.                            |
| w+   | w + Read.                                                                    |
| a    | Write-only. Appends data to the end. Creates a new file if it doesn’t exist. |
| a+   | a + Read.                                                                    |
| x    | Write-only. Creates a new file. Returns FALSE if the file exists.            |
| x+   | x + Read.                                                                    |
| c    | Write-only. Opens the file but does not create it. Doesn’t overwrite.        |
| c+   | c + Read.                                                                    |

**Reading from Files**

```php
$file = fopen("example.txt", "r");
$content = fread($file, filesize("example.txt"));
fclose($file);
//file_get_contents() reads the file into a string (simpler for small files):
$content = file_get_contents("example.txt"); 
echo $content;
//fgets() Reads the file line-by-line, useful for processing large files
$handle = fopen("file.txt", "r");
while (($line = fgets($handle)) !== false) {
 echo $line . "<br>";
}
fclose($handle);
//fgetc() reads one character at a time, useful for parsing or tokenization
while (($char = fgetc($handle))!== false) {/**/}fclose(/**/);
//feof() checks if the end of file has been reached
while (!feof($handle)) {
	echo fgets($handle)
}
```


**Writing to Files**
```php
$file = fopen("log.txt", "a");
fwrite($file, "User visited on " . date("Y-m-d H:i:s") . "\n");
fclose($file);
```

**Handling Errors**
`$file = @fopen("nonexistent.txt", "r") or die("Error: File not found!");`
The @ suppresses errors, while `die()` outputs a custom error message.

**File Permissions and Security Considerations**
- Permissions: Ensure proper permissions (e.g., `chmod 644`) to prevent unauthorized access.
- Security: Avoid reading/writing sensitive files like `/etc/passwd`. Always validate file paths.

Simple Log System (build a basic log system to track user visits)
```php
// Open or create the log file
$logFile = fopen("visits.log", "a") or die("Unable to open file!");
// Record the visit with timestamp and IP address
$logEntry = "Visit from IP: " . $_SERVER['REMOTE_ADDR'] . " on " . date("Ym-d H:i:s") . "\n";
// Write the entry to the log
fwrite($logFile, $logEntry);
// Close the file
fclose($logFile);
echo "Visit logged successfully!";
```

### File and Directory Control
PHP provides functions to work with files and folders, allowing developers to automate tasks such as uploading files, organizing data, and managing user content.

**Deleting Files**
```php
$profilePic = "uploads/user123.jpg";
if (file_exists($profilePic)) {
	unlink($profilePic);
	echo "Profile picture deleted.";
} else {
	echo "File not found.";
}
```

**Creating Directories**
`mkdir(path, mode, recursive)`
```php
$username = "user123";
$userFolder = "uploads/$username";
if (!is_dir($userFolder)) {
 mkdir($userFolder, 0755, true);
 echo "User folder created.";
} else {
 echo "Folder already exists.";
}
```
0755 is the permission setting, and true allows nested folders if needed.

**Removing Directories**
```php
$categoryFolder = "uploads/category-abc";
if (is_dir($categoryFolder) && count(scandir($categoryFolder)) == 2) {
 // Only '.' and '..' exist
 rmdir($categoryFolder);
 echo "Empty category folder removed.";
} else {
 echo "Folder is not empty or doesn't exist.";
}
```

```php
realpath()    // Obtain the absolute path to a file
unlink()      // Delete a file
filesize()    // Retrieve the size of a file
file()        // Read the contents of a file into an array
is_writable() // Check if a file is writable
file_exists() // Check if a directory exists
scandir()     // Read the contents of a directory into an array
file_put_contents() // Write a string to a file
mkdir()       // Create a new directory
rmdir()       // Delete a directory
opendir()     // Create a pointer to a directory
is_file()     // Check if a directory entry is a file
is_dir()
```
**Understanding Paths**
a. Server Root Directory:
```php
$uploadPath = $_SERVER['DOCUMENT_ROOT'] . "/uploads/file.txt";
file_put_contents($uploadPath, "Hello world!");
echo "File saved to: $uploadPath";
```
b. Current Script Directory
`__DIR__` returns the directory of the currently executing script.
`include(__DIR__ . "/config.php");`


#### Image Processing
The GD Library is a powerful tool in PHP for creating and manipulating images.
- You can create images from scratch, modify existing ones, and perform tasks like resizing, cropping, and adding watermarks.

**Resizing Images**
```php
function resizeImage($file, $width, $height) {
	list($origWidth, $origHeight) = getimagesize($file);
	$imageResized = imagecreatetruecolor($width, $height);
	$image = imagecreatefromjpeg($file);
	imagecopyresampled($imageResized, $image, 0, 0, 0, 0, $width, $height,
		$origWidth, $origHeight);
	imagejpeg($imageResized, 'resized_image.jpg');
}
```
**Cropping Images**
```php
function cropImage($file, $x, $y, $cropWidth, $cropHeight) {
	$image = imagecreatefromjpeg($file);
	$imageCropped = imagecreatetruecolor($cropWidth, $cropHeight);
	imagecopyresampled($imageCropped, $image, 0, 0, $x, $y, $cropWidth,
		$cropHeight, $cropWidth, $cropHeight);
	imagejpeg($imageCropped, 'cropped_image.jpg');
}
```
**Adding Watermarks**
```php
function addWatermark($file, $text) {
	$image = imagecreatefromjpeg($file);
	$color = imagecolorallocate($image, 255, 255, 255);
	$font = __DIR__ . '/arial.ttf';
	imagettftext($image, 20, 0, 10, 30, $color, $font, $text);
	imagejpeg($image, 'watermarked_image.jpg');
}
```

# CH - 8: Object-Oriented PHP and MVC Architecture

OOP allows you to structure your code into modular, reusable pieces, making it easier to manage, extend, and debug.
- *Reusability*: You can reuse classes and objects across different parts of your application.
- *Maintainability*: Code is easier to read and maintain when organized into objects.
- *Scalability*: OOP makes it easier to scale up applications by separating concerns
- *Real-world modeling*: Objects can represent real-world entities, making your code more intuitive.

**Core Concepts of OOP**
Classes and Objects
```php
class Car {
	public $brand; 
	public function drive() { echo "The car is moving"; }
}
$myCar = new Car(); 
$myCar->brand = "Toyota";
```

**Encapsulation**
Means restricting direct access to some components of an object. This protects data and promotes security. `public, private, protected`.

#### Important OOP Concepts
**Constructors and Destructors** 
A constructor is a special method that automatically runs when an object of a class is created. It is used to initialize properties or run setup code. 
In PHP, constructors are defined using the `__construct()` method.

```php
class Book {
	public $title;
	public function __construct($title) {
		$this->title = $title;
	}
}
$book = new Book("PHP Programming");
```
A destructor is another special method, defined with __destruct(), which is called automatically when an object is destroyed or the script ends. It is often used to release resources like closing a file or database connection.
```php
class Demo {
	public function __destruct() {
	echo "Object destroyed.";
 } }
$demo = new Demo();
```

**Static Properties and Methods**
Static properties and methods belong to the class itself rather than to any object created from the class. They are accessed using the class name, not an object instance. `static` keyword

```php
class Math {
	public static $pi = 3.14;
	public static function add($a, $b) {
		return $a + $b;
	}
}
echo Math::$pi; // Output: 3.14
echo Math::add(5, 10); // Output: 15
```


**Abstract Classes and Interfaces**
An **abstract** class cannot be instantiated directly. Just extended by child classes. 
They may contain abstract methods, which are method declarations without bodies; child classes must implement them.
```php
abstract class Animal {
	abstract public function makeSound();
}
class Dog extends Animal {
	public function makeSound() {
		echo "Bark!"; }}
```
``
An **interface** defines a contract that classes must follow. A class that implements an interface must provide implementations for all its methods.

```php
interface Shape {
	public function area();
}
class Circle implements Shape {
	public function area() {
		return "Calculating area of Circle"; } }
```
Interfaces are useful when different classes must follow a similar structure but have different implementations.

**Traits in PHP**
Traits are a mechanism for code reuse in PHP. 
They allow you to include methods into multiple classes without using inheritance. This solves the problem when you want a class to inherit behavior from multiple sources.

```php
trait Logger {
	public function log($message) {
		echo "Log message: $message";
	}
}
class User {
	use Logger;
}
$user = new User();
$user->log("User created."); 
```

### Namespaces
**Purpose of Namespaces**
Namespaces are used to organize code and prevent naming conflicts in large projects. They group related classes, functions, or constants, similar to how folders organize files, ensuring that identical names from different libraries or parts of an application can coexist without errors.

**Defining and Using Namespaces**
- *Defining a Namespace*: Use the `namespace` keyword at the top of a PHP file to define a namespace.
```php
namespace App\Models;
class User {
	public function getName() {
		return "User from Models";
	}
}
```

- **Using a Class from a Namespace**:
	- Refer to the class with its full namespace path:
```php
$user = new \App\Models\User();
```
- Or import it with the `use` keyword for cleaner code:
```php
use App\Models\User;
$user = new User();
```

You can also alias classes if two classes have the same name:
```php
use LibraryOne\User as UserOne;
use LibraryTwo\User as UserTwo;
$user1 = new UserOne();
$user2 = new UserTwo();
```
**Namespaces and Autoloading**
Modern PHP applications (especially those following PSR-4 standards) often use autoloaders to automatically load class files based on their namespace and directory structure. 

Example: 
Namespace `App\Models\User` would map to the file path `App/Models/User.php`.
- Composer handles autoloading automatically by following this pattern, saving you from manually including class files.

### Autoloading Classes
In larger applications with dozens or hundreds of classes, manually including files becomes messy, hard to maintain, and error-prone.
Autoloading automatically loads the necessary class files when they are needed, without manually writing require statements.

**`spl_autoload_register()` Function**
PHP provides a built-in function called `spl_autoload_register()` to make autoloading simple and customizable. You register a function that PHP will call whenever it encounters a class that hasn’t been loaded yet.
e.g.
```php
spl_autoload_register(function ($className) {
	include $className . '.php';
});
$user = new User(); // If User class is not loaded, PHP will now include "User.php"
```

**Composer and PSR-4 Autoloading**
One of its features is that it automatically generates an autoloader for your classes based on PSR-4 standards.
PSR-4 is a standard that maps a namespace to a folder structure.
```php title=composer.json~example
"autoload": {
 "psr-4": {
 "App\\": "src/"
 }
}
```
then `composer dump-autoload`, Composer will then autoload any class under the `App\` namespace from the `src/` directory.

### Introduction to MVC Architecture
MVC stands for Model-View-Controller, a design pattern that separates an application into three interconnected components:
- **Model**: Manages data and business logic. It interacts with the database, processes data, and responds to controller requests.
- **View**: Manages the user interface. It displays data from the model in a user-friendly format, typically as HTML pages or templates.
- **Controller**: Serves as an intermediary between the Model and the View. It handles user input (e.g., form submissions), processes it (often using the Model), and returns the appropriate View.
##### Benefits of Using MVC
- **Separation of Concerns**: Each component has a distinct responsibility, simplifying development and maintenance.
- **Code Reusability**: Models, views, and controllers can be reused across different application parts.
- **Simplified Collaboration**: Frontend developers can focus on Views, while backend developers work on Models and Controllers.
- **Scalability**: Applications are organized, and each part remains independent, facilitating easier scaling.
- **Improved Testing**: Logic separation makes individual components easier to test.

PHP project, the folder structure usually looks like:
```
/app
	/Controllers
		HomeController.php
		UserController.php
	/Models
		User.php
		Product.php
	/Views
		home.php
		user.php
	/public
		index.php
```

The Public folder contains the front-facing files like `index.php`, CSS, JavaScript, and images.

Example flow: 
- User requests `https://example.com/user/profile`. 
- `index.php` routes the request to `UserController`.
- `UserController` fetches user data from the User model. 
- Data is sent to a `user.php` view to display.

### Connecting OOP with MVC
##### How Classes Represent Models, Views, and Controllers
In an MVC architecture, Object-Oriented Programming (OOP) structures the application into different classes, each with a specific responsibility:
- **Model Classes**: Represent the data layer. They manage database operations such as fetching, inserting, updating, and deleting records.
	- *Example*: User, Product, or Order classes.
- **View Files/Classes**: Responsible for displaying the output (HTML, JSON, etc.). In simple PHP MVC setups, Views are usually files, but in more advanced systems, View classes manage templates.
	- *Example*: View files or template classes.
- **Controller Classes**: Handle user input, control the application's flow, interact with models, and select which view to render.
	- *Example*: `UserController`, `ProductController`, etc.

Each part (Model, View, Controller) is organized into a separate class or set of files, adhering to OOP principles like encapsulation and separation of concerns.

E.g.
Here's a short example illustrating the three components in an MVC architecture:
- **Model Class**:
  ```php
class User {
	public function getUserData($userId) {
		// Fetch user data from the database
		return "User Data for ID: $userId";
	}
}
  ```

- **View File**:
```php
<!-- user_view.php -->
<html>
	<body>
		  <h1><?= $userData ?></h1>
	</body>
</html>
```

- **Controller Class**:
```php
class UserController {
	public function showUser($userId) {
		$userModel = new User();
		$userData = $userModel->getUserData($userId);
		include 'user_view.php';
	} }
```

In this example:
- The `User` class represents the Model, handling data retrieval.
- The `user_view.php` file represents the View, displaying the data.
- The `UserController` class represents the Controller, managing the flow between the Model and View.



# CH - 9: CMS and Frameworks
### Content Management Systems (CMS)
Software for organizing and facilitating collaborative content creation, especially for websites.
- **Content Storage**: Content is stored in a database and displayed using templates.
- **Goal**: Avoid hand coding.
**Common Functions**:
  - **Content Creation**: Easily create and format content through a UI.
  - **Content Storage**: Store content consistently in one place.
  - **Workflows/User Management**: Assign permissions based on roles like authors, editors, and admins.
  - **Publishing**: Manage when and where content goes live.
  - **Optimization**: Improve digital experience and learn from content.
  - **Indexing, Search, and Retrieval**: Enable efficient content search and retrieval.
  - **Theme System**: Modify site view and functionality using stylesheets, images, and templates.
  - **Extending Plugins**: Offer custom functionalities and features.
  - **Multilingual, Media Management**: Support for multiple languages and media management.

**Overview of CMS**
A content management system can have two core parts:
- **A content management application** (CMA) – allows to add and manage content on your.
- **A content delivery application (CDA)** – this is the backend, behind-the-scenes process that takes the content you input in the CMA, stores it properly, and makes it visible to your visitors.

Example CMSs: WordPress, Joomla, Drupal, Squarespace, `Wix`, Magento and eCommerce.

**Web CMS** 
- A software system that provides website authoring, collaboration, and administration tools.
- Designed to allow users with little knowledge of web programming to create and manage website content with relative ease.
- Uses a content repository or a database to store page content, metadata, and other information assets.
- Has a presentation layer (template engine) to display the content to website visitors based on a set of templates.
- Uses server side caching to improve performance.

**Website vs CMS**
**Website**: a collection of web pages and related content that is identified by a common domain name and published on at least one web server.
**CMS**: is a piece of software that allows you to store, manage and publish said web pages.

Most CMS are flexible, While there are some that focus on a specific use like Magento and eCommerce.
For example, you can use WordPress to power: • Static websites • Blogs • eCommerce stores • Forums • Social networks • Online courses • Membership sites • Portfolios and etc.

### Introduction to Frameworks (Teachers)
A set of libraries, tools and best practices that provide a structured foundation for software development. 
It defines a standard way to build and deploy applications by handling common tasks such as routing, database access, security, and session management.
They increase productivity, improve code organization, and promote maintainability. & often include built-in security features.

A CMS is designed for content-heavy websites and allows non-developers to manage content easily through a graphical interface.
In contrast, a framework is intended for developers to build customized applications from the ground up, offering more control and flexibility but requiring programming skills.

#### Introduction to Laravel
 A PHP web application framework for easier and faster development with built-in features.
- It was created by `Taylor Otwell`  in June 2011 as to provide a more advanced alternative to CodeIgniter framework by including built-in features like authentication and authorization.
- Its popularity has grown due to its elegant syntax, modern development tools, and active community. 

##### Core Features of Laravel
1. **MVC Architecture**:
	- *Models* represent the data and business logic (e.g. database tables)
	- *View* handles the user interface (HTML rendered withe Blade templates.)
	- *Controllers* act as intermediary between models and views, handling user input and responses. 
	- This separation of concern makes code easier to organize and maintain.
2. **Router**:
	- Clean and simple routing algorithm that maps URLs to specific controller actions or closures.
	- defined in `routes/web.php` or `routes/api.php` and can handle all HTTP methods.
	```php
	Route::get('/welcome', function () {
		return view('welcome');
	})
	```
3. **`Elequent` ORM**: 
	- It is Laravel's built in Object-relational mapper (ORM). w/c allows developers to interact with the database using PHP objects instead if writing SQL queries.
	```php
	$user = User::find(1);
	echo $user->name;
	```
	- Each model class corresponds to a table in the database, and relationships can be easily defined.
4. **Blade Templating Engine**:
	- Laravel’s lightweight and powerful templating engine. It allows the use of PHP code in views with a clean and readable syntax. 
	```php
	<h1> Hello, {{ $name }} </h1>
	```
	- supports features like template inheritance and conditionals (@if, @foreach), making view files clean and maintainable. 

##### Why Laravel is Popular
Reasons: 
- Elegant syntax and developer-friendly tools.
- Comprehensive documentation and learning resources. 
- Rich ecosystem, including tools like:
	- Artisan CLI for automation
	- Laravel Mix for asset compilation
	- Laravel Forge/Vapor for deployment
- Security features such as CSRF protection, authentication scaffolding, and input validation.
- Large community and frequent updates with new features. 

### Introduction to CodeIgniter 
Open-source PHP framework for building dynamic web applications. was developed by `EllisLab` & released in 2006. now maintained by British Columbia Institute of Tech. (BCIT).

It was created to provide a simple and elegant toolkit for developers who need a framework with small footprint and minimal learning curve.
It is Lightweight, fast and especially suited for shared hosting environments.

##### Core features of CodeIgniter
1. **Lightweight and Fast**:
	- around 2MB in its core & has high performance
	- doesn't require heavy server resources, suitable for speed-critical applications.
2. **MVC Architecture**:
	- Same as Laravel but, flexible in that CodeIgniter doesn't force strict MVC usage.
3. **Easy Configuration**:
	- minimal configuration to get started, uses simple PHP files for config and avoids complex syntax or setups.
	- No need for composer just download and use.
4. **Good Documentation**:
	-  clear and comprehensive documentation
	- Every feature is well explained with examples, which is particularly helpful for beginners. 

**Where CodeIgniter shines** 
- Small to medium size projects for fast development.
- Performance-sensitive apps.
- Environments with limited resources.
- Beginner friendly projects
- Legacy PHP support.

While it lacks modern features like ORM or templating engines, its simplicity makes it practical for more control and few abstractions.


### When To Use Frameworks
1. **Custom Applications**:
	- Tailored to specific business needs or workflows.
	- Unlike CMSs, Frameworks allow full control over the arch, logic and design.
2. **Large, Scalable Projects**:
	- They Support Modular arch, component reusability and separation of logic (MVC).
	- They are suited for:
		- Apps with multiple user roles and permissions
		- Projects with multiple developers
		- System with high traffic and frequent updates.
		- An API-first application powering mobile apps and web clients, requiring versioning and rate-limiting.
		- $\dots$ 
3. **Security and Maintainability Needs**:
	- Often come with Features like CSRF protection, input validation and SQL injection prevention.
	- The also promote best practices to help with writing maintainable and reusable code.
	- Useful for:
		- Apps handling sensitive data
		- Long-term maintenance

##### Choosing Between CMS and Frameworks
1. Small Websites vs. Complex Applications
	- CMS is ideal for small websites like blogs, portfolios, or news portals where content management is the main focus and no custom business logic is needed.
	- Frameworks are better suited for complex applications that need tailored workflows, data processing, and interaction logic.
2. Speed of Development vs. Flexibility
	- CMS platforms allow for quick deployment using pre-built plugins and themes but are limited in flexibility and customization.
	- Frameworks require more setup time but offer full control over how your application functions, looks, and scales. 

### Overview of Web Application Framework (not teacher's)
It is a software framework that is designed to support the development of web applications including web services, web resources, and web APIs.

It provides a standard way to build and deploy web applications on the World Wide Web.

They aim to automate the overhead associated with common activities performed in web development. Example:
- Libraries for Database access 
- Templating frameworks and session management
- They often promote code reuse 
- Although they often target development of dynamic web sites, they are also applicable to static websites

#### Types of framework architectures
Most web frameworks are based on the model–view–controller (MVC)
**Model-View-Controller (MVC)**  
   - Separates data (Model), logic (Controller), and UI (View).  
   - Promotes modularity, code reuse, and multi-interface support (e.g., mobile vs. desktop or machine readable).  

**Push-Based vs Pull-Based**
1. *Push-Based (Action-Based)* - Most MVC frameworks
	- Controllers process requests and "push" data to views.  
	- Examples: Django, Ruby on Rails, Spring MVC, CodeIgniter.  
2. *Pull-Based (Component-Based)*
	- Views "pull" data from multiple controllers as needed.  
	- Examples: Jakarta Server Faces, Wicket, Tapestry. 
3. *Hybrid (Push & Pull)*
    - Supports both approaches.  
    - Examples: Play, Struts, ZK.

**Three-tier organization**
applications are structured around three physical tiers: 
- Client,
- Application, - contains the business logic and runs on a server
- Database - normally an RDBMS

### Framework applications
Frameworks are built to support the construction of internet applications based on a single programming language, ranging in focus:
- general purpose tools like Zend, Ruby on rails, augment the capabilities of a specific language
- and native-language programmable packages built around a specific user app, e.g. CMS, some mobile dev tools and portal tools

**Single Page Applications**: make heavy use of JavaScript and only refresh parts of the page.
**Server Side Applications**: Apache Wicket, ASP.NET Core, `CakePHP`, Catalyst, CodeIgniter, ...
**Client Side Applications**: Backbone.js, AngularJS, Angular, `EmberJS`, ReactJS, jQuery UI, Svelte, Vue
#### Common Features of Web Frameworks
- Frameworks set the **control flow** of a program and allow the user of the framework to "hook into" that flow by exposing various events. This design pattern is considered a defining principle of a framework.
	- e.g. some popular `microframeworks` such as Ruby's `Sintra` (w/c inspired `Express.js`) allow for "middleware" hooks prior and after HTTP requests.
		- these can be used for logging, auth, session management and redirecting
- Web template system
- Caching - caching web documents in order to reduce bandwidth usage, server load, and perceived "lag“
	- this bypasses stages such as database access or template interpretation
- Security - web frameworks often come with auth and authorization frameworks for identification and restrict access functions based on a criteria.
	- e.g. Drupal - provides role based access to pages and a web based interface to create users and assign roles to them.
- Database access, mapping and configuration - a unified API to a database backend that enable us to work with variety of DB's with no code changes.
	- and some OOP frameworks contain mapping tools to provide object-relational mapping w/c maps objects to tuples.
- they minimize configuration through the use of introspection and/or following well-known conventions.
- Other features include transactional support and database migration tools

- **URL mapping** - a mechanism by which the framework interprets URLs.
	- **Pattern Matching** (e.g., Django, Drupal) – Uses regex to match URLs.
    - **URL Rewriting** – Converts complex URLs into simpler ones.
    - **Graph Traversal** (e.g., `Zope`) – Navigates an object graph.
    - Enables **clean, SEO-friendly URLs** (e.g., `/page/science/physics` instead of `?cat=science&topic=physics`).
- **AJAX Support**: Allows **asynchronous data exchange** without full page reloads.
	- Dedicated (e.g., jQuery, `Axios`)., Built into larger frameworks (e.g., Ruby on Rails includes jQuery).
	- increases interactivity, speed, maintainability, and usability
	- Trend: High-level languages (Java, Python, Ruby) can compile to JavaScript (e.g., Google Web Toolkit, `Pyjs`).
- **Web Services & RESTful APIs** - **Features**:
	- Tools for building **web services** (SOAP, REST). 
    - **RESTful frameworks** support **Resource-Oriented Architecture (ROA)**.
    - Aligns with **Semantic Web** (RDF) for structured data.





---
# CH - 10: Performance Optimization and Security in Web APPs

### Performance Optimization
##### 1. Caching
- Storing copies of files and data in temporary storage locations to enable faster access in subsequent requests.
- it reduces server load and response time, it also makes our apps more scalable.
**Types of caching** 
1. *page level Caching* - the entire HTML output for static content. e.g. Response::cache() in Laravel.
2. *Database Query Caching* - results of big queries, e.g. Laravel's QC using Redis.
3. *Opcode Caching* - compiled PHP code. -> `opcache.enable=1` in `php.ini`
4. *Browser Caching* - Static assets (CSS, JS and Images) in the browser, e.g. in PHP `header("Cache-Control: max-age=31536000")` and others

Implementation Examples
- File based: Laravel's file cache - stores cache in local files
- In-memory caching: Redis, `Memchached` - high speed & scalable cache for sessions, queries etc.
- Opcode caching: `OPcache` - speeds up PHP execution
- CDN-based caching: Cloudflare, AWS - caches static content at network edge

##### 2. Query Optimization
1. **Use of Indexes**:
	- e.g. SQL:`CREATE INDEX idx_email ON users(email);`, 
	- Laravel: `$table->index('email');`
2. **Avoiding `SELECT *`**:
	- PHP:`$pdo->query("SELECT id, name FROM users");`
	- Laravel: `DB::table('users')->select('id', 'name')->get();`
3. **Analyzing Slow Queries (Using EXPLAIN)**:
	- SQL:`EXPLAIN SELECT id FROM users WHERE email = 'admin@example.com';`
	- Laravel:`DB::listen(function ($query) { logger($query->sql);});`
4. **Pagination and Limiting Results**:
	- SQL: `"SELECT * FROM posts ORDER BY created_at DESC LIMIT $limit OFFSET $offset";`
	- Laravel: `$posts = DB::table('posts')->orderBy('created_at', 'desc')->paginate(10);`

##### 3. Code Optimization
1. **Efficient Loops and Logic** - reduce the depth of nested loops when processing large datasets.
```php title=bad-practice
foreach ($users as $user) {
	foreach ($posts as $post) {
		if ($user->id == $post->user_id) {
			// Process post for user
		}	} }
```

```php title=good-practice
	$postsByUser = [];
	foreach ($posts as $post) {
		$postsByUser[$post->user_id][] = $post;
	}
	foreach ($users as $user) {
		if (isset($postsByUser[$user->id])) {
			// Process posts for user
		}
	}
```
- foreach is more optimized for arrays in PHP.
```php
	for ($i = 0; $i < count($array); $i++) { // not this
	foreach ($array as $item) { // but this
```
- Short-circuiting Conditions: Stop evaluating conditions as soon as possible to save processing time.

2. **Reducing Unnecessary I/O or DB Calls**:
	- *Batch Database Queries*: Fetch data in bulk or using more efficient queries. Avoid multiple roundtrips to the database.
	```php
	foreach ($users as $user) { // Bad - Multiple DB Queries
		$posts = DB::table('posts')->where('user_id', $user->id)->get();
	}
	$posts = DB::table('posts') // Good - Single DB Query with Join
	->join('users', 'posts.user_id', '=', 'users.id')
	->get()
	```
	- *Caching Results*:  for subsequent requests to avoid repeated queries
	```php
	$cacheKey = 'user_posts_' . $userId;
	$posts = Redis::get($cacheKey);
	if(!$posts) {/*fetch*/}
	```
	- *Lazy Loading & Eager Loading* (in Laravel): Lazy Loading fetches data when you need it. Eager Loading fetches related data upfront, reducing queries.
	```php
	$users = User::all(); // Bad Practice (Lazy Loading)
	foreach ($users as $user) {
		// Fetch posts for each user separately (N+1 problem)
		$posts = $user->posts;
	}
	$users = User::with('posts')->get(); // Good Practice (Eager Loading)
	// same loop but we now access the posts without any queries
	```
3. **Avoiding Expensive Functions in Loops**:
	- Some functions or operations are computationally expensive (e.g., `strlen()`, `count()`, `array_search()`).
	```php
	for ($i = 0; $i < count($items); $i++) { } //bad
	$count = count($items); //good
	for ($i = 0; $i < $count; $i++) { }
	```
4. **Avoiding Object Instantiation Inside Loops**:
	- can increase memory usage and slow down execution.
	```php
	$obj = new SomeClass(); // good
	foreach ($items as $item) {
		 $obj->process($item);
	}
	```
5. **Use `array_map()`, `array_filter()`, and `array_reduce()` for Array Operations**:
	- Instead of writing custom loops to manipulate arrays, efficient and clean.
	```php
	$results = array_map(function($item) { // filter then map
	 return $item * 2;
	}, array_filter($array, function($item) {
	 return $item > 5;
	}));
	```
6. **Minimize Memory Usage by Unsetting Variables**:
	 - Large objects and arrays consume a lot of memory.
	 - `processItem($item);  unset($item);`
7. **Avoid `implode()` or `join()` in Loops**:
	- they are expensive functions, especially in loops.
	- `$results .= implode(',', $item); // Multiple implodes`
	- `$results .= $item . ','; // Concatenate directly`
8. **Use `isset()` Over `empty()` for Faster Checks**:
	- `isset()` checks if a variable is set and is not null, which is generally faster than `empty()`.
9. **Use `str_replace()` for Simple String Replacements**:
	- faster and simpler compared to `preg_replace()` when performing simple replacements.
10. **Use PDO for Database Interactions**:
	- more efficient and secure than `mysql_*` functions.
	- It supports prepared statements, which are faster and prevent SQL injection.


### Security Threats

##### 1. SQL Injection
Occurs when untrusted input is used to construct raw SQL queries, allowing attackers to inject malicious SQL code.
```php
$id = $_GET['id']; // Vulnarable code
$result = mysqli_query($conn, "SELECT * FROM users WHERE id = $id");
// Secure code (prepared stmt)
$stmt = $conn->prepare("SELECT * FROM users WHERE id = ?");
$stmt->bind_param("i", $id); // $id must be integer
$stmt->execute();
```

##### 2. Cross-Site Scripting (XSS) 
Injection of malicious JavaScript into pages viewed by other users. 
- Always escape user input when displaying in HTML.
```php
echo $_GET['name']; // Vulnarable code ?name=<script>alert('Hacked!');</script>
echo htmlspecialchars($_GET['name'], ENT_QUOTES, 'UTF-8'); // Secure
# &lt;script&gt;alert('Hacked');&lt;/script&gt
```

##### 3. Cross-Site Request Forgery (CSRF)
Tricks authenticated users into submitting unintended requests.
**Example**: A hidden link or form triggers an action (e.g., deleting an account) without user consent.
Solution:
- Use CSRF tokens in forms.
- Validate tokens on the server.

##### 4. Remote Code Execution (RCE)
Allows attackers to execute arbitrary code or shell commands on the server.
```php
eval($_GET['code']); //Avoid: eval(), exec(), system() with user input.
```

##### 5. File Inclusion Vulnerabilities
Occurs when user input determines which files the server includes, leading to local file disclosure or remote execution.
- `include($_GET['page'] . ".php");`
- Use a whitelist of allowed pages or structured conditional logic (e.g., switch-case).
##### 6. Session Hijacking and Fixation
Attacker steals or fixes a session ID to impersonate users.
Solutions:
- Use `session_regenerate_id(true)` on login.
- Enable secure session cookie settings (`HttpOnly`, `Secure`, `SameSite`).
- Validate session data regularly.
##### 7. Insecure File Uploads
Uploading malicious files disguised as legitimate content (e.g., PHP scripts renamed as .jpg).
Solutions:
- Validate file types and extensions.
- Store uploads outside the web root.
- Rename files before storing.
- Use proper MIME type checking and set file permissions.

##### 8. Information Disclosure
Revealing sensitive information such as stack traces, server paths, or credentials.
Solutions:
- Disable `display_errors` in production.
- Log errors securely.
- Display generic error messages to users.

### Best Practices and Tools
**1. Using Security Headers**
Headers via server configuration (e.g., Apache, Nginx) or in PHP using header().

- Content-Security-Policy (CSP): Prevents cross-site scripting (XSS) and data injection by controlling the sources of content.
	- `Content-Security-Policy: default-src 'self';`
- X-Content-Type-Options: Prevents MIME-type sniffing.
	- `X-Content-Type-Options: nosniff`
- X-Frame-Options: Protects against clickjacking.
	- `X-Frame-Options: DENY`
- Strict-Transport-Security (HSTS): Enforces HTTPS connections.
	- `Strict-Transport-Security: max-age=31536000; includeSubDomains`

You can set these headers via server configuration (e.g., Apache, Nginx) or in PHP using `header()`.

**2. Validating and Sanitizing Input**
All user input should be trusted as untrusted:
- Validation ensures the data is of the expected format and type (e.g., email, integer).
	- `filter_var($email, FILTER_VALIDATE_EMAIL);`
- Sanitization cleans data to remove or escape unwanted characters.
	- `filter_var($email, FILTER_SANITIZE_EMAIL);`

**3. Secure Session Management**
Use `session_regenerate_id(true)` after login or privilege change.
Configure secure cookie parameters:
```php
session_set_cookie_params([
 'secure' => true,
 'httponly' => true,
 'samesite' => 'Strict'
]);
// Destroy sessions properly on logout:
session_unset();
session_destroy();
```
Avoid storing sensitive information in sessions.

**4. Using Frameworks and Libraries Responsibly**
Modern PHP frameworks offer built-in security, but they must be used correctly.
Framework Benefits (e.g., Laravel, Symfony):
- CSRF protection
- XSS filtering
- Input validation
- Secure authentication and password hashing

Best Practices:
- Keep all libraries and frameworks up to date.
- Avoid using unmaintained or untrusted third-party packages.
- Use Composer to manage dependencies and run composer audit to detect vulnerabilities.
- Read and follow the security documentation of the framework.










# Notes
Backend developers manage databases, create and optimize application logic, design APIs, and configure server architecture. caching, optimizing database queries.

4 Components of client-server architecture -> client, server, database, network(through HTTP)

 a PHP-based web server, Apache receives a request from a user's browser and passes it to a PHP interpreter, which processes the request, interacts with a database if needed, and generates an HTML response.

Workflow
Request -> Server processing -> database? -> response -> client render
also
DNS Look Up -> DNS IP response -> TCP/IP connection -> HTTP Request -> HTTP Response

Adv of CSA = multiple clients, centralized auth, dedicated DB, data sharing without duplication

Backend developer responsibilities -> B. Logic, Manage DB, Authentication, Scaling and reliability, dynamic content for requests.

Web Servers -> handle requests, process and response, load balancing, caching, access control.
Servers: Apache(open source, shared hosting), Nginx(event driven, reverse proxy), `LiteSpeed`(faster alt for Apache),  Tomcat(java based: enterprise)

Web servers -> 1. request, 2. processing(forward to 3. backend app if required), 4. response gen and response in HTTP, 5. rendering

Features of WS, -> SSL/TSL, Logging, Virtualization, Compression, Proxy(hiding), Rate limiting and response throttling.

Auth types: username, MFA, Role based access control, `OAuth` and JWT.

SQL injection -> prepared statements, input validation, privileges, web app firewalls, escaping input

XSS -> input sanitization, content security policy (restricting execution of inline scripts), HTTP-only and secure cookies, Framework security features

**Performance** ->
*Caching* -> client-side, server-side, CDN, object/D.S caching, page cache, DB query cache, Opcode caching (storing compiled PHP or other interpreted code).
*Load balancing* -> round robin, least connections, App-level load balancing(reverse proxies to intelligently route requests based on factors such as server health, traffic load, and response times.)
*Asynchronous Processing* -> message queues, worker threads, promise & async-await, web sockets(remain open instead of request-response), serverless functions, deferred execution.

Future Trends -> Serverless Computing, Microservices Architecture(flexible to use d/t programming languages and frameworks for different services), AI-Powered Backends


U-2

print(returns success) vs echo(void, & can take multiple arguments, marginally faster)

Removing Variables: `unset($variable)`
constants: 
```php
define("MINSIZE", 50); 
echo MINIMIZE 
echo constant("MINSIZE");
```
Only scalar data (Boolean, integer, float and string) can be contained in constants.
```php
$somevar = 15;
function addit() {
	GLOBAL $somevar;
	$somevar++;
}
```

a static variable will not lose its value when the function exits.
`function keep_track() {	STATIC $count = 0;`

`$random_number = mt_rand($lower, $upper);`

```php
if(!preg_match("/^[.0-9]*$/", $value)) {} // Digits 0-9 only Validation
if(!preg_match("/^[a-zA-Z]*$/", $value)) {} // Letters only Validation
if(!filter_var($value, FILTER_VALIDATE_EMAIL)) {} // E-mail Address Validation
```

Arrays : Numeric, Associative(a string index), Multi-dimensional
`array_shift(), array_push(), array_pop(), array_unshift(), print_r()` should only be used for numeric arrays.

function names are not case sensitive

```php
function sayHello()
	echo "Hello<br />";
$function_holder = "sayHello";
$function_holder(); // dynamic funton calls
```


CH-4

`new PDO("mysql:host=$server;dbname=$database", $username, $password);`

```php
$conn = mysqli_connect($server, $username, $password, $database);
if (!$conn) {die();} // procedural

$conn = new mysqli($server, $username, $password, $database);
if ($conn->connect_error){die();} // oop

try { //PDO
  $conn = new PDO("mysql:host=$server;dbname=$database", $username, $password);
  // Set error mode to exceptions
  $conn->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
  echo "Connected successfully"; //if we reach here there were no exceptions
} catch (PDOException $e) { echo "Connection failed: " . $e->getMessage(); }


mysqli_close($conn); // procedural
$conn->close(); //mysqli OOP
$conn = null; //PDO

$sql = "CREATE DATABASE test_db"; // any statement
if (mysqli_query($conn, $sql)) {}
if ($conn->query($sql) === TRUE) {}
try {
 $conn->exec($sql); } catch(PDOException $e){}

// Prepare SQL statement PDO
$stmt = $conn->prepare("INSERT INTO users (name, email) VALUES (:name, :email)");
// Bind parameters
$stmt->bindParam(':name', $name);
$stmt->bindParam(':email', $email);
// Assign values and execute
$name = "Alice Doe";
$email = "alice@example.com";
$stmt->execute();


$sql = "SELECT id, name, email FROM users";

$result = mysqli_query($conn, $sql);
if (mysqli_num_rows($result) > 0) {


$result = $conn->query($sql);
if ($result->num_rows > 0) {

$stmt = $conn->prepare("SELECT id, name, email FROM users");
$stmt->execute();
$result = $stmt->fetchAll(PDO::FETCH_ASSOC);
foreach ($result as $row) {

```

Prepared Statements: -> security, performance, readability & maintenance.
```php
$stmt = $mysqli->prepare("SELECT * FROM users WHERE username = ? AND password = ?");
$stmt->bind_param("ss", $username, $password);
$stmt->execute();
$result = $stmt->get_result();


$stmt = $pdo->prepare("SELECT * FROM users WHERE username = :username
AND password = :password");

//bindValue -> binds the current value of the variable
$stmt->bindValue(':username', $username, PDO::PARAM_STR);
$stmt->bindValue(':password', $password, PDO::PARAM_STR);
$stmt->execute();
// bindParam -> binds the variable and changes with the variable
$stmt->bindParam(':username', $username, PDO::PARAM_STR);
$stmt->bindParam(':password', $password, PDO::PARAM_STR);
// Set values to the variables 
$username = "john_doe"; 
$password = "securepassword";
$stmt->execute();
```

| Large Object      | `PDO::PARAM_LOB` | For large binary data (e.g. images, files) |
| ----------------- | ---------------- | ------------------------------------------ |
| `PDO::PARAM_NULL` | `PDO::PARAM_INT` | `PDO::PARAM_STR` `PDO::PARAM_BOOL`         |

Displaying Errors :
```php
ini_set('display_errors', 1);
error_reporting(E_ALL);
// Logging Errors
ini_set('log_errors', 1);
ini_set('error_log', 'errors.log');
error_log("Error occurred on " . date('Y-m-d H:i:s'));
```

```php
//.env
DB_HOST=localhos

//php
$host = getenv('DB_HOST');
```

```php
try {
  $pdo->beginTransaction();
  $pdo->exec("INSERT INTO accounts (user, balance) VALUES ('John', 1000)");
  $pdo->exec("UPDATE accounts SET balance = balance - 500 WHERE user ='John'");
  $pdo->commit();
} catch (PDOException $e) {
  $pdo->rollback();
  echo "Transaction failed: " . $e->getMessage();
}
```

```sql
CREATE INDEX idx_username ON users(username);
```
	Don't overuse indexes — they speed up reads but slow down inserts/updates.
Query Optimization:
- Avoid SELECT * Select only the columns you need.
- Use JOINs efficiently Fetch related data in a single query instead of multiple queries.
- Limit results:
	`SELECT * FROM orders ORDER BY date DESC LIMIT 10;`
- Cache results For data that doesn’t change often, caching reduces repetitive queries.


**RESTful API Principles** 
- Statelessness
- Client-Server Separation - clear separation of concern
- Uniform interface - consistent way to interact with resources using standard HTTP methods.
- Everything is treated as a resource, defined by a unique URL.
- The layered system principle allows the system to have multiple intermediary layers, such as for security, caching, or load balancing.
- Cache-ability - responses must indicate whether they are cacheable to optimize performance.

```php
$url = "https://api.example.com/create";
$data = ["name" => "John", "email" => "john@example.com"];
$ch = curl_init($url);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_POST, true);
curl_setopt($ch, CURLOPT_POSTFIELDS, json_encode($data)); 
curl_setopt($ch, CURLOPT_HTTPHEADER, ['Content-Type: application/json']);
```

```php
$content = file_get_contents("example.txt"); 
$file = fopen("example.txt", "r");
while (($line = fgets($file)) !== false) { echo $line . "<br>"; }
while (($char = fgetc($handle))!== false) {/**/}
while (!feof($handle)) {
fclose($file);

$file = fopen("log.txt", "a");
fwrite($file, "User visited on " . date("Y-m-d H:i:s") . "\n");
fclose($file);

$file = @fopen("nonexistent.txt", "r") or die("Error: File not found!");
```



# Questions



Here are 30 multiple-choice questions based on the provided material:

Which of the following is the primary focus of backend development? a) User interface design b) Logic, database, and server operations c) Client-side scripting d) Styling web pages
    
Which of the following is a common task of a backend developer? a) Creating HTML and CSS layouts b) Managing databases and designing APIs c) Implementing frontend frameworks like React d) Ensuring website responsiveness
    
Which programming language is commonly used for backend development with the Laravel framework? a) JavaScript b) Python c) PHP d) Java
    
What is a crucial aspect for maintaining the speed and reliability of a backend application? a) Complex frontend animations b) Optimizing database queries and implementing caching c) Using the latest JavaScript features d) Minimizing the use of images
    
What is the computing model where multiple clients request and receive services from a centralized server called? a) Peer-to-peer network b) Client-Server Architecture c) Distributed system d) Mainframe computing
    
Which of the following is a responsibility of the client in a client-server architecture? a) Processing database queries b) Facilitating user interaction and sending requests c) Managing application logic d) Handling user authentication
    
Which web technology is typically used by the client to send requests to the server? a) PHP b) Java c) HTTP/HTTPS d) SQL
    
What is the role of the server in a client-server architecture? a) Displaying the user interface b) Processing requests and sending responses c) Storing static website files only d) Handling only client-side validation
    
Which of the following is a structured system for storing and managing data that a server interacts with? a) Network b) Client c) Database d) Framework
    
What protocol is primarily used for communication between clients and servers over the internet? a) FTP b) SMTP c) HTTP/HTTPS d) TCP/IP (while foundational, HTTP/HTTPS is the application protocol)
    
Which of the following security measures protects sensitive information during transmission between a client and a server? a) Firewall rules b) SSL/TLS encryption c) Load balancing d) Caching
	
In the typical workflow of a client-server interaction, what happens after the client sends an HTTP/S request? a) The client renders the data. b) The server processes the request. c) The database is directly updated. d) The network routes the request.
    
Which of the following is a key responsibility of a backend developer? a) Designing the user interface b) Writing client-side JavaScript code c) Handling business rules and database operations d) Creating CSS stylesheets
    
Which of the following functionalities is typically enabled by backend development? a) Interactive UI elements b) User login systems and payment gateways c) Website animations d) Responsive layouts
    
Which programming language is known for its clean syntax and powerful frameworks like Django? a) PHP b) Java c) Python d) Node.js
    
For which type of applications is Node.js particularly well-suited due to its asynchronous nature? a) Content Management Systems b) Data-heavy applications c) Real-time applications d) Enterprise applications
    
What is the primary function of a web server? a) To design the layout of web pages b) To process client requests and deliver web pages or data c) To manage databases directly d) To handle client-side scripting
    
Which popular web server is open-source and widely used in shared hosting environments, supporting PHP? a) Nginx b) LiteSpeed c) Tomcat d) Apache
    
What is the purpose of load balancing in web server management? a) To encrypt data transmission b) To distribute incoming traffic across multiple servers c) To store frequently accessed data d) To manage user authentication
    
What type of content can web servers serve? a) Dynamic content only b) Static content only c) Both static and dynamic content d) Only database information
    
What is SQL injection? a) A method of encrypting database connections b) A technique to optimize database query performance c) Exploiting vulnerabilities in database queries by injecting malicious SQL statements d) A type of server-side caching mechanism
    
What is a common prevention method for Cross-Site Scripting (XSS) attacks? a) Using strong passwords b) Implementing load balancing c) Input sanitization and Content Security Policy (CSP) d) Using HTTPS protocol
    
What is the purpose of caching in performance optimization? a) To encrypt network traffic b) To store frequently accessed data for faster retrieval c) To distribute traffic across multiple servers d) To handle asynchronous requests
    
Which caching strategy involves storing static assets like CSS and JavaScript in the user's browser? a) Server-side caching b) Client-side caching c) Object caching d) Page caching
    
What is the benefit of asynchronous processing in backend development? a) It ensures all requests are processed sequentially. b) It improves efficiency by handling multiple requests simultaneously. c) It primarily enhances frontend performance. d) It simplifies database interactions.
    
What is the main characteristic of serverless computing? a) Developers manage the underlying servers. b) Applications run on dedicated physical servers. c) Developers can run applications without provisioning or managing servers. d) It requires manual scaling of resources.
    
What is a potential disadvantage of serverless computing? a) Automatic scaling b) Reduced operational costs c) Cold start delays d) Simplified deployment
    
What architectural style structures applications as a collection of small, independent services? a) Monolithic architecture b) Microservices architecture c) Client-server architecture d) Event-driven architecture
    
Which of the following is a benefit of using a microservices architecture? a) Increased complexity in deployment b) Difficult inter-service communication c) Independent scaling of individual services d) Reliance on a single technology stack
    
What is a key capability enabled by AI-powered backends? a) Designing user interfaces with natural language b) Analyzing data, making predictions, and automating decision-making c) Directly manipulating client-side browser behavior d) Simplifying the management of physical servers




Each action in an e-commerce website typically triggers an _ HTTP _ request to the server.
A server is a _ backend _ system that processes requests from clients and sends responses.
In a Node.js environment, the server directly handles requests using its built-in _ HTTP _ module.
Security measures like _ SSL/ TSL _ encryption protect sensitive information during transmission6 .

Server
APIs
Laravel, Node
caching
clients
device ?
Angular, Client
Request ?
__
__
NoSQL
HTTP/S
password? SSL/ TSL
request? HTTP/S
websites? servers? Application
	Login
dynamic
Ruby? Node
Frontend
Node? Django
PHP
JS/ Node
user? HTTP/S
Apache
`Nginx`
Load balancing
backend
data? SSL/ TSL
caching
virtual
authentication
RBC - role based control? Least privilege principle
___ firewalls . **Web Application Firewalls (WAFs)**
prepared statements
- Content Security Policy (CSP) restricts the execution of _ inline _ scripts in a web application
client side / malicious? Inline
round robin
serverless
microservices
web sockets
AI



CH-2
hypertext processor, server side
html, js , php
plain html
`.php .php3, .phtml`
to be sent to every browser?
_ _
`<?php ?>`
;
echo, print
The "_here document_" syntax can be used with the print statement to output multiple lines with variable interpolation
_ _
SUPERGLOBALS
`$_SERVER` is a `superglobal` that holds server, execution environment information
_ _
_ _
Session data
`unlink()`? `unset()`
data types, resources
constant, define()
may not be redefined, undefined
name
constant()
global variables, GLOBAL
static variable
permeative/ ? scalar data
PHP automatically converts between _ floating point _ and numbers
strings? 
concatenation
copy
smaller string
insert 0
reverse copy
_ _
pads
PAD_RIGHT? STR_PAD_RIGHT
after the found
nearest int
up
down
range
random


`ksort()` key sort







Here are the fill-in-the-blank questions without the answers:

1. `When a form uses the _GET_ methd, the data is passed in the _URL_.`
2. `The form variables are available to PHP in the superglobal array called _$_REQUSET_, _$_POST_, and _$_GET_.`
3. `The _$_GET_ method can't be used to send _binary data_, like images or word documents.`
4. `The $_REQUEST superglobal contains the contents of $_GET,  $_POST, and _ _ variables.` `$_COOKIE`
5. `The PHP header() function can be used to _redirect_ the browser to _another page/ location_.`
6. `A good way to validate a form on the server is to ___________ the form to ___________.` post, itself before redirecting
7. `___________ or ___________ can be used for ___________.` X
8. `strlen($password) can be used for ___________ validation.` length
9. `An array with a ___________ index is called a ___________.` numeric -> `numeric`
10. `An array where each ___________ is associated with a value is called an ___________.` `ID Key, associative array`
11. `The ___________ loop statement is used to iterate over ___________.` foreach, array
12. `array_shift() removes an element from the ___________ of an array.` front
13. `array_push() adds an element to the ___________ of an array.` back
14. `___________ is used to sort ___________ alphabetically or numerically, from lowest to highest value.` sort, numerically indexed arrays
15. `___________ sorts the elements in the array ___________.` `asort(), with indexes intact`
16. `Functions ___________ be defined before they are called.` MUST
17. `Function names are ___________ case sensitive.` NOT
18. `It is possible to assign function names as strings to variables for ___________.` dynamic function calls
19. `PHP provides two primary ways to interact with MySQL databases: ___________ and ___________.`
20. `___________ supports ___________.`
21. `The ___________ in PDO defines the database connection settings.` DSN
22. `The setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION) method in PDO ensures that ___________.`
23. `___________ is the SQL operation for creating (inserting) data.` I into
24. `___________ is the SQL operation for reading data.` SELECT _ _
25. `___________ is a function used in ___________ to connect to MySQL.` 
26. `$conn->query() is a method used in ___________ to execute SQL queries.`
27. `$conn->exec() is a method used in ___________ to execute SQL queries.`
28. `___________ help in ___________.`
29. `In MySQLi prepared statements, _______ is used as a placeholder for data.`
30. `In PDO prepared statements, ___________ is used as a placeholder for data.`
31. `The bind_param() method is used with ___________ prepared statements.`
32. `The bindParam() and bindValue() methods are used with ___________ prepared statements.`
33. `mysqli_error() returns the ___________ of the last MySQLi function.`
34. `mysqli_errno() returns the ___________ of the last MySQLi function.`
35. `In PDO, errors are typically handled using _______ blocks with _______.`
36. `In a production environment, it is safer to ___________ errors instead of displaying them.`
37. `___________ speed up searches by creating a ___________.`
38. `Avoid ___________ when you only need specific columns.`
39. `Use ___________ efficiently to fetch related data in a single query.`
40. `___________ can be used to limit ___________.`
41. `___________ results for data that doesn’t change often.`
42. `___________, ___________, and ___________ are used for ___________ to ensure data integrity.`







