# Pre-Interview Setup Instructions

Welcome! To ensure our coding test goes smoothly, please follow these steps **before** the interview:

1. **Install Docker & Docker Compose**

   - Confirm Docker is installed and running.
   - Check your versions:
     ```bash
     docker --version
     docker compose version
     ```
   - If you get an error with `docker compose version`, make sure you have Docker Desktop (with the newer `docker compose` plugin) or install the standalone `docker-compose`.

2. **Clone This Public Repo**

   - Pull this repository onto your machine:
     ```bash
     git clone https://github.com/jerestre/cisco-pre-interview-instructions.git
     ```
   - Then navigate into the folder:
     ```bash
     cd cisco-pre-interview-instructions
     ```

3. **Start the Blank PostgreSQL Container**

   - We’ve provided a `docker-compose.yml` that spins up a **blank** PostgreSQL database.
   - Run:
     ```bash
     docker compose up -d
     ```
   - This will:
     - Download the official `postgres:14` image if you don’t already have it.
     - Start a container named `my-postgres` on port `5432`.

4. **Verify the Container is Running**

   - Check with:
     ```bash
     docker ps
     ```
   - You should see a container named `my-postgres` in the list.

5. **Prepare Your IDE**

   - Have your preferred Java IDE (e.g., IntelliJ) or editor with **Java 17** support ready.
   - Confirm your Java version:
     ```bash
     java -version
     ```
   - If you don’t have Java 17 installed, please do so before the interview.

6. **Await the Private Repo Access**

   - During the interview, we will invite you as a collaborator so you can clone a **private** Spring Boot Gradle project. That code will automatically run Flyway migrations against this blank Postgres instance.
   - **Important**: Keep this container running; you’ll connect to it from the private repo’s Spring Boot app.

### What to Expect During the Interview

- We’ll confirm your Docker setup is functioning.
- You’ll clone the private repo using the token we provide.
- You’ll open it in your IDE, run the Spring Boot app, and watch Flyway seed the database.
- Then you’ll tackle the assigned coding task (detailed in that private repo’s `README.md`).

**That’s it!** If you have any questions before the interview, feel free to reach out. Otherwise, we look forward to seeing you soon.

---

_**Note**: This public repo and its `docker-compose.yml` only provide a **blank** database with default credentials. The actual schema and data will be loaded via Flyway migrations in the private repo._
