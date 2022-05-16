# Seventh Ave

## Company official languages
- JS
- TypeScript
- Golang
- Ruby/Crystal
- Solidity

## Style Guides
1. Official JS Style Guide: JavaScript Semi-Standard, and TS Semi Standard
2. Official GoLang Style Guide: Uber GoLang Style Guide
3. Official Ruby Style Guide: The Ruby Style Guide
4. Official Crystal Style Guide: Crystal Lang Official Coding Style
5. Official Solidity Style Guide: 0xcert Solidity Style Guide

## Work submission guidlines
1. Step 1 Clone Repo locally and make a feature branch that coinsides with your jira ticket
2. If no Jira Ticket exists, create one and tag Your Flight Pilot and Head of Engineering
3. branch should be named as follows for ticket `NC-99` , `feature/NC-99`
4. When that particular ticket is complete make a pull request to your repos `development` branch
5. The peer-reviewer assigned must review within 1 business day
6. Peer reviewer will verify any tests pass, they understand the code, and it meets the appropriate style guide
7. Flight Pilot or Head of Engineering will ensure that the repo satisfies the ask in the Jira ticket
8. Head of Product will ensure that the ticket accomplishes what was intended
9. Every week whatever is in the Development Branches must be tested and either merged to main or a reason must be given why they cannot be
10. Each week each Flight will demo it's progress

## Additional Tools 
1. Pull Request will use the official Seventh Ave Pull Request Template 

```markdown
### Is this PR for a specific JIRA task? If yes, what’s the JIRA task ID?
- [ ] Yes. (*Leave this unchecked if your answer is: No.*)
<!--- Provide the exact ID of your task here (e.g., "SC-50"). -->

### Does your code compile/build without errors?
- [ ] Yes. (*Leave this unchecked if your answer is: No.*)

### Did you merge the master/develop branch into your branch?
- [ ] Master
- [ ] Develop
(*Leave this unchecked if your answer is: No.*)

### Are your changes/updates visual? If yes, insert a screenshot/GIF/video of your changes/updates.
- [ ] Yes. (*Leave this unchecked if your answer is: No.*)
<!--- Insert a screenshot/GIF/video of your changes/updates here. -->
```

2. JS Repos will use `husky`, `commitlint`, `@commitlint/config-conventional` and `lint-staged`
3. This will ensure all commits meet guidelines
4. All APIs must be documented with either `Docco`, `Swagger` or `JSDoc`
5. All Readme's must have up to date information about starting app.
6. The master doc site that will go live next week will be the source of truth for all practices of Engineering (Built with Gatsby) 


### <u>API Functional Testing Guide</u>
| Testing Category | Action Category | Action Description | 
| ---------------- | --------------- | ------------------ |
| 1. Positive Test Category | | |
| Execute Api with valid required paramaters | | |
| | Validate Status Code | All requests should return 2XX HTTP response depending on spec|
| | Validate Payload | Response should be valid JSON response and the response matches the data model |
| | Validate State of Data/System | GET Requests should not change any data, <br> <br> POST, DELETE, PUT, PATCH should modify system as expected, this can be tested by making get requested and verifying data has been Created, Updated or Destroyed |
| | Validate headers | Verify that HTTP Headers have valid information, verify nothing is leaked in the headers that doesn't belong |
| | Performance Sanity Check | Verify that data is receieved in a timely manner | 
| 2. Positive + optional parameters	| | |
| Execute API call with valid required parameters AND valid optional parameters <br> Run same tests as in Group 1, this time including the endpoint’s optional parameters <br>(e.g., filter, sort, limit, skip, etc.)|||
| | Validate Status Code | As in group 1|
| | Validate Payload | As in group 1 <br> In addition to group 1 testing check optional paramaters <br> filter: ensure the response is filtered on the specified value. <br> sort: specify field on which to sort, test ascending and descending options. Ensure the response is sorted according to selected field and sort direction.<br> skip: ensure the specified number of results from the start of the dataset is skipped <br> limit: ensure dataset size is bounded by specified limit. <br> limit + skip: Test pagination |
| | Validate State | As in group 1 |
| | Validate Headers | As in group 1 |
| | Performance Sanity | As in group 1 |
| 3. Negative Testing - valid input | | |
| Execute API calls with valid input that attempts illegal operations i.e:<br> <br> Attempting to create a resource with a name that already exists (e.g., user configuration with the same name) <br> Attempting to delete a resource that doesn’t exist (e.g., user configuration with no such ID) <br> Attempting to update a resource with illegal valid data (e.g., rename a configuration to an existing name) <br> Attempting illegal operation (e.g., delete a user configuration without permission.) <br> And so forth. | | |
| | Validate Status Code: | 1. Verify that an erroneous HTTP status code is sent (NOT 2XX) <br> 2. Verify that the HTTP status code is in accordance with error case as defined in spec |
| | Validate payload: | 1. Verify that error response is received <br> 2. Verify that error format is according to spec. e.g., error is a valid JSON object or a plain string (as defined in spec) <br> 3. Verify that there is a clear, descriptive error message/description field <br> 4. Verify error description is correct for this error case and in accordance with spec |
| | Validate Headers | As in group 1 |
| | Performance Sanity | Make sure errors are received in a timely and safe way and do not cause whole system to shut down |
| 4. Negative testing – invalid input |||
| Execute API calls with invalid input, e.g.: <br> Missing or invalid authorization token<br> Missing required parameters<br> Invalid value for endpoint parameters, e.g.:<br> Invalid UUID in path or query parameters<br> Payload with invalid model (violates schema)<br> Payload with incomplete model (missing fields or required nested entities)<br> Invalid values in nested entity fields<br> Invalid values in HTTP headers<br> Unsupported methods for endpoints <br> And so on.|||
| | Validate Status Code | As in group 1 |
| | Validate State | As in group 1 |
| | Validate Headers | As in group 1 |
| | Performance Sanity | As in group 1 |
| 5. Destructive Testing | | |
| Intentionally attempt to fail the API to check its robustness: <br>Malformed content in request <br>Wrong content-type in payload <br> Content with wrong structure <br> Overflow parameter values. E.g.:<br> Attempt to create a user configuration with a title longer than 200 characters <br> Attempt to GET a user with invalid UUID which is 1000 characters long <br> Overflow payload – huge JSON in request body <br> Boundary value testing <br> Empty payloads <br> Empty sub-objects in payload <br> Illegal characters in parameters or payload <br>Using incorrect HTTP headers (e.g. Content-Type) <br>Small concurrency tests – concurrent API calls that write to the same resources (DELETE + PATCH, etc.) <br> Other exploratory testing | | |
| | Validate Status Code | As in #3. API should fail gracefully.  |
| | Validate State | As in #3. API should fail gracefully. |
| | Validate Headers | As in #3. API should fail gracefully. |
| | Performance Sanity | As in #3. API should fail gracefully. |
