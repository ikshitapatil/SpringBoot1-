# Spring Boot MVC Web Application 🚀

## Project Overview

This project is a basic Java Spring Boot MVC application created to understand the fundamentals of backend web development using Spring technologies.

The application can:

* receive parameters directly from the URL,
* generate personalized greeting messages,
* render dynamic HTML pages with Thymeleaf,
* display static images on the webpage.

This project was built using:

* Java
* Spring Boot
* Spring MVC
* Thymeleaf
* Maven

---

# Technologies & Tools

* Java
* Spring Boot
* Spring MVC
* Thymeleaf
* Maven
* IntelliJ IDEA

---

# Project Folder Structure

```text
src
 └── main
     ├── java
     │    └── pl.edu.vistula.firstprojectjavaspring
     │          └── controller
     │                └── HelloController.java
     │
     └── resources
          ├── templates
          │      └── greeting.html
          │
          └── static
                └── images
                      └── vistula.png
```

---

# Application Workflow

The project follows the MVC (Model-View-Controller) architecture pattern.

## Controller Layer

The controller is responsible for processing HTTP requests and returning responses.

Controller file:

```text
HelloController.java
```

Example method:

```java
@GetMapping("/greeting")
public String greeting(
        @RequestParam(name = "name", required = false, defaultValue = "World")
        String name,
        Model model) {

    model.addAttribute("name", name);

    return "greeting";
}
```

---

# Method Explanation

### `@GetMapping("/greeting")`

Handles GET requests sent to:

```text
/greeting
```

### `@RequestParam`

Reads the `name` value from the URL.

### `model.addAttribute("name", name)`

Passes the value from the controller to the HTML page.

### `return "greeting"`

Returns the `greeting.html` Thymeleaf template.

---

# Thymeleaf HTML Template

Template file:

```text
greeting.html
```

The webpage:

* shows a greeting message,
* prints the entered user name,
* displays a static image.

Example:

```html
<h1 th:text="'Hello, ' + ${name} + '!'"></h1>

<img src="/images/vistula.png">
```

---

# HTTP Request Example

## GET Request

```text
http://localhost:8080/greeting?name=Vistula
```

The application reads the `name` parameter and dynamically displays a personalized greeting page.

---

# Use Cases

## Use Case 1 — Greeting Page

### HTTP Method

GET

### URL

```text
http://localhost:8080/greeting?name=Vistula
```

### Purpose

The application retrieves the `name` parameter from the URL and displays a custom greeting using Thymeleaf templates.

The page also contains:

* additional MVC content,
* a static Vistula image loaded from the resources folder.

### Output

* Hello, Vistula!
* This is my first Spring Boot MVC page.
* Vistula logo/image displayed on the webpage.

---

## Use Case 2 — Static Resource Display

### HTTP Method

GET

### URL

```text
http://localhost:8080/images/vistula.png
```

### Purpose

Loads a static image from the `resources/static/images` directory.

### Output

The image/logo is displayed successfully in the browser.

---

# Running the Project

## Step 1 — Open the Project

Open the project using IntelliJ IDEA.

## Step 2 — Run the Application

Run the main Spring Boot application class:

```text
FirstProjectJavaSpringApplication
```

## Step 3 — Open in Browser

Visit:

```text
http://localhost:8080/greeting?name=Vistula
```

---

# Screenshots

## Browser Output

<img width="440" height="525" alt="Browser Output" src="https://github.com/user-attachments/assets/9e803869-36d0-4376-8129-27a3d38ec3cf" />

---

## IntelliJ Project Structure

<img width="460" height="868" alt="Project Structure" src="https://github.com/user-attachments/assets/daf1edb0-f32c-4c94-b96b-53704f71b4f3" />

---

## Controller Implementation

<img width="460" height="868" alt="Controller Code" src="https://github.com/user-attachments/assets/daf1edb0-f32c-4c94-b96b-53704f71b4f3" />

---

## Static Image Preview

<img width="1259" height="868" alt="Static Image" src="https://github.com/user-attachments/assets/b2fd4e8a-6653-473d-8a97-401330afef12" />

---

# GitHub Repository

Repository Link:

```text
https://github.com/ikshitapatil/SpringBoot1-.git
```

---

# .gitignore

The project includes a `.gitignore` file to avoid uploading unnecessary files to GitHub.

Ignored files/folders include:

* `.idea`
* `target`
* temporary files
* system-generated files

---

# Author

Ikshita Patil

GitHub: https://github.com/ikshitapatil
