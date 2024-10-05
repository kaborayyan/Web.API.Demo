 ASP.NET Core Web API

* only MC Model and Controller
* C# Functions will turn into a Service that can be called through JavaScript
* In MVC, the Functions were called Actions and they returned Views 
* In APIs, the Functions will be called End Points and they will return JSON data
* Web APIs also can deal with large number of users compared to MVC

### Creating A New Web API Project
* When creating a new Web API Project, you will find 2 more options
    * Use Controllers: if not checked, it won't create the usual Controller folder
    * Open API: Swagger is used for Documentation
* Remember: there are no Views. Swagger will run once you launch your project

### The default Controller
* The default Controller file will inherit from ControllerBase instead of Controller
* You'll notice that the default route is presented as Attributes inside the Controller

### Postman
* Download and install Postman
* Create a personal workspace
* Create a Collection named after the current project
* Create a new request of the Verb GET
* The address will come from the URL once you run your project, the route and the Controller name
* It should be something like this ```https://localhost:7169/api/WeatherForecast```
* To use Postman, your project should be running

### Restful API
* Short for Representational State Transfer
* Any Controller you add must inherit from ControllerBase
* ControllerBase has 5 Methods "EndPoints"
    | EndPoint | Verb              |
    | -------- | ----------------- |
    | Get      | [HttpGet]         |
    | GetById  | [HttpGet("{Id}")] |
    | Add      | [HttpPost]        |
    | Update   | [HttpPut]         |
    | Delete   | [HttpDelete]      |
* The Verb for each End Point is very important to know since the frontend will communicate through these verbs.
* If two End Points have the same verb, we must differentiate between them using the parameters
* The format foe GetById is important since ```("Id")``` will request the word Id but ```("{Id}")``` will mean that Id is a parameter
* So the most important thing is the Verb and the Parameters

### Other types of APIs
* SOAP: Simple Object Access Protocol => Older type which uses XML. Not easy to use but very secure.
* RestFul API: Can return either JSON or XML
* GraphQL API: Query Language for API

### Onion Layer Architecture
* Domain Layer - Core Layer: The Models "Classes" that represent tables in the data base + non implemented Interfaces
* Repository Layer: DbContext + Repositories "Business Logic"
* Service Layers: Services "payment, tokens ... etc" + Implementation of the Interfaces
* Presentation Layer: either MVC or API
* The first 3 layers are all Class Libraries

### The Core
* It will be the Product, The Brand and the type
