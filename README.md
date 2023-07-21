<h1 align="center">Bliven ERP</h1>
<p align="left">This is a setup guide is for the application in a local development setup. This application comprises 3 parts: frontend React.js app, backend Express.js app, and
PostgreSQL database</p>
<h2>Pre-requisites</h2>

- Download and install the latest version of the Node.js runtime environment from the official website.

- Download and install the PostgreSQL database from the official website. At the time of installation keep a note about the database username, password, and port
number.

- Type command: npm install --global yarn. It will install yarn package manager globally on your machine.

<h2>STEP 1</h2>
<h3>Database - PostgreSQL</h3>

- After installing PostgreSQL you have to create a database. To create a database open psql command shell from and type: CREATE DATABASE erp;
Here's a tutorial on how to create a database: https://www.tutorialspoint.com/postgresql/postgresql_create_database.htm

- Keep remembering your database username, password, port, and created database
name. It’ll be needed later in the backend part to set up the environmental variable in
.env file.

<h2>STEP 2</h2>
<h3>Backend - Express/Node.js</h3>

- Navigate into the backend folder ‘backend’ from your command prompt/terminal.

- Type command: yarn. It will install all the required libraries and packages required for the backend. You can as well use the npm install command instead of yarn.

- You will find a .env file in the root directory of the backend ‘backend’ and set appropriate values for all the variables. To do this you have to edit the .env file and change all the variables accordingly. The .env file will look like this:
    JWT_SECRET = #type your secret word here#
        Example: JWT_SECRET = my-secret
    DATABASE_URL=postgresql://username:password@localhost:port/database_name
        Example: DATABASE_URL=postgresql://postgres:admin@localhost:5432/erp
    HOST = #For Image Host#
        Example: HOST = http://localhost
    NODE_ENV = #runnig environment#
        Example: NODE_ENV = development

- Type command: yarn prisma migrate dev. It will create the required database table and data in the PostgreSQL database that you have installed previously. Your admin and login data will be generated in this step.

- Type command: yarn start. It will start the backend server on http://localhost:5000/

<h2>STEP 3</h2>
<h3>Frontend - React.js</h3>

- Navigate to the frontend folder ‘frontend’ from your command prompt/Terminal.

- Type command: yarn. It will install all the required libraries and packages required for the front end. Be patient, it’ll take some time.

- You will find a .env file in the root directory of the front and set the variable
REACT_APP_API = http://localhost:5000/v1/

- Type in your terminal command: yarn start. It will start the frontend server on http://localhost:3000/

- Now go to your browser and type http://localhost:3000/ in your search/address bar and hit enter. You have successfully installed the Bliven ERP on your computer/machine!


