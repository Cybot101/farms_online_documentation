# FARMS API Documentation #

The following is a list of URI endpoints to access the FARMS Online API.
A valid ACCESS_TOKEN needs to be presented with all requests.

## Animals ##

> GET /animals

**Return: `animal-short[]`**

List ALL animals in farm - not recommended for mobile applications due to large data size.

> GET /animals/

Hint for animal collection category endpoints.

> GET /animals/current/

**Return: `animal-short[]`**

Lists current animals (not archived/deleted) in farm.

> GET /animals/archived/{year}

**Return: `animal-short[]`**

List animals archived in {year}

>GET /animals/{animal\_id}

**Return: `animal`**

List a particular animal with id {animal\_id}

>GET /animals/{animal\_id}/latest_records

**Return: `latest\_record`**

List latest records for animal.

>GET /animals/{animal\_id}/records

**Return: `record[]`**

List all records for animal.

>GET /animals/{animal\_id}/{record\_type}

Lists records for current animal.

**Return: `record`**

{record_type} can be

- progeny
- weights
- observations
- treatments
- tasks
- conditions
- fleeces
- movements


>GET /animals/{animal\_id}/{record\_type}/{record\_id}

List a particular record for an animal.

**Return: `record`**



#Response Frames

**animal-short**

	{
		"id": 2474,
       	"ear_tag": "0182",
       	"nlis": *nlis*,
       	"name": "Anikan",
       	"breed": *breed*,
       	"mob": *mob*,
       	"dob": "2010-07-26",
       	"gender": "m",
       	"archive": 2014,
       	"status": "alive",
		"is_favourite": true
	}


**animal**

	{
		"id": 2461,
		"ear_tag": "B0264",
		"nlis": *nlis*,
		"name": "Mia",
		"breed": *breed*,
		"mob": *mob*,
		"dob": "2010-01-01",
		"gender": "f",
		"status": "alive",
		"sire": *sire*,
		"dam": *animal-very-short*,
		"archive": 0,
		"whp_status": false,
		"is_favourite": false
	}

**latest_records**

	"latest_records": {
	   	"weight": *weight*,
	   	"observation": *observation*,
	   	"treatment": *treatment*,
		...
	}

**nlis_history**

	"nlis_history": [
			*nlis*,
			...
		],