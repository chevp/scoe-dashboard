
# Scoe Dashboard

## Overview

Scoe Dashboard is a Java-based server built using the **Quarkus** framework. It serves as an endpoint for **Scoe-scene** requests and provides a visualization interface. The server facilitates rendering and displaying interactive 3D scenes based on the **scoe3.json** structure, with an easy-to-use web UI for the users. 

This project is intended for use cases where users want to visualize and interact with 3D scenes, and optionally load data from external sources like a database.

## Features

- **Scoe Scene Endpoint**: The server provides an API endpoint that serves the 3D scene data in the `scoe.json` format.
- **Qute-based UI**: The UI is built using **Qute** templating engine to display the scenes in an interactive, easy-to-navigate dashboard.
- **Easy Scene Visualization**: Dynamically visualizes the **scoe-scene** configuration defined in `scoe.json` through Three.js integration.
- **RESTful API**: Exposes REST endpoints to manage scenes, allowing users to interact with the server and control the content programmatically.

## Requirements

- **Java 17+** for the Quarkus framework.
- **Maven** for building the application.
- **Node.js** and **npm** (if needed for additional web-based visualizations like Three.js).
  
## Setup

### 1. Clone the repository

```bash
git clone https://github.com/chevp/scoe-dashboard.git
cd scoe-dashboard
```

### 2. Build the Quarkus app

Ensure you have Maven installed and set up. Then build the project using Maven:

```bash
./mvnw clean install
```

This will compile and package the application.

### 3. Configure the Server

Make sure to configure your `application.properties` to set up the correct paths for your **scoe.json** files, databases, or any external resources.

Example configuration:

```properties
quarkus.http.port=8080
quarkus.datasource.db-kind=h2
quarkus.datasource.jdbc.url=jdbc:h2:./target/testdb
```

### 4. Run the Server

Once everything is set up, run the application using:

```bash
./mvnw quarkus:dev
```

This will start the Quarkus server in development mode. The server will be running at `http://localhost:8080`.

### 5. Access the Dashboard

Open your browser and go to `http://localhost:8080` to access the Scoe Dashboard.

## API Endpoints

- **GET /api/scene**: Returns the current 3D scene in `scoe.json` format.
- **POST /api/scene**: Allows updating the 3D scene by sending a new `scoe.json` payload.
- **GET /api/nodes**: Fetches all nodes defined in the current scene.
- **GET /api/node/{id}**: Fetches the details of a specific node.

## Development

For making changes to the server or the front-end dashboard:

- Modify the Qute templates under the `src/main/resources/templates/` directory.
- For API endpoints, make changes to the corresponding classes in the `src/main/java/` directory.
- If you're integrating with Three.js or other client-side libraries, you can make changes in the `src/main/resources/static/` directory.

### Frontend Integration

If you are using Three.js to visualize the `scoe.json` scene on the frontend, ensure that the client-side logic is integrated and points to the correct API endpoint to fetch the scene data.

## Contributing

If you'd like to contribute to **Scoe Dashboard**, feel free to fork the repository and create a pull request. Please follow these guidelines:

- Write clear commit messages.
- Ensure your changes are thoroughly tested.
- Make sure the code follows Java and Quarkus best practices.

## License

Scoe Dashboard is open-source software released under the MIT license.

