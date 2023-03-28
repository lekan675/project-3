### MERN STACK IMPLEMENTATION
## Step 1

*Download updates for ubuntu*

`sudo apt update`

![Download updates for ubuntu](./images/sudo%20apt%20update.jpg)

*Upgrade ubuntu*

`sudo apt upgrade`

![Upgrade ubuntu](./images/sudo%20apt%20upgrade.jpg)

*Get the location of Node.js software from Ubuntu repositories.*

`curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -`

![Get the location of Node.js software from Ubuntu repositories](./images/get%20the%20location%20of%20Nodejs.jpg)


*Install Node.js on the server*

`sudo apt-get install -y nodejs`

![Install Node.js on the server](./images/install%20nodejs.jpg)

*Verify the node installation with the command below*

`node -v`

![Verify the node installation with the command below](./images/verify%20node%20installation.jpg)

`npm -v`

![Verify the node installation with the command below](./images/verify_npm_installation.jpg)

# Application Code Setup

*Create a new directory for your To-Do project*

`mkdir Todo`

![Create a new directory for your To-Do project](./images/create%20new%20directory%20todo.jpg)

*Verify the Todo directory*

`ls`

![Verify the Todo directory](./images/verify%20todo.jpg)

*Change to the Todo directory*

`cd Todo`

![Change to the Todo directory](./images/cd%20Todo.jpg)

*Initialise your project with npm init*

`npm init`

![Initialise your project with npm init](./images/npm_init.jpg)

**Install ExpressJS**

*To use express, install it using npm:*

`npm install express`

![To use express, install it using npm](./images/install%20express%20using%20npm.jpg)

*Now create a file index.js with the command below and confirm file creation*

`touch index.js`
`ls`
![Now create a file index.js with the command below and confirm file creation](./images/confirm%20index.js.jpg)

*Install the dotenv module*

`npm install dotenv`

![Install the dotenv module](./images/install%20dot%20env.jpg)


*Open the index.js file with the command below*

`vim index.js`

![Open the index.js file with the command below](./images/open%20index.js.jpg)

*Type the code below into it and save. Do not get overwhelmed by the code you see. For now, simply paste the code into the file.*

![Type the code below into it and save. Do not get overwhelmed by the code you see. For now, simply paste the code into the file.](./images/code.jpg)

*Start the server to see if it works. Open your terminal in the same directory as your index.js file and type:*

`node index.js`

![Start the server to see if it works. Open your terminal in the same directory as your index.js file and type](./images/node%20index.js.jpg)


*Open port 5000 in EC2 Security Groups*

![Open port 5000 in EC2 Security Groups](./images/Project%20MERN.jpg)

*Open up your browser and try to access your server’s Public IP or Public DNS name followed by port 5000:*

![Open port 5000 in EC2 Security Groups](./images/test%20port%205000.jpg)

**Routes**

*There are three actions that our To-Do application needs to be able to do:*

-   Create a new task
-   Display list of all tasks
-   Delete a completed task*

*For each task, we need to create routes*

`mkdir routes`

![Start the server to see if it works. Open your terminal in the same directory as your index.js file and type](./images/create%20routes.jpg)

*Change directory to routes folder*

`cd routes`

![Change directory to routes folder](./images/cd%20routes.jpg)


*Open the file with the command below*

`vim api.js`

![Open the file with the command below](./images/add%20code.jpg)

**Models**
*Change directory back Todo folder with cd .. and install Mongoose*

`npm install mongoose`

![install Mongoose](./images/install%20mongoose.jpg)

*Create a new folder models and change directory to models*

`mkdir models`
`cd models`

![Create a new folder models](./images/mkdir%20models.jpg)

*Inside the models folder, create a file and name it todo.js*

`touch todo.js`

![Inside the models folder, create a file and name it todo.js](./images/create%20todo.js.jpg)

*Open the file created with vim todo.js then paste the code below in the file*

`vim todo.js`

![Open the file created with vim todo.js then paste the code below in the file](./images/paste%20code.jpg)

*Update our routes from the file api.js in ‘routes’ directory*

`vim api.js`
`%d`

![Update our routes from the file api.js in ‘routes’ directory](./images/updated.jpg)

**MongoDB Database**

*Create Mongodb*

![Create Mongodb](./images/signup.jpg)

*Allow access to mongodb from anywhere*

![Allow access to mongodb from anywhere](./images/mongodb%20p%20allow.jpg)

*Create mongodb database*

![Create mongodb database](./images/mogodb%20DB.jpg)

*Create a file in your Todo directory and name it .env*

`vim todo.js`

![Create a file in your Todo directory and name it .env](./images/touch%20vi%20.env.jpg)

*Add the connection string to access the database in it, just as below*

`DB = 'mongodb+srv://<username>:<password>@<network-address>/<dbname>?retryWrites=true&w=majority'`

![Add the connection string to access the database in it, just as below](./images/touch%20vi%20.env.jpg)

*Update the index.js to reflect the use of .env, delete the paste the entire content*

`vim index.js`
`%d`
![Update the index.js to reflect the use of .env, delete the paste the entire content](./images/code.jpg)

*Start your server using the command*

`node index.js`

![Start your server using the command](./images/db_connected.jpg)

*Open your Postman, create a POST request to the API*

`http://<PublicIP-or-PublicDNS>:5000/api/todos`

![Open your Postman, create a POST request to the API](./images/post-postman.jpg)

*Create a GET request to your API*

`http://<PublicIP-or-PublicDNS>:5000/api/todos`

![Create a GET request to your API](./images/get-request.jpg)

**Step 2 – Frontend creation**

*Create react app in the Todo directory*

`npx create-react-app client`

![Create a GET request to your API](./images/npm%20create%20react%20app.jpg)

**Running a React App**

*Before testing the react app, there are some dependencies that need to be installed.*

`npm install concurrently --save-dev`

![Before testing the react app, there are some dependencies that need to be installed](./images/dependecy.jpg)

*Install nodemon. It is used to run and monitor the server*

`npm install nodemon --save-dev`

![Install nodemon. It is used to run and monitor the server](./images/insall%20nodemon.jpg)


*Open the package.json file in the Todo directory, then paste the code*

`vim package.json`

![Open the package.json file in the Todo directory, then paste the code](./images/package.json.jpg)

*Configure Proxy in package.json, change directory to client*

`cd client`
`vi package.json`

*Add the key value pair in the package.json file "proxy": "http://localhost:5000"*

![Configure Proxy in package.json](./images/proxy.jpg)

*Inside the Todo directory, run the command below*

`npm run dev`

![Inside the Todo directory, run the command below](./images/npm%20run%20dev.jpg)

**Creating your React Components**

*From your Todo directory run*
*move to the src directory*
*Inside your src folder create another folder called components*
*Move into the components directory*
*Inside ‘components’ directory create three files Input.js, ListTodo.js and Todo.js*
*Open Input.js file*
*Move to the src folder*
*Move to clients folder*

![Inside the Todo directory, run the command below](./images/List%20todo.jpg)

![Inside the Todo directory, run the command below](./images/input.js.jpg)

*Install axios*

`npm install axios`

![Install axios](./images/npm%20install%20axios.jpg)

*Install axios*

*Go to ‘components’ directory*

`cd src/components`

*open your ListTodo.js*

`vi ListTodo.js`

*Move to the src folder*

`cd ..`

![Install axios](./images/commands.jpg)

*Open App.js*

`vi App.js`

![Open App.js](./images/app.js.jpg)

*Copy and paste the code below into it*

![Copy and paste the code below into it](./images/App1.js.jpg)

*Open App.css*

`vi App.css`

![Open App.css](./images/app.css%20s.jpg)

*Open index.css and paste*

`vim index.css`

![Open index.css](./images/vim%20pasrte.jpg)

*Go to the Todo directory*

`cd ../..`

![Go to the Todo directory](./images/cd%20Todo.jpg)

`npm run dev`

![Todo app; ](./images/npm%20run%20dev.jpg)