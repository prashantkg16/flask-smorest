OS - Kernel and File/Program
    Kernel - it is usually interacts with and control the hardware

Dockers - Everything except Kernel
Docker images are snapshot of what inside in Container
> docker build -t rest-apis-flask-python .

Note: 
* -t rest-apis-flask-python flag is optional, but tags the image
* . means "the current directory

For rest-apis-flask-python image, Run container for exposed port
> docker run -p 5005:5000 rest-apis-flask-python

For run background (-d)
> docker run -d -p 5005:5000 rest-apis-flask-python

continuous update the changes in docker 
for Linux
> run -dp 5000:5000 -w /app -v "$(pwd):/app" flask-smorest-api

For window
> 

python-dotenv library: - load environment variables and use the .flaskenv file
.flaskenv
FLASK_APP=app
FLASK_DEBUG=True

Flask Rest API
> Flask-Smorest - similar to Flask-RESTful 

* Flask-Smorest uses flask.views.MethodView classes registered under a flask_smorest.Blueprint
* Flask-Smorest uses flask_smorest.abort to return error responses
* uses marshmallow for serialization and deserialization
* define marshmallow schemas that represent incoming data (for deserialization and validation) and outgoing data (for serialization). It uses these schemas to automatically validate the data and turn Python objects into JSON
* provides Swagger (with Swagger UI) and other documentations
> Flask-RESTful -

* Flask-Smorest uses flask.views.MethodView classes registered under a flask_restful.Resource
* manually returning the error JSON and error code
> RESTX -

* Doesn't use marshmallow