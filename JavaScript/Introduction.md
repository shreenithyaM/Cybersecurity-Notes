# Introduction to JavaScript

Before learning JavaScript, let's understand where it fits in web development.

Every webpage is created using three building blocks:

- **HTML**
- **CSS**
- **JavaScript**

Let's discover what each one does with a simple example.

---

## 1. Why JavaScript?

Every website you use today is built using three technologies that work together.

Let's understand them using a simple example.

### Example: Watching a Video on YouTube

You see a **Like** button below the video.

- **HTML** creates the button.
- **CSS** makes the button look attractive.
- **JavaScript** makes the interaction possible.

When you click the button, the like count can increase instantly without refreshing the page.

### Example: Shopping Online

You see an **Add to Cart** button.

- **HTML** displays the button.
- **CSS** controls its appearance.
- **JavaScript** performs the action.

When you click the button, JavaScript can add the product to your cart and update the cart count immediately.

> [!IMPORTANT]
> **HTML creates the content, CSS styles it, and JavaScript makes it interactive.**

---

## 2. What Is JavaScript?

**JavaScript** is a programming language that allows websites to:

- Respond to user actions
- Update content dynamically
- Communicate with servers
- Perform calculations
- Validate user input
- Create interactive experiences

JavaScript can run directly in web browsers and can also run outside the browser using environments such as **Node.js**.

---

## 3. Where Does JavaScript Run?

### In the Browser

JavaScript runs directly inside modern web browsers such as:

- Google Chrome
- Mozilla Firefox
- Microsoft Edge
- Safari

Modern browsers have built-in JavaScript engines that execute JavaScript code.

### Outside the Browser

Using **Node.js**, JavaScript can also run outside the browser.

It can be used to build:

- Servers
- APIs
- CLI tools
- Backend applications
- Automation scripts

---

## 4. What Can You Build With JavaScript?

JavaScript is one of the most versatile programming languages.

It can be used to build many different types of applications.

| Type | Examples |
|---|---|
| **Interactive Websites** | Dynamic webpages and animations |
| **Web Applications** | Dashboards, online tools, and web apps |
| **Backend APIs** | Server-side applications and APIs |
| **Games** | Browser-based games |
| **Mobile Apps** | Android and iOS applications |
| **Desktop Apps** | Cross-platform desktop applications |
| **Browser Extensions** | Chrome and Firefox extensions |
| **Automation Scripts** | Task automation and utility scripts |

### One Language, Many Possibilities

With JavaScript, you can build:

- Websites
- Web applications
- Servers
- APIs
- Games
- Mobile applications
- Desktop applications
- Browser extensions
- Automation tools

---

## 5. Your First JavaScript Code

Let's write your first line of JavaScript:

```javascript
console.log("Hello, World!");
```

---

## 6. How JavaScript Is Useful in Cybersecurity

JavaScript is useful in cybersecurity because most modern websites use JavaScript. Understanding it helps security professionals find and understand **web application vulnerabilities**.

## Real-World Example: XSS

Suppose a website has a comment box:

```text
User enters a comment
        ↓
Website displays the comment
```
If the website does not properly handle user input, an attacker might inject JavaScript code instead of a normal comment.

> [!NOTE]
The following is a simplified example for learning purposes only. It is not a real-world XSS payload or a complete attack.

For example:
``` javascript
<script>alert("XSS")</script>
```

If the website executes this code, it can lead to an XSS (Cross-Site Scripting) vulnerability.

Why Learn JavaScript?

- JavaScript helps cybersecurity professionals understand:
- How websites work
- How user input is processed
- How APIs communicate
- How browsers handle data
- How vulnerabilities like XSS happen

> In simple words: JavaScript helps you understand the behavior of web applications, which is important for finding and fixing web security issues.
