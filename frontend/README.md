# Contactify - Frontend using React.JS
Welcome to the Contactify frontend part of the Full stack App repository! Here, you'll find the codebase for Contactify, a user-friendly web application crafted with React.js, tailored for seamless contact management. Contactify simplifies the process of managing contacts, offering you the ability to effortlessly create, edit, and browse your contact list. Leveraging modern web technologies like React.js, our frontend ensures a responsive and intuitive interface. Additionally, I have provide a Dockerfile to containerize the application, enabling seamless deployment across different environments. Within this repository, you'll discover Contactify, a straightforward web application developed using React.js, alongside a breakdown of its main files and functionalities for your easy navigation and understanding.

## Dockerfile Explanation
This Dockerfile serves to containerize a web application constructed with Node.js and Nginx. It facilitates the encapsulation of the application, enabling consistent deployment across various environments. Below, I'll delve into the specifics of each segment to grasp its functionality.

## Build Stage
- `FROM node:alpine as build`: This sets the base image as Node.js with Alpine Linux as its lightweight version. It creates an intermediate image named `build` for the build stage.
- `WORKDIR /app`: Sets the working directory within the container to `/app`.
- `COPY . .`: Copies all files from the current directory into the container's working directory (`/app`).
- `RUN npm install && npm run build`: Installs dependencies using npm and then builds the application.

## Final Stage
- `FROM nginx:alpine`: Sets the base image as Nginx with Alpine Linux.
- `WORKDIR /usr/share/nginx/html`: Sets the working directory to where Nginx serves files from.
- `COPY --from=build /app/dist/ .`: Copies the built application files from the build stage into the Nginx container's working directory.
- `EXPOSE 3000`: Exposes port 3000, indicating that the container will listen on this port at runtime.
- `ENTRYPOINT [ "nginx", "-g", "daemon off;"]`: Specifies the command to run when the container starts. In this case, it starts the Nginx server in the foreground.

## Usage
To use this Dockerfile, follow these steps:
1. Place the Dockerfile in the root directory of your Node.js project.
2. Build the Docker image by running:
   ```
   docker build -t your_image_name .
   ```
   Replace `your_image_name` with the desired name for your Docker image.
3. Run the Docker container using the following command:
   ```
   docker run -p 3000:3000 your_image_name
   ```
   This will run the container, making your web application available on port 3000 of your local machine.

Make sure your Node.js application is configured to run on port 3000 as specified in the Dockerfile's `EXPOSE` directive. Adjust the port number if your application uses a different port.

## File Structure and Functionalities
Within this repository lies Contactify, a straightforward web application developed using React.js, tailor-made for contact management. Here's a comprehensive overview of the primary files and their respective functionalities:

### 1. `App.jsx`

This file (`App.jsx`) is the main component of the Contactify application. It manages the state of contacts, handles modal visibility, and provides functions for fetching contacts from the backend server. Here's a breakdown of its functionalities:

- **State Management**: Utilizes React's `useState` hook to manage states for contacts, modal visibility (`isModalOpen`), and the current selected contact (`currentContact`).
- **Fetching Contacts**: Uses `fetchContacts` function to retrieve contacts from the backend server (`http://127.0.0.1:5000/contacts`) and updates the state accordingly.
- **Modal Handling**: Provides functions (`closeModal`, `openCreateModal`, `openEditModal`) to control the visibility of the modal for creating and editing contacts.
- **Rendering**: Renders `ContactList` component to display the list of contacts and a button to create new contacts. Additionally, renders a modal (`ContactForm`) for creating/editing contacts when `isModalOpen` is `true`.

### 2. `ContactList.jsx`

The `ContactList.jsx` file contains the component responsible for rendering the list of contacts. It receives the list of contacts as props and provides a callback function (`updateContact`) to handle editing contacts.

### 3. `ContactForm.jsx`

This file (`ContactForm.jsx`) defines the component for creating and editing contacts. It receives props such as `existingContact` (for pre-filled data) and `updateCallback` (to notify changes to the parent component).

### 4. `App.css`

The `App.css` file contains styles for the Contactify application.

### 5. `index.html`

The `index.html` file serves as the entry point for the web application. It includes the root div (`<div id="root"></div>`) where React components are mounted, as well as a script tag (`<script type="module" src="/src/main.jsx"></script>`) to load the main JavaScript file (`main.jsx`).

## Usage

To run the Contactify application locally, follow these steps:

1. Ensure you have Node.js installed on your machine.
2. Clone this repository.
3. Navigate to the project directory in your terminal.
4. Install dependencies by running `npm install`.
5. Start the development server with `npm run dev`.
6. Open your web browser and go to `http://localhost:3000` to view the Contactify application.

## Dependencies

This project utilizes the following dependencies:

- **React**: JavaScript library for building user interfaces.
- **react-dom**: Provides DOM-specific methods that can be used at the top level of your app.
- **react-scripts**: Scripts and configuration used by Create React App.

## Notes

- This application assumes that there is a backend server running at `http://127.0.0.1:5000` which provides an API endpoint for managing contacts.
- Ensure that your backend server is properly configured and running before using this application.