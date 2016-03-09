## HTTP Questions

__URLs__

* Name all of the parts of the url that you can remember.  In your own words describe what they do.

```
  --> protocol has two types of HTTP, http and https.
  --> domain name - DNS sends the request with the domain name to get IP address that's associated with the IP domain name. Domain name is just a way to replace IP?
                    easy for human to read.
  --> port - domain can have several ports. Usually we use the non default ports
             for testing.
  --> path - this is like the directory. We can access different files by
             navigate the path.
  --> query string - get request?
  --> anchor tag - allow us to jump to a specific id on a page.
```

* Name the pieces of the following urls:

```
	* `https://www.google.com/`
  --> https:// is the secured protocol.
  --> www.google.com is the domain name.
  --> port is set to default.
	* `https://workbook.galvanize.com/cohorts/41/learning_experiences/367`
  --> https:// is the secured protocol.
  --> workbook.galvanize.com is the domain name.
  --> port is set to default.
  --> cohorts/41/learning_experiences/367 is the path name.
	* `http://locahost:5000/animals/puppies?onlycute=1&size=medium#firstpuppy`
  --> http:// is the non-secured protocol.
  --> localhost is the domain name.
  --> 5000 is the port.
  --> animals/puppies is the path.
  --> ?onlycute=1&size=medium is the query string that provides arguments
                                 that modify the request.
  --> #firstpuppy is the anchor tag that we jump into when we get the response.
	* `https://en.wikipedia.org/wiki/List_of_HTTP_status_codes#4xx_Client_Error`
  --> https:// is the secured protocol.
  --> en.wikipedia.org is the domain name.
  --> wiki/List_of_HTTPstatus_codes is the path.
  --> #4xx_Client_error is the anchor tag that allows us to jump to that.
```

* Can a server use more than 1 port?

```
  --> Yes
```

* Why is https different than http?

```
  --> https ensures that all your communication between the browser and the website are encrypted whereas http doesn't.
```

* How does a server interpret the following url's query paramter.  What data structure does it create on the server?

```
  --> http://locahost:5000/animals?puppies=fido&puppies=max&puppies=moxie
The server created the 

```

__HTTP Request/Response__

* Name at least 4 http verbs

```
GET, POST, PUT, DELETE
```

* What is each verb useful for in your own words

```
GET allows us to get the data from websites.
POST allows us to post information to websites.
PUT allows us to update the information on websites.
DELETE allows us to delete the content on websites.

```

* What does idempotent mean?

```
Idempotent means that the content doens't change on websites. 
When we send a GET request to a website, we will not change anything on the server side. 
```

* Name the 5 http status code ranges.  What are they used for in general?

```
1XX - Be patient. We are processing your stuff.
2XX - You got what you need. Now, be gone.
3XX - You are knocking on the wrong door.
4XX - It's not my fault. You need to get your stuff together.
5XX - OK! Now, it's my fault; I have a problem.
```


* If a server returns a http status code of 301 and a location of `https://www.google.com/`, what does the browser do?

```
Status 301 means the site has moved permanently.
When the broswer gets the 301, it will get the new location through the response header, and then it will send another request to that new location.
```

* For the following HTTP headers, decide if the following header is used for requests, responses or both:
	* Accept
```
REQUEST
```
	* Content-type
```
BOTH
```
	* User-agent
```
REQUEST
```
	* Set-cookies
```
RESPONSE
```
	* Cache-control
```
BOTH
```
	* Cookie
```
REQUEST
```
* Is the following a http request or response?  How do you know for each?

```
This is the response because it has the server sends back the document.
```


```
HTTP/1.1 200 OK
Access-Control-Allow-Origin: *
Vary: Accept
Content-Type: text/html; charset=utf-8
Content-Length: 722
ETag: W/"2d2-Wu0We9N5g35FXWY+gOATLA"
Date: Tue, 08 Mar 2016 20:37:11 GMT
Connection: keep-alive

<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <link rel="stylesheet" href="/style.css">
    <title>Student Roster</title>
  </head>
  <body>
    <main>
      <h1>Student Roster</h1>
      
        <section>
          <h3>Daenerys Targaryen</h3>
          <span>Student Id: nys8fbohl</span>
          <h4>Hobby: Motherhood</h4>
          <img src="https://i.imgur.com/KlycRG5.jpg" alt="Daenerys Targaryen" />
        </section>
      
        <section>
          <h3>Tyrion Lannister</h3>
          <span>Student Id: njehukbohe</span>
          <h4>Hobby: Traveling</h4>
          <img src="https://i.imgur.com/fFMusdC.png" alt="Tyrion Lannister" />
        </section>
      
    </main>
  </body>
</html>
```

```
It has the HTTP verb: DELETE, so it's a request.
```


```
DELETE /students/n1vmyrw3x HTTP/1.1
Host: g22-students.herokuapp.com
Accept: application/json
Cache-Control: no-cache
Postman-Token: 0041e3c3-efdb-f0c3-b2f4-2d79f6d0f44b
```

__JSON__

* Describe what JSON is.  What is it used for.

```
JSON stands for JavaScript Object Notation. It is used for data exchange.
```


* Convert the following map into a javascript object then console log the age.

```
{ "company" : "Github", "age": 7, "categories" : "Services,Internet,Software" }
```
```
MY ANSWER:
var myObj = JSON.parse('{ "company" : "Github", "age": 7, "categories" : "Services,Internet,Software" }');
console.log(myObj.age);
```
* Convert the following to a javascript object.  Console log each company name.

```
{ "Companies":[ { "company": "Github", "age": 7, "categories": "Services,Internet,Software"},
              { "company": "Airbnb", "age": 6, "categories": "Hotels,Travel"},
              { "company": "Square", "age": 7, "categories": "FinTech,Hardware + Software,Finance"},
              { "company": "Dropbox", "age": 11, "categories": "Cloud Data Services,Storage,Web Hosting"}
            ]
}
```
```
MY ANSWER:
var myObj = JSON.parse('{ "Companies":[ { "company": "Github", "age": 7, "categories": "Services,Internet,Software"},{ "company": "Airbnb", "age": 6, "categories": "Hotels,Travel"},{ "company": "Square", "age": 7, "categories": "FinTech,Hardware + Software,Finance"},{ "company": "Dropbox", "age": 11, "categories": "Cloud Data Services,Storage,Web Hosting"}]}');

myObj.Companies.map(function(val) {
  return val.company;
});
```

* The following is javascript.  Convert the object to a string and console log it.

```
var myObj = {
  company: "Galvanize",
  age: 3,
  categories: "Education"
};
```
```
MY ANSWER:
var myObjJson = JSON.stringify(myObj);
```

__MISC__

* Describe what DNS is.

```
DNS converts the domain name to IP address.
```

* In the terminal, type `man curl`.  Look at the man page for curl.  What do the following flags do? `-v`, `-X`.  (Hint: to search for a string, type `/` then the text you want, then enter.  To quit the man page, type `q`).

```
curl -v
verbose - make the operation more talkative

curl -X
request COMMAND Specify request command to use.
```

* What is TCP/IP?  How does it interact with HTTP?

```
TCP ensures that data get send in a timely manner.

IP ensures that data are sent to the correct place.
```

* Does HTTP break the data that is being sent into small packets?  If not, what protocol is responsible for it?

```
No, I don't think so.  I think it's TCP that breaks down the data into small package.
```

