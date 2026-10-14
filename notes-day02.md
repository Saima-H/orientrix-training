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

<img width="521" height="315" alt="image" src="https://github.com/user-attachments/assets/c347fbd4-073d-450d-82b0-2a8b1b5d9b35" />

URL has a scheme portion http
http specifies the uri along with a htttp verb in this case its GET

<img width="251" height="91" alt="image" src="https://github.com/user-attachments/assets/58bc5e08-59bd-4316-90cd-ec10699164cd" />

The server receives the request and sends back the response to client
The most important part of the response is the body. for a webpage tht contains HTML(Hyper text markup lang) this forms the ht part of http

# HTTP-Its a stateless protocol
There are some pieces of important info included in request and response
# ways to pass info about request 
**1.query string parameters in url's(stuff after question mark)**



**2.THRU SPECIFIC KEY-VALUE PAIRS CALLED HEADERS**
1.Both req and response have headers and they are used to communicate whts wanted as well as wht has been said back.
2.some req headers allow u to write info about the content u expect back , u can also specify u want to access a page if it was changed this allows cahing
3.u can embed authentication info in each req using a header , this way u keep client logged in acrosss requests



response also contains headers
important one is status code: helps to convey wht happens on server side

# WHAT EXACTLY IS THE RELATION BETWEEN REST AND HTTP (YE RISHTA KYA KEHLATA HAI)
Here is your pizza analogy mapped exactly to the tech world:

### 🍕 The Analogy

**HTTP (The Waiter)**
The waiter’s only job is to carry food from the kitchen to your table. He doesn't care if you order a pizza, a salad, or a rock. He just delivers whatever you ask for. 

-   **Tech:** HTTP is just the protocol (the delivery system) that moves data (JSON, HTML, images) between your browser and a server. It doesn't care what the data is.

**REST (The Restaurant Manager)**
The manager writes the menu rules. The manager says: "We don't just throw food at customers. We serve pizza on a plate, we use a specific section of the menu for drinks, and we use the right utensils." 

-   **Tech:** REST is a set of architectural rules for designing the API. It says: "Don't use verbs in URLs. Use nouns. Use the right HTTP methods for the right actions."

---

### 🍕 The Tech Part (With Your Analogy)

**1. The Bad Restaurant (HTTP without REST)**
-   **You say:** "Hey waiter, go get me the pizza and remove the pepperoni."
-   **Tech:** `GET /getPizza?remove=pepperoni`
-   **Why it's bad:** You are using the word "get" in the URL. The waiter (HTTP) delivers it, but the menu is messy.

**2. The Good Restaurant (HTTP + REST)**
-   **You say:** "Hey waiter, I want the pepperoni pizza, but I want to modify it."
-   **Tech:** `PUT /pizzas/pepperoni` (with new data)
-   **Why it's good:** The URL is just a noun (`/pizzas/pepperoni`). The action is the HTTP method (`PUT`). This follows REST rules.

---

### 🍕 The "Plate vs. Tray" Rule

You said: *"HTTP just focuses on serving pizza but REST says serve it on a plate not tray."*

**Tech Translation:**

-   **HTTP says:** "I can carry your data using `GET`, `POST`, `PUT`, `DELETE`."
-   **REST says:** "Okay, but here are the rules for using those:
    -   Use `GET` to **read** data (Don't use it to delete!).
    -   Use `POST` to **create** new data.
    -   Use `PUT` to **update** data.
    -   Use `DELETE` to **remove** data.
    -   Keep your URLs clean (nouns, not verbs)."

---

### 🍕 Summary Table

| Analogy | Tech | Role |
| :--- | :--- | :--- |
| **Waiter** | **HTTP** | Delivers the order (data) back and forth. |
| **Menu Rules** | **REST** | Tells you how to order and how to name things. |
| **"Plate not Tray"** | **RESTful URL Design** | `GET /users/5` instead of `GET /getUser?id=5` |
| **The Pizza** | **Data (JSON)** | The actual thing being delivered. |

**Bottom line:** 
HTTP is the **vehicle**. REST is the **traffic law**. You need both to have a smooth ride. 🍕🚗


**REST USES HTTP IN IT LIKE RESTFUL APIS USE HTTP METHODS TO DO THEIR WORK**

# REST(REPRESENTATIONAL STATE TRANSFER) , API'S THAT MEET REST ARCHITECTURE ARE CALLED RESTful. CONSTRAINTS THT DEFINE THEM:


<img width="290" height="289" alt="image" src="https://github.com/user-attachments/assets/bf09f3e3-02f3-4d77-b49e-90030557d204" />



REST API sits on top of web tech like a little hat 

<img width="466" height="221" alt="image" src="https://github.com/user-attachments/assets/d8a53d61-8636-4844-9d47-cce74d2dc6ac" />
**CONSTRAINT 1: CLIENT-SERVER ARCH**
**CONSTRAINT 2:STATELESS** SINCE WE ARE USING HTTP PROTOCOL ITS  STATELESS

SO basically when we send a request from client we are basically requesting something , whats tht something ????????????????????????????????????????

tht something is RESOURCE 
(7 CROREEEEEEEEEEEEEEEEEEEEEEEEEEEEEEE!!!! LOL)
SO THIS RESOURCE IS THE 'R' IN URI,URL 
resource is a reference to an object which could be anything in the real lyf

































