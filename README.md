#Card Saver

This is a quick and semi dirty contact manager! 
It's intended purpose is to have all contacts/business cards 
saved into one place! 

I made this for my company Fuzzi Studio for our trip to GDC!

##How to Run It

####Set Up:

* Add a `.env` file to the api folder. You can simply rename `.env-sample` to `.env`
* In the dashboard folder under `src/enviornments` edit both files to reflect your company name!
    * **NOTE:** In a production environment (Which the docker files will build by default) you need to make sure you have the proper api path set! 
* Adjust the logo.png in `src/assets/static/images` to be your logo!

##### When the project is running:

* Using curl or postman, run the following endpoint to add a user `POST {Your URL}/api/v1/users/` with the JSON blob and headers below!
    * **NOTE:** The default URL is `http://localhost:9001`

`Headers: token:'YOUR SECRET KEY IN THE ENV FILE'`

```$xslt
{
	"user":{
		"firstName":"Matthew",
		"lastName":"Willard",
		"email":"matt@fuzzistudio.com",
		"password":"Some_Super_Sweet_Password!"
	}
}
```
####Requirements:

* Docker

(Not really required, but suggested! You can serve these files from anywhere!)

####Running With Docker:

* Clone the Repo
* In a terminal, navigate to API and Dashboard and run `docker-compose up`!
* You can now (after successfully building) access the dashboard at `localhost:8080` and the api at `localhost:9001`!!

* **NOTE:** If you want to build upon the project, you will need to install `ImageMagick`. This is used to downscale images before they save!

#Features to Add Someday...

* Paging to contact list
* Google Vision and some Regex to parse business card data auto magically!
* Ability to add Users