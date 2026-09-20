# postman-api-testing-selflearning
Gained hands-on experience in API testing using Postman, including testing REST APIs with GET, POST, PUT, PATCH, and DELETE methods. Practiced validating HTTP status codes, JSON responses, request parameters, headers, and authentication. Created basic API test scripts and assertions, and worked with Postman Collections, Variables, and Environments to organize and execute API test cases.

HTTP Method = Action you want to perform on server

GET -> fetch data
POST -> create data
PUT -> update data
PATCH -> partial update
DELETE -> remove data

**
GET -> No body
POST/PUT -> Needs body
DELETE -> Usually no body

my collection -> add request

https://jsonplaceholder.typicode.com/posts

GET
1) create a request - GET (link)
2) run and check status: 200 OK
3) check response - lists of posts

POST
1) create a request - POST (link)
2) go to Body -> raw -> JSON (Create Data here)
3) run and check status: 201 Created

PUT
1) create a request - PUT (link/(any id))
2) go to Body -> raw -> JSON (update data here)
3) run and check status: 200 OK
** PUT replaces full data

PATCH
1) create a request - PUT (link/(any id))
2) go to Body -> raw -> JSON (update data here)
3) run and check status: 200 OK
** PUT replaces full data, PATCH updates some fields

DELETE
1) create a request - DELETE (link/(any id))
2) run and check status: 200 OK or 204 No Content
** Deletes resource (simulation in JSONPlaceholder)

==========================================================================================================================
Query Parameters, Headers, Request Body

API = Food order

Method -> What you want (order food)
Params -> Filters (less spicy, veg)
Headers -> Instructions (language, format)
Body -> Actual order details

WHAT to do -> (GET, POST, PUT, DELETE, PATCH)
HOW to control requests -> (Headers, Params, Body)

Query Parameters

1) Create a new request GET https://jsonplaceholder.typicode.com/posts?userId=1
2) Go to Params tab and check key - value
**Filters you apply to get specific data

single query
?key=value
multiple query
?key1=value1&key2=value2
 https://jsonplaceholder.typicode.com/comments?postId=1&id=5

Extra data (filters) sent in URL

*************************************************************
Headers

Content-Type: application/json -> Tells server: "I am sending JSON data"
Accept: application/json -> "Give me response in JSON"

they dont contain the main data - they describe the request

**metadata sent with request

address -> URL
box content -> body
labels on box -> headers

*fragile/urgent/handle with care
** headers = instructions for server

*************************************************************
Request Body

POST, PUT, PATCH

Types of body:
raw (JSON) -> most common
form-data -> file upload
x-www-form-urlencoded -> form submission

Params -> filter data
Headers -> extra info
Body -> actual data

**Actual data sent to server

Online form submission
*URL -> Website
*Headers -> Instructions
*Body -> Form data you fill

=============================================================
Collections

- Collection is like a project folder where we keep all API requests

=============================================================
Mini Project 1

- Auth handling
- Token usage
- Basic validation
- Dynamic data extraction

This is how secured APIs and tested in real projects

Login -> Get Token -> Use Token -> Fetch Data -> Validate

1) Create Environment - Add variable
base_url = https://dummyjson.com
2) Create Collection - Ecommerce API Project
3) Add Request - LOGIN API- POST {{base_url}}/auth/login
4) Add scripts to extract token from response
5) Add Request - GET USER PROFILE - GET {{base_url}}/auth/me
6) Add Header - Authorization: Bearer {{token}}  Can add tests
7)  Add Request - GET PRODUCTS GET {{base_url}}/products  Can add tests
8) Save Product Id for next requests

=============================================================
Mini Project 2

E-Commerce Flow: Product -> Cart -> Validation -> Automation

- API flow (Products -> Cart)
- GET & POST requests
- Dynamic data handling
- Variables & chaining
- Test scripts & validation
- Collection Runner
- Debugging & AI usage

**If you understood this flow, you are already doing what API testers do in real projects

1) Add Request - Add to Cart - POST {{base_url}}/carts/add
2) Add tests and script to save cart_id
3) Add Request - Get Cart Details - Get GET {{base_url}}/carts/{{cart_id}}
4) Add Tests
5) Check negative conditions
Remove token
Wrong product_id
Failures teach more than success
6) Run complete Collection
