# Workshop: Creating an API with Express for managing tracks and albums 🎵

[⬅ Version française](./README-FR)

## Objective
Learn how to create a simple REST API with Express.js by gradually implementing the CRUD features (Create, Read, Update, Delete). This project will be done in a single file (index.js) to simplify the handling. The objective is also to encourage autonomy by consulting the official documentation.

## Prerequisites
Have Node.js installed on your machine. If not, download it from Node.js Official.
Install Express via npm.

## Step 1: Initialize the project
Create a folder for the project and initialize it:

```bash
npm init -y
```

Install Express:

```bash
npm install express
```

Define the module type in your package.json:
```json
"type": "module"
```

Create an index.js file that will be used for all development.

## Step 2: Set up an Express server
In the index.js file, configure a minimal Express server.

Check out the documentation to start a server:
👉 [express hello world](https://expressjs.com/en/starter/hello-world.html)

Create a default route (GET /) that returns a simple response to verify that the server is working.
Example: "Welcome to my Express API".

Start the server with the following command and test your route in a browser or with a tool like Postman:

```bash
node --watch index.js
```

## Step 3: Adding the tracks routes

### Goal: Implement the following routes:

- GET /tracks: Get all tracks.
- GET /tracks/:id: Get a track by its ID.
- POST /tracks: Create a new track.
- PUT /tracks/:id: Modify an existing track.
- DELETE /tracks/:id: Delete a track.

### Rules :

- :white_check_mark: Response bodies should be JSON.
- :white_check_mark: Request bodies should be JSON.
- :white_check_mark: `PUT` and `DELETE` request should return `204 no content`.
- :white_check_mark: `POST` request should return `201 created` with the associated created resource.

### Steps:

Add a static list of tracks (in-memory array) to your index.js file.

Example:

```js
const tracks = [
{ id: 1, title: 'Track 1', albumId: 1 },
{ id: 2, title: 'Track 2', albumId: 1 }
];
```

Implement each route in the file.

See the documentation on routes:

👉 [Express Routing](https://expressjs.com/en/guide/routing.html)

### Tips:

- For GET /tracks: Return the full list with res.json(tracks).
- For GET /tracks/:id: Use req.params to retrieve the ID and look up the corresponding track in the array.
- For POST /tracks: Add a track to the array and handle the data sent by the client via req.body.
- For PUT /tracks/:id and DELETE /tracks/:id, update or delete a track based on the ID.

### Highlights:

Enable express.json() middleware to read JSON data from request bodies.
👉 [Express JSON Middleware](https://masteringjs.io/tutorials/express/express-json)

## Step 4: Adding Album Routes

### Goal: Implement CRUD functionality for albums:

- GET /albums: Get all albums.
- GET /albums/:id: Get an album by its ID.
- POST /albums: Create a new album.
- PUT /albums/:id: Edit an existing album.
- DELETE /albums/:id: Delete an album.

### Steps:

Create a static list of albums similar to the one for tracks.
Add routes for each action in index.js.
Implement a specific route to retrieve the tracks of an album (GET /albums/:id/tracks).

Related documentation:

👉 [Express Params](https://dev.to/ericlecodeur/nodejs-express-part-2-route-parameters-3n12)

## Step 5: Data improvements and persistence

### Goal: Add advanced features like:

A basic validation of the data sent (for example, check that the title of a track is not empty before adding it).
Handle errors if a track or album is not found.

Helpful documentation:

👉 [Error Handling](https://dev.to/srishtikprasad/error-handling-with-express-40pk)

## Step 6: API Testing
Test all routes with a tool like Postman, Insomnia, or using fetch/Axios in a simple front-end application.
Check that the data returned is correct and that all CRUD features work.

## Step 7: Going Further
Code Structuring: Once all features are working, think about structuring the project (separate routes, controllers, models).
Additional documentation:
👉 [Express architecture best practice](https://blog.treblle.com/egergr/)

## Conclusion
Congratulations 🎉! You have built a working REST API from scratch. You have learned how to configure Express, implement routes, and manipulate data on the server side. Moving on, you can dive deeper by exploring databases like MongoDB or PostgreSQL for robust data persistence.
