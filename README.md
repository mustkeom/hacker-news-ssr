### Project Title and Overview
This project is created by server side rending with reactjs. The templetes are created at server side and sent back to client.

### Purpose and Need
You can understand the flow and setup of SSR app by following up this project. This can be considered as sheed project and 
can be expended to any scale. 

### Benefits and Costs
Search engines can crawl the site and therefore better SEO support than client side rendering.
The initial page load is faster than client side rendering.

### Expected Outcomes:
1. Server side Rendering with custom setup -- No third party plugin is used
2. Semantic design
3. Unit tests cases (tests if props are correctly passed, childrens are available, If mock click event works fine. file-name= [__tests__]). A custom setup to support Test cases is intigrated.
4. Upvote - You can add as many upvotes as you wish.(Api mocked)
5. Hide functionality to remove the news from user’s view. (Also created action that can be intigtated with api )
6. Prev | Next link should get the relevant data and all paginated urls should be bookmarkable.

### Design strategy
Mobile first design

### Implementation Method and technology stack
This project hosts a intermediate server, generate all the templates at server side as requested by client/browser and send them back to 
client. These templates are sent as plain html and are hydrated at client side by methods proided by reactdom.
Below is the list of Technology, library, packages etc used to create this project.


## Node.js
To create JavaScript runtime environment that can executes JavaScript code outside a web browser ie:server

## Express.js
This package is used to create a intermediate server which listen to client route requests and reroute these requests to a routing 
library such as static router and send the content back to client/browser.


## React.js
This javascript library is used for building user interfaces aka components at server side and as well as at client side.

## Webpack
Webpack is used to bundle the assets of project. There are two seprate files one configuration for client assets and another is 
for server assets. Both files have diffent entry and output points. Both files share base configuration form a webpack.base.js
file which is shared/common between both.

## Babel
For transpilation of code babel is used. This transpiler is used in conjunction with webpack. Transpiling is targeting the last 2 versions 
of browsers. It means all advance/ES6/ES7 code will be transpiled to a code which browser can understand. For loading css files
raw loader is used. And for static assets like css files / images a webpack loaded url-loader is used.

## nodemon
Restarting the application when file changes in the directory are detected.

## redux react-redux
Redux is used as application state container. This application has two redux store one for each the client side and the server side. We build a standalone store at server side and this store will fill data to our react component at server side. Once our html is build, it is sent back to client by express server along with the stringified data of server store.
At client side we have all the components rendereded in client page. Now our requirment is to hydrate our app and give it the life. Bind all the javascript and events. For that we build the same html at client side by using the store data passed by server. So we pass this
store json data which comes form server, to client store as initial state. And once element tree is build at client side it take over the html sent by server.

## Redux-thunk
To dispatch actions other than object. ie - functions

## immutable
This package is used to achieve immutibility in redux store.

## axios
To make api requests. We have two diffrent domain for each server and client. Whenever client sent request they are sent to our intermediate server that is our host server. Now this server redirects these client requests to api server. On the other hand host server can directly send the api calls. For this reason we need two diffrent api paths. 

## express-http-proxy
This package is used to proxy the client api call to api server from our host server.

## react-bootstrap
UI framwork

## react-helmet
To create dynamaic meta and styles based on dynamic content or route.

## react-icons
Icons are used from this library

## react-router-config And react-router-dom
To support serverside rendering StaticRouter is used and for browser browserRouter is used.

## serialize-javascript
To sanatise the html sent by server. And to nullify the XSS attacks

## npm-run-all
To run multiple commands parallelly



# Run project

Below command will run a development server. And project will run on localhost:3000
npm run dev

Below command will run test coverage for test cases
npm run test

Below command is to deploy the code at heroku
npm start









