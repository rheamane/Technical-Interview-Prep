Application Programming Interface (API): Communicates between 2 computers/servers
RESTful: Representational State Transfer

RESTful API: Organizes data entities or resources in unique URIs: Uniform Resource Identifiers
A Client can get data by making an HTTP request
- GET: READ
- POST: CREATE
- PATCH: UPDATE
- DELETE: DESTROY

Client gets back a response:
- Status Code:
	- 2** : Good
	- 3** : User error
	- 4** : Server Error/Broken
- Response headers
- Response Body: Usually in JSON

This architecture is stateless:
Both bodies do not need to store an information about each other
Every request-response cycle is independent/unique

---
