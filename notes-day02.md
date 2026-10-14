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















