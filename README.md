#### What is API?
API testing is a type of software testing that involves testing the application programming interfaces (APIs) directly. APIs are the communication protocols and tools that allow different software applications to communicate with each other. API testing ensures that the APIs work as expected in terms of functionality, reliability, performance, and security.
#### Postman Introduction
Postman is an API client used to develop, test, share and document.It is utilized for backend testing, in which the endpoint URL is entered, a request is sent to the server, and the server responds. Swagger, an API template, can be used to achieve the same goal.
##### Request
A request consists of the following components: HTTP, HTTPS, header, body, or payload, and the entire URL, including any arguments or keys.
##### Collection
A collection is a repository/folder in which we can save all our requests.
##### How to create Collection & Request
* Step 1: Once your postman is open, select the collection option from the sidebar on the left.
* Step 2: You will see + button click on this button and set an name you want
* Step 3: Creating collection you add a request in collection repository
* Step 4: Click 3dot(…) on collection you create then choose add request from dropdown
* Step 5: Set a name of requset then choose a method from dropdown and given your link
* Step 6: Once you have a complete request, click on the “Send button” and see the response code. A 200 OK code stands for successful operation. In the image below you can see that we have successfully hit the URL.
##### Environment
An environment is a set of one or more variables that you can reference when sending requests, writing pre-request scripts, or writing post-response scripts. You can create environments for the different types of work you do in Postman.
##### How to create Environment
* Step 1: To open the environment editor, select the name of an environment.
* Step 2: Select Environments from the menu on the left, then click to start a new environment.
* Step 3: Assign your environment a name and initialize it with any necessary variables (you can also provide variables for the environment at a later time).
* Step 4: Adding environment variables.Enter a name for your variable, and specify its Initial and Current values. By default the current value will copy the initial value.
* Step 5: Creating your environment save it.
##### Accessing environments
You can access your environment variables from Postman and from your request elements, including the URL, parameters, body data, and test scripts.
To use the variables in an environment, select it from the environment selector at the top right of Postman.

If your requests include environment variables, Postman performs all of your requests against the environment you specify using the environment selector, treating it as the active environment.

Use the name of the environment variable, surrounded in double curly braces {{base_url}}, to reference it in a request.

Save and click on the “Send button” and see the response code. A 200 OK code stands for successful operation. In the image below you can see that we have successfully hit the URL.

## Postman | Newman | Report
####  Newman:
Newman is a command line interface tool which allows you to run a postman collection directly from the command line.
##### Install Newman
Prerequisite
* NodeJs
  To check if the node is installed or not, simply check the node version on your cmd using the below command.
```dtd
$ node -v
```
If not download node js from here
Link: https://nodejs.org/en/)

After completing the node installation,you can install Newman from your cmd using the below command.
```dtd
npm install -g newman
```
For confirmation you can also check the version in your cmd
```dtd
newman -v
```
Running Collections Using Newman
To run a collection through Newman, we have two ways to proceed.

* URL of the hosted collection
* The collection in JSON format.

**URL of the  hosted collection**
* Step 1: Click on the 3 dots(…) besides the collection name.
* Step 2: Click on Share select json link and copy the link
* Step 3: Open your CMD and paste the link with below command
```dtd
newman run <your JSON link>
```
**The collection is in JSON format**
* Step 1: Click on collection and export it to(recommended) JSON format
* Step 2: Save the json file in your system and remember the directory.
* Step 3: Open a command prompt and run the collection using Newman run command
```dtd
newman run "Path/CollectionName.json"
```
**Newman Integration With Environment Variables**
* Step 1: Choose Environment based on your collection.Click three dots(…) and select export from dropdown.
* Step 2: Save the json file in your system and remember the directory.
* Step 3: Open a command prompt and run the collection using Newman run with enviroment command
```dtd
newman run "Path/CollectionName.json" -e Path/EnvironmentName.json
```
**Report Generation Using Newman**

There are some custom node modules available for generating Newman test execution reports. We will walk through an example using a newman-html-reporter.
To generate report need to separately install newman report file using below command
```dtd
npm install -g newman-reporter-htmlextra
```
Open a command prompt run the collection and generate report using Newman run with enviroment command
```dtd
newman run "Collection Link" -e "Path/EnvironmentName.json" -r cli,htmlextra
```
After Enter you successfully generate a report with newman folder