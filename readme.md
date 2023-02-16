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
> docker run -dp 5000:5000 -w /app -v "/c/Documents/yourproject:/app" flask-smorest-api

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

#### Smorest Blueprint is same as Flask Blueprint, only description is extra
MethodView - These are classes where each method maps to one endpoint

Without lazy="dynamic", the items attribute of the StoreModel resolves to a list of ItemModel objects.
With lazy="dynamic", the items attribute resolves to a SQLAlchemy query

* A key benefit is load speed. Because SQLAlchemy doesn't have to go to the items table and load items, stores will load faster.
> store.items.all()

* A key drawback is accessing the items of a store isn't as easy. 
However this has another hidden benefit, which is that when you do load items, you can do things like filtering before loading.
> store.items.filter_by(name=="Chair").first()

>  Flask-JWT-Extended that a refresh token is required with @jwt_required(refresh=True)

#### Alembic and Flask-Migrate
changes directly to the models without module will make out of sync
* Alembic to detect the changes to the models
* tracks each of these migrations over time
Initiate DB - This will create a migrations' folder inside your project folder
* flask db init
Migrate Command - create the migration file
* flask db migrate
upgrade Command - apply the changes
* flask db upgrade

#### git reset - "modes": soft, mixed, hard, merge and keep
> SOFT - You will remove the last commit from the current branch

git reset --soft HEAD~1
> HARD - Lose all uncommited changes and all untracked files. changes will stay in your working tree. Also, the changes will stay on your index

git reset --hard HEAD~1
> MIXED - Default mode and quite similar to soft. keep the changes in your working tree but not on the index (use git add)

git reset HEAD~1
> KEEP - Aborts the reset if one or more of these files has uncommited changes. It basically acts as a safer version of hard

git reset --keep HEAD~1
