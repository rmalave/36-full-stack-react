# ![CF](http://i.imgur.com/7v5ASc8.png) 36 Full Stack React

## Submission Instructions
* Work in a fork of this repository
* Work in a branch on your fork
* Write all of your code in a directory named `lab-` + `<your name>` **e.g.** `lab-duncan`
* Submit a pull request to this repository
* Submit a link to your pull request on canvas
* Submit a question, observation, and how long you spent on canvas  

## Requirements  
Build a back-end server that your front-end app draws it's initial data
from. Populate a database with sample data then configure a route that
serves the data from the database to the front-end application.

Your application should make an initial request to the server to fill it's
store with data. Use `fetch` to make the request to the server, then use
`store.dispatch` to dispatch an action that inflates the store with data.

The reducer should simply parse and return the data from the inflate action
as the state of it's store.

Refer to the [lecture app](https://github.com/codefellows/seattle-javascript-401n6/tree/master/36-asynchronous-actions/lecture)
as a reference.

```js
import reducers from './reducers';
const store = createStore(reducers);

fetch('http://localhost:3000')
.then(res => res.json())
.then(json => {
  console.log('json:', json);
  store.dispatch(inflateMovies(json));
});
```

#### Configuration  
The front-end app and the back-end server are two different servers for now.
Run the server with a command like `nodemon index.js`, and run the front-end
app with a command like `webpack-dev-server`.

##### backend/
* Make a simple bare-bones server that includes a route to retrieve
  budget information, and a route to retrieve expense information.
* Make Mongoose models to model the budget and expenses.
* Use the `cors` npm module to configure your server to be accessed
  via a cross-origin request.
* Attach a `uuid` property to the models that keeps tracks of ids as
  you've used them so far in your app. Ignore the ids MongoDB creates.

##### frontend/
* **README.md** -- with a documention about your lab
* **.babelrc** -- with all dependencies and dev-dependencies 
* **.gitignore** -- with a robust gitignore
* **src/** -- containing the front end code
* **src/main.js** -- renders the app

#### Feature Tasks 
* Create a frontend for your lab-14-two-resource-api.
 * You can also choose to to instead use a comprable REST api that does not have auth (must permit full CRUD)
* You are only required to create CRUD opperations for a single resource of your bakend
* Use react/redux best practices
* Add validation in your redux routers
* Add reporter and thunk middleware to your redux store
* make async action creators for making ajax request to your backend
* make sync action creators from updating your app store

## Stretch Goals
* Write your application up so it makes `POST` requests to the server
  then budgets and expenses are created so they're really saved in the
  server database.

####  Documentation  
Write a description of the project in your README.md
