# 🎬 Movie Ticket Booking Platform

A simple, responsive **movie ticket booking platform** built with plain HTML, CSS and JavaScript. The project can be run directly in a browser or served as a Docker container using Nginx.

## 📁 Project Structure

```
movie-ticket-booking-platform/
├── index.html
├── Dockerfile
└── README.md
```

## ✨ Features

- 🎥 Movie listing with posters and movie details
- 🕐 Multiple show timings
- 💺 Interactive seat selection
- 🔴 Pre-occupied seats
- 💰 Automatic ticket price calculation
- 🎟️ Booking confirmation message
- 📱 Responsive design for desktop and mobile
- 🐳 Docker support using Nginx

## 🚀 Run Locally Without Docker

Clone the repository:

```bash
git clone https://github.com/bhanuroyal002/movie-ticket-booking-platform.git
cd movie-ticket-booking-platform
```

Since this is a static HTML application, you can open `index.html` directly in your browser.

### Option 1: Open directly

On Linux:

```bash
xdg-open index.html
```

On Windows:

```start index.html
```

Or simply double-click `index.html`.

### Option 2: Run with a local web server

If Python is installed:

```bash
python3 -m http.server 8080
```

Then open:

```
http://localhost:8080
```

Press `Ctrl+C` to stop the server.

## 🐳 Run Using Docker

### 1. Build the Docker image

From the project directory:

```bash
docker build -t movie-ticket-booking .
```

### 2. Run the container

```bash
docker run -d --name movie-ticket-booking -p 8080:80 movie-ticket-booking
```

The application will be available at:

```
http://localhost:8080
```

### 3. Check the running container

```bash
docker ps
```

### 4. View container logs

```bash
docker logs movie-ticket-booking
```

### 5. Stop the container

```bash
docker stop movie-ticket-booking
```

### 6. Remove the container

```bash
docker rm movie-ticket-booking
```

### 7. Remove the Docker image

```bash
docker rmi movie-ticket-booking
```

## 🔄 Rebuild After Code Changes

If you modify `index.html`, rebuild the image and recreate the container:

```bash
docker stop movie-ticket-booking
docker rm movie-ticket-booking
docker build -t movie-ticket-booking .
docker run -d --name movie-ticket-booking -p 8080:80 movie-ticket-booking
```

## 🔍 Dockerfile Explanation

The Dockerfile uses **Nginx Alpine** as a lightweight web server:

```dockerfile
FROM nginx:alpine
COPY index.html /usr/share/nginx/html/index.html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
```

- `FROM nginx:alpine` — Uses a lightweight Nginx image.
- `COPY index.html ...` — Copies the website into Nginx's web root.
- `EXPOSE 80` — Documents that Nginx listens on port 80.
- `CMD ...` — Starts Nginx in the foreground.

## 🧪 Verify the Application

After starting the container:

```bash
curl http://localhost:8080
```

You should receive the HTML content of the movie booking application.

You can also check the container:

```bash
docker ps
```

## 🛠️ Technologies Used

- HTML5
- CSS3
- JavaScript
- Nginx
- Docker
- Git & GitHub

## 📌 Notes

This is currently a **frontend/demo application**. Movie data, seat availability and bookings are handled in the browser and are not persisted to a backend database.

For a production version, a backend API, database, authentication, payment integration and persistent booking system can be added.

## 👨‍💻 Repository

urlGitHub Repositoryhttps://github.com/bhanuroyal002/movie-ticket-booking-platform
