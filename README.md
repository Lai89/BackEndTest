
# Pet Store Back-End Challenge

## Description

This is an exercise to test the API PetStore in Swagger ( <https://petstore.swagger.io/#> ). Test case description can be found in the collection documentation.

## How To

In order to be able to execute the tests in Postman or Newman, do the following steps:

**<p> To execute tests with Postman: </p>**

1. Install Postman in your computer.
2. Download the Postman collection and environment from repository.
3. Export both files to Postman.
4. Execute them manually or with Postman Runner.

**<p> To execute tests with Newman </p>**

1. Install node js in your computer.
2. Download the Postman collection and environment from repository.
3. Export both files to the folder you want to use to execute the tests.
4. Open a terminal and move to the folder where Postman files have been saved.
5. Install Newman CLI via command line with the script: npm install -g newman
6. Install  Newman custom reporter HTML Extra Report with the script: npm install -g newman-reporter-htmlextra
7. Execute collection with the script: newman run BackEndTest.postman_collection.json -e PetStoreEnv.postman_environment.json -r htmlextra
8. The report will be saved as HTML in a folder named 'newman'

## Observations

- Pet Id is set as a bigInt, but Postman only read floats. That is why we have setted the id as '25' and we assert that the property is not null. This way the test still be dynamic in case we solve this question.
- I checked the response status in each of the requests. If each of the requests of the test case obtained the same response status we could have saved the test in the Test case folder in order to launch the same test for each of the requests and avoid unnecessary repetition.
- I have only save the variables I need to use in the following tests. For the PUT requets, for example, we only need the elements we want to change, that is 'Id' and 'status'.

## Next Steps

- Find a solution for the Id that cannot be stored as a variable.
- We could validate updating inexistent pet properties for requests 1.2 and 1.4.
- As the collection grows and we use the same variables or methods for multiple requests, we can store these elements in the test scenario folder so we avoid unnecessary repetition.
- We could also create an external JSON file in order to use different data sets for the tests.
- We could move the tests to Rest Assured, as it is a more complete framework for coding.
- We can add conditions to test to log messages in console in order to made the tests more traceables.