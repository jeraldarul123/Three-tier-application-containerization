# MERN Stack Application Containerized with Docker Compose 🚀

This project is a fully containerized **MERN Stack** (MongoDB, Express, React, Node.js) application using **Docker Compose**. It follows a three-tier architecture to ensure a clean separation between the frontend, backend, and database.

## 📌 **Project Structure**
```
mern-docker-compose/
├── docker-compose.yml
├── backend/
│   ├── Dockerfile
│   ├── server.js
│   ├── package.json
├── frontend/
│   ├── Dockerfile
│   ├── src/
│   ├── package.json
└── database/
    └── data/ (MongoDB Data Storage)
```

---

## 🛠 **Prerequisites**
- Docker & Docker Compose installed
- Basic understanding of Docker and MERN stack

---

## 🚀 **Getting Started**

1. **Clone the Repository:**
    ```bash
    git clone https://github.com/your-username/mern-docker-compose.git
    cd mern-docker-compose
    ```

2. **Create Environment Files (if required):**
    ```bash
    touch backend/.env
    touch frontend/.env
    ```
    Configure your environment variables as needed.

3. **Build and Start the Containers:**
    ```bash
    docker-compose up --build -d
    ```

4. **Access the Application:**
- Frontend: [http://localhost:3000](http://localhost:3000)
- Backend API: [http://localhost:5000](http://localhost:5000)
- MongoDB: Connect to `localhost:27017` using any MongoDB client.

---

## 🧑‍💻 **Docker Compose Configuration**

Here is a simplified version of the `docker-compose.yml` file:

```yaml
version: '3.8'

services:
  frontend:
    build: ./frontend
    ports:
      - "3000:3000"
    depends_on:
      - backend

  backend:
    build: ./backend
    ports:
      - "5000:5000"
    environment:
      MONGO_URI: mongodb://database:27017/mydb
    depends_on:
      - database

  database:
    image: mongo:6
    ports:
      - "27017:27017"
    volumes:
      - mongo-data:/data/db

volumes:
  mongo-data:
```

---

## 🛡️ **Troubleshooting**

- **Unable to prepare context error:** Ensure the `docker-compose.yml` is in the root directory and the paths in the `build.context` are correct.
- **MongoDB connection issues:** Verify that the backend uses `mongodb://database:27017/mydb` to connect to the database.

---

## 📖 **Future Enhancements**
- Implement Kubernetes for orchestration
- Add CI/CD pipeline for automated deployments
- Containerize using multi-stage builds for optimization

---

## 🎉 **Contributing**
Feel free to fork this project, submit issues, or suggest enhancements!

---

## 📝 **License**
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## 💬 **Connect with Me**
- LinkedIn: [Your LinkedIn Profile](www.linkedin.com/in/jeraldarul)


Happy Containerizing! 🚀

