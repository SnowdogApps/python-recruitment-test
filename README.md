# Snowdog Python Recruitment test
Implement a simple Pokemon database with REST API using Django framework. 


### Task 1
Fork this repository and prepare the environment.

### Task 2
Implement endpoints:

`POST /catch`
The request body will contain a Pokemon name. The caught Pokemon should be saved in the database. The response should contain the id of the record created in the database.
*example request*
`POST /catch`
```json
{
	"name": "Pikachu"
}
```
*example response*
```json
{
	"id": 42,
	"name": "Pikachu"
}
```

`GET /pokemon/<id>`
Should return the Pokemon record from the database.
*example request*
`GET /pokemon/42`
*example response*
```json
{
	"id": 42,
	"name": "Pikachu"
}
```


### Task 3
Use https://pokeapi.co/ to fetch additional data: forms and types during the processing of the `POST /catch` request. Modify the database to allow to save additional data.
If a user tries to catch a Pokemon with a name that doesn't exist in PokeAPI, return a response with an error.
`GET /pokemon/<id>` should return all the data from the database.
*example response*
```json
{
	"id": 42,
	"name": "Pikachu",
	"forms": [
	  	{
	  		"name": "pikachu",
	  		"url": "https://pokeapi.co/api/v2/pokemon-form/25/"
	  	}
	],
	"types": [
	    {
	    	"slot": 1,
	      	"type": {
		        "name": "electric",
		        "url": "https://pokeapi.co/api/v2/type/13/"
	      }
	    }
	]
}
```

### Task 4
[Fair Policy](https://pokeapi.co/docs/v2#fairuse) points out that requests should be cached. Please implement such a cache mechanism.

### Task 5
Implement a `GET /pokemon` endpoint that will allow to fetch a list of Pokemons filtered by type.
*example request*
`GET /pokemon?type=electric`
*example response*
```json
[
	{
		"id": 42,
		"name": "Pikachu",
		"forms": [
		  	{
		  		"name": "pikachu",
		  		"url": "https://pokeapi.co/api/v2/pokemon-form/25/"
		  	}
		],
		"types": [
		    {
		    	"slot": 1,
		      	"type": {
			        "name": "electric",
			        "url": "https://pokeapi.co/api/v2/type/13/"
		      }
		    }
		]
	},
	{
		"id": 43,
		"name": "Voltorb",
		"forms": [
		  	{
		  		"name": "voltorb",
		  		"url": "https://pokeapi.co/api/v2/pokemon-form/100/"
		  	}
		],
		"types": [
		    {
		    	"slot": 1,
		      	"type": {
			        "name": "electric",
			        "url": "https://pokeapi.co/api/v2/type/13/"
		      }
		    }
		]
	},
]
```

### Task 6
Prepare a basic test of endpoints.

### Task 7
Deploy the app with AWS, Heroku or another service.

## Rules:
* Commit changes after every task.
* Include a README file with notes on application setup so we can run it ourselves.