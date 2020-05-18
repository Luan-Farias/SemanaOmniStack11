<h1 align="center">Be The Hero (backend)</h1>
<p>Here is the backend of application!</p>
<p>All the backend was madden in node and the libraries used are</p>

- - - 
- express: to create the application
- cors: to permite the application to use cross-origin
- knex: a sql builder to connect with sql's database
- sqlite: the sql database that was used

<p>There are seven routes used in this application:</p>

- - -
- `base_url/ongs` (get route): this route is used to get all NGOs that exists in database and list the NGOs responsing a array json objects each with a NGO
- `base_url/ongs` (post route): this route is used to create a NGO, the route reviece a request with  a body like this and the responde is ngo_id that is used to login the NGO
```json
{
	"name":"NGO's name",
	"email":"NGO's email",
	"whatsapp":"NGO's whatsapp",
	"city":"NGO's city",
	"uf":"NGO's uf"
}
```
- `base_url/session` (get route): this route is to make session of the NGO, the route reviece the ngo_id by the header of request with a var called authorization, and if id exists in database the NGO can acess her profile
- `base_url/profile` (get route): this route is to in profile of NGO when she response with all incidents of the NGO to render the ongs incidents
- `base_url/incidents` (get route): this route is used to get all incidents in database and return the incidents in json with the NGOs informations
- `base_url/incidents` (post route): this route is use to create a incident, by the request of route is passed this body in json and by the header is passed the id of the NGO to want to create the incident
```json
{
	"title": "incident's title",
	"description": "incident's description",
	"value": "incident's value"
}
```
- `base_url/incidents/:id` (delete route): this route reviece a route param that is the id of incident and the ngo_id by the header of request like a authorization