# gin-go-boilerplate

Project tree is:

- core: package that contains base implementations of every util, sdk or integration that any of the microservices need.
- microservices: package that contains all microservices of the project.
    - collections: postman file for testing purpose.
    - config: global enviroments of the applications.
    - controller: controllers of each main path of the microservice.
    - db_migrations: sql in timestamp order for updating databases.
    - lib: interface to core utils like alert(telegram), database, sdks, etc.
    - log: interface to logger utils.
    - pipes: pipes/inputs of each endpoint in the routes.
    - repository: database communication for the controllers. There are generic functions like Item, Items, NewItem, UpdateItem, RemoveItem and custom functions that let you create your own sql script.
    - routes: endpoints of the microservice.
    - start.go: main file of the microservice.
    - startup.go: async file for starting anything that takes so much time for the microservice, for example  initialize REDIS variables from SQL database.

If you want to start any microservice, you could use two ways:
- cd microservices/{micro_name} && nodemon
- cd microservices/{micro_name} && go run *.go