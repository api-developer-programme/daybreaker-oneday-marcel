## As a service technician I would like to get the standard minimum outdoor temperature for an installation address in France, so that I can scale the heating system properly

### Background /  Description

We need to add a new microservice to our existing Vaillant API environment to get the standard minimum outdoor temperature for a given address that can be used by our service technicians to recommend a heatpump-based heating system to the customer.

The service should take an address as argument and use Google Maps APIs ([Geocoding](https://developers.google.com/maps/documentation/geocoding/start), [Elevation](https://developers.google.com/maps/documentation/elevation/start)) to retrieve the altitude in meters.
In the next step the determined altitude has to be used to calulate the standard minimum outdoor temperature.

The standard minimum outdoor temperature is the sum of the base minimum outdoor temperature for the given postalcode prefix (provided in mongo-seed/france-min-outdoor-temperature.json) and the provided offset for the determined elevation (mongo-seed/france-elevation-offset.json).

### Definition of Ready

* Datasets of standard minimum outdoor temperatures are provided
* Bitbucket repository is available
* Google API key is provided: ```<YOUR_GOOGLE_MAPS_API_KEY_HERE>```

### Definition of Done

* Service is tested adequately with a testing framework of your choice
* All changes are committed and pushed to a Git repository in our corporate Bitbucket instance
* The application can be built without errors and produces a potentially shippable artifact (e.g. a JAR, WAR or Docker container)

### Acceptance criteria

* The service is written in **Java**
* The service exposes its functionality via a **RESTful API**
* The API accepts an **address as argument/**s - either as a single or split into multiple parameter (will only be tested with french addresses)
* The API returns the **standard minimum outdoor temperature as response**.

### Out of Scope

* Any kind of authentication or authorization (e.g. OAuth2)

### Nice to have

* The API is documented **for developers of Vaillant partner organizations**
* async REST calls
