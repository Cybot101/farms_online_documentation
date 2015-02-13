# FARMS API Documentation #

The following is a list of URI endpoints to access the FARMS Online API.
A valid ACCESS_TOKEN needs to be presented with all requests.

## Animals ##

> GET /animals/

**Return: `animal-short[]`**

List ALL animals in farm - not recommended for mobile applications due to large data size.

> GET /animals/current/

**Return: `animal-short[]`**

Lists current animals (not archived/deleted) in farm.

> GET /animals/archived/{year}

**Return: `animal-short[]`**

List animals archived in {year}

>GET /animals/{animal_id}

**Return: `animal`**

List a particular animal with id {animal_id}

>/animals/{animal_id}/records

**Return: `record[]`**

List all records for animal.

>/animals/{animal_id}/{record_type}

Lists records for current animal.

{record_type} can be

- weights
- observations
- treatments
- tasks
- conditions
- fleeces
- movements

>/animals/{animal_id}/progeny

**Return: `animal-short[]`**

List progeny (children) of current animal.




**Response Frames**

**animal-short**

	{
		"id": 2474,
       "ear_tag": "0182",
       "nlis": {
           "id": 150,
           "number": "",
           "eid": "000121722679"
       },
       "name": "Anikan",
       "breed": {
           "id": 45,
           "name": "Corriedale"
       },
       "mob": null,
       "dob": "2010-07-26",
       "gender": "m",
       "archive": 2014,
       "status": null
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
		"nlis_history": [
			*nlis*,
			...
		],
		"sire": *sire*,
		"dam": *animal-very-short*,
		"archive": 0,
		"latest_records": {
		   "weight": *weight*,
		   "observation": *observation*,
		   "treatment": *treatment*
		}
	}