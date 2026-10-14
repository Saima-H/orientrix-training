# RESTFUL API IN 100 SEC

<img width="299" height="131" alt="image" src="https://github.com/user-attachments/assets/a57865b8-c482-4c50-adf7-989d0812c06a" />

Most api in the world are RESTFUL , which means they follow set of rules or constraints known as representational state transfer(std for api development)

RESTful api organizes data entities or  resources into a bunch of unique URI'S(Uniform Resource Identifiers)
URI-->DIFFERENTIATE DIFFERENT TYPES OF DATA RESOURCES ON A SERVER


client can get data about a resource by making a request to the end point over http

The request message has a particular format 
**POST/dinosaur HTTP/1.1**//startline (dinosaur-URI,POST-http verb or request method)
//Accept,Authorization,Connection are headers which contain info about meta data
**Accept:application/json** //tells i only accept data in a particular format
**Authorization:<token>**// tells u r allowed to make tht request
**Connection:keep-alive**
**{"face":🥇 
}** //body




<img width="215" height="167" alt="image" src="https://github.com/user-attachments/assets/0da304cf-c816-4ea0-a233-0c70182975eb" />

<img width="225" height="175" alt="image" src="https://github.com/user-attachments/assets/9905844a-a8c5-4f23-8e67-0b1312d3e82d" />
<img width="223" height="137" alt="image" src="https://github.com/user-attachments/assets/bc2bc766-1f05-4147-8837-735ebfb6f4ac" />

<img width="279" height="358" alt="image" src="https://github.com/user-attachments/assets/bd594c4b-4e5d-431b-9130-5e15865f8498" />

THE SERVER WILL RECEIVE THE  REQUESTMSG THEN EXECUTE SOME CODE USUALLY TO READ FROM A DB THT CAN BE FORMATTED TO A RESPONS MSG

<img width="206" height="162" alt="image" src="https://github.com/user-attachments/assets/b7250f91-2436-44f3-a0c9-b767331c3fb2" />


<img width="206" height="101" alt="image" src="https://github.com/user-attachments/assets/4adb5ca3-ae2e-4c98-8507-f000dc7d6395" />

<img width="236" height="168" alt="image" src="https://github.com/user-attachments/assets/df842f78-d985-4ad1-be6d-a630d1854fcb" />

<img width="225" height="167" alt="image" src="https://github.com/user-attachments/assets/c98c6348-2fe2-49ac-9d2e-1af268ccc50c" />
The response body is usually formatted in JSON when talking about API'S 
The important thing about this architecture is tht its **STATELESS**
which means tht the two parties dont need to store any info about each other and every req-response cycle is independent from all other communication.


# API'S FOR BEGINNERS
Actually everything tht we use has an iterface we dont understand its complete working internally but we know how to use it ryt internally these buttons for example will interact with the api which will do the magic 

Helps in abstraction of implementation 
Most likely when the word api  is used its used to refer web based api

most of the api's provide some way of working with strings
<img width="311" height="179" alt="image" src="https://github.com/user-attachments/assets/7efefc08-a1bd-4921-ab7f-c5d35419b442" />

**CONFUSIONNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNN**
# BUT ISN'T IT SIMILAR TO FUNCTION THEN WHTS THE DIFFERENCE BETWEEN API AND FUNCTION 

This is a fantastic question that gets to the heart of software engineering terminology. The confusion is very common because, in practice, people use these words interchangeably.

**Short Answer:**
Yes, `toUpperCase()` is **both** a function and an API method.
*   It is a **Function** because it performs a specific action (it takes an input, does work, and returns a result).
*   It is an **API** because it is a standardized tool provided by the language (JavaScript) for you (the developer) to use to interact with the string data type.

However, not all functions are APIs, and not all APIs are functions.

Here is the breakdown of the distinction, an example where they are distinct, and a comparison table.

---

### The Core Distinction: Implementation vs. Interface

To understand the difference, think of a **Restaurant**:

1.  **The Function (Implementation):** This is the kitchen. The chef takes ingredients (input), cooks them (process), and produces a meal (output). You don't see how it happens; it just works.
2.  **The API (Interface):** This is the **Menu**. It is the contract that tells you, "If you ask for 'Pasta,' you will get 'Pasta.'" It doesn't tell you how to cook it; it just defines *what* you can ask for and *what* you will get back.

**`toUpperCase()`** is the item on the menu (API). The specific code written by the JavaScript engine to convert those letters is the kitchen (Function).

---

### Example Where It Can't Be Both

To see the distinction clearly, we need a scenario where something is an API but **not** a function.

**Example: A REST API Endpoint**

Imagine a weather app. You want to get the weather for London. You make a request to:
`https://api.weather.com/v1/london`

*   **Is this an API?** Yes. It is a defined interface that allows your code to talk to a remote server.
*   **Is this a function?** No. It is a **URL (or Endpoint)**. It is a location/address, not a piece of executable code in your file.

You might use a function to *access* it (like `fetch()`), but the API itself is the **service contract**, not the code block.

**Another Example: A GUI (Graphical User Interface)**

*   **Is it an API?** Yes. The "Save" button in Microsoft Word is part of the API (Application Programming Interface). It allows you to interact with the software.
*   **Is it a function?** No. It is a visual button. You click it with a mouse. It is an interface element, not a function definition.

---

### The Clear Distinction (Table)

| Feature | Function | API (Application Programming Interface) |
| :--- | :--- | :--- |
| **Definition** | A specific block of code designed to perform a particular task. | A set of rules, protocols, and tools that allows different software to communicate. |
| **Nature** | **Implementation.** It is the *how*. | **Interface.** It is the *what* and the *contract*. |
| **Scope** | Usually small, self-contained logic. | Can be massive (entire libraries, web services, operating systems). |
| **Visibility** | You can often read the code inside a function. | You usually cannot see the code inside an API (it's a "black box"). |
| **Example** | `function add(a, b) { return a + b; }` | The `toUpperCase()` method, The Google Maps API, The Windows API. |
| **Relationship** | A function can be *part of* an API. | An API is often *made of* many functions. |
| **Analogy** | The engine inside a car. | The steering wheel and pedals (the controls). |

### Applying this to your image

In the image you provided, `'yeet!'.toUpperCase()`:
1.  **It is a Function:** It is an executable block of code. You call it, it runs, it returns `"YEET!"`.
2.  **It is an API:** It is part of the **JavaScript String API**. The creators of JavaScript (ECMAScript standard) decided that every string in the language must have a `toUpperCase` method. They published this "contract" so developers know they can use it.

**Summary:**
*   **Function** = The *action* (verb). "I am going to run this code."
*   **API** = The *catalog* of actions available to you. "Here is the list of codes you are allowed to run."

  **Yes, exactly.** 

# One single API (like `toUpperCase()`) works on any OS.

**But remember:** It only works because the developer wrote separate code for each OS **behind the scenes**. 

You see **one button**. They built **three different machines** under it.

# Remote API :
A **Remote API** is an API that lives on a **different computer** (a server), not on your own device. You access it over the internet.

**Simple Analogy:**

- **Local API** = Your TV remote. It's in your hand. You press a button, the TV responds instantly.
- **Remote API** = Calling a restaurant to order food. You dial a number, someone far away takes your order, and they send back the result.

**Example:**

- **Local API:** `'yeet!'.toUpperCase()` — runs on YOUR computer.
- **Remote API:** Weather app asks `api.weather.com/london` — runs on THEIR server.

**How it works:**

1. Your code sends a **request** over the internet.
2. The remote server does the work.
3. It sends back a **response** (usually data like JSON).

**Key point:** You never see the code. You just send a request and get an answer. Same idea as a local API, but the work happens far away.
computational power of remote api is insane
ex:google translate in rela time translates stuff

# REST:The architectural style 
its lyk how we use word xerox for photocopy 
REST for api

# When api's embrace the style and constraints of REST they are said to be RESTful
<img width="236" height="134" alt="image" src="https://github.com/user-attachments/assets/b9a3732e-2bf9-4f37-bc41-1dec390321a3" />



**URI** = The full address (ID card).
**URL** = The location (Home address).

**Simple way to remember:**
- **URI** tells you **what it is** (name/ID).
- **URL** tells you **where it is** and **how to get it**.


**Perfect example!** You got it. ✅

- **URI:** `saima` → Just identifies **who** (a name/ID).
- **URL:** `hyd` → Tells you **where** she is (Hyderabad).

**But wait — one small fix:**

A **URL** usually needs a bit more to be a real "location." Like:

- **URI:** `saima`
- **URL:** `https://india.com/hyderabad/saima`

**Why?** Because a URL must tell you:
1. **How** to get there → `https://`
2. **Where** it is → `india.com/hyderabad/`
3. **What** it is → `saima`

**Your version simplified:**
- **URI** = Saima (the person)
- **URL** = Hyderabad (the place)

That works as a basic idea. But a full URL is like a **full postal address**, not just the city.

**So:**

| | Your Example | Full Version |
| :--- | :--- | :--- |
| **URI** | `saima` | `saima` |
| **URL** | `hyd` | `https://india.com/hyderabad/saima` |

**Bottom line:** You understood the concept. Just remember a URL needs the "how to get there" part (`https://`).












