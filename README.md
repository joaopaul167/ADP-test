# ADP Innovation Labs Pre-Interview Assignment
Hello potential future coworker! :D

We're looking forward to having some great days working on creating new projects, debugging issues, planning applications, solving problems, and all of the other fun things we do here in Innovation Labs - together with you!

But before that, let's see if you can demonstrate some stock skills you'll need to be successful in this position :)

If anything isn't specifically called out here, feel free to be as inventive as you like - no pressure to adhere to any strict rules. Our primary goal is to know that you generally understand web application principles.

Have fun!

Task
Create a simple JavaScript (nodejs) application that makes an HTTP GET request to

https://interview.adpeai.com/api/v2/get-task

This endpoint will provide you with an id and an array of transactions data.
```json
{
  "id":"81728ed3-25ff-473c-9491-4a2026dadd8c",
  "transactions": [
    // This will be an array of transactions
  ]
}
```
Each transaction object within the array has the following shape (details may be different):

```json
{
  "transactionID": "TX_691",
  "timeStamp": "2021-05-25T17:35:19.460Z",
  "amount": 1060,
  "type": "alpha",
  "location": {
    "name": "New York, New York",
    "id": "L027145"
  },
  "employee": {
    "name": "Abram W Choi",
    "id": "SED133",
    "categoryCode": "red"
  }
}
```
With this data:

Get all the transactions of last year's top earner. This means find the employee with the highest sum total of amount within the prior calendar year. Prior calendar year means, if it is currently 2022, we want only to consider transactions in 2021.
With last year's top earner's transactions get the transactionIDs where the type is alpha.
Once you have an id and an array of transactionIDs (should be an array of strings), make an HTTP POST request to

https://interview.adpeai.com/api/v2/submit-task

with a JSON POST body including the properties id and result.

Body example:
```json
{
  "id": "81728ed3-25ff-473c-9491-4a2026dadd8c",
  "result": ["TX_002", "TX_003"]
}
```
The submit-task endpoint will return as follows:

Status Code	Description
200	Success
400	Incorrect value in result; no ID specified; value is invalid
404	Value not found for specified ID
503	Error communicating with database
If you get 200, you are done!

## Evaluation Criteria
the candidate should not use frameworks like React, Angular, and Express, or bootstraps like create-react-app and angular cli. Libraries are allowed, just not frameworks.
- a reviewer should be able to clone this repository (e.g. from Github, Bitbucket)
- a reviewer should be able to run npm install and get all required dependencies
- a reviewer should be able to run npm start to run the application
- a reviewer should be able to see that calls are successful
  
the work should be free of CORs errors when running on http://localhost

Code is commented where appropriate

Report any bugs or issues you find (there shouldn't be any, but who knows ;))


# My development process:

 - create the main program
 - add a main function
 - add a get function to retrieve data from the API
 - process data:
    - get all the last years transactions
    - create map to add total amout for each employee in that year
    - get the highest one
    - get all his transactions with type == 'alpha'
  - add a post function to send data to the API
  - evaluate response
  - end main program

# Commands to get the project, build and run

Requirements: 
-  [npm](https://www.npmjs.com/)
-  [node](https://nodejs.org/en)
-  [git](https://git-scm.com/downloads)

To download the repo:
```bash
  git clone https://github.com/joaopaul167/ADP-test.git
```

To install all dependencies:
```bash
  npm i
```

To run the project:
```bash
  npm start
```

