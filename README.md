<p align="center">
  <a href="https://www.withcoherence.com">
    <img alt="Coherence Logo" title="Coherence" src="./logo.png" width="400" style="color: black">
  </a>
</p>


<p align="center">
  <i>Platform-as-a-service in your own Cloud</i><br/> 
  <a href="https://www.withcoherence.com">withcoherence.com</a>
</p>

<h1 align="center">
Django and Postgres Example
</h1>

<p align="center">
<img src="https://img.shields.io/badge/django-%23092E20.svg?style=for-the-badge&logo=django&logoColor=white">
<img src="https://img.shields.io/badge/postgres-%23316192.svg?style=for-the-badge&logo=postgresql&logoColor=white">
</p>

<br/>

# Full stack Django and Postgres application (employee management)

<p>
This is the code to accompany the tutorial available at our <a href="https://docs.withcoherence.com/coherence-templates/full-stack-template/?tabs=django">Framework Guide (Django)</a> page.
</p>

You can use it as a starting point for any full stack Django application. Read the guide to see how to deploy it to a production environment in your own cloud, or see the instructions below to run a development version of it locally.

## Getting Started 

Fork the repository to your GitHub account. To test locally, clone the forked repository to your machine. You will need to have Docker installed.

### Prerequisites

- Docker
- Postgres

### Installation and Usage

1. **Clone the repository:**

    ```bash
    git clone https://github.com/<your_github_username>/django-postgres-employees-demo.git
    cd django-postgres-employees-demo
    ```

2. Add your database credentials to the `docker-compose.yml` file:

    ```yaml
    services:
      db:
        image: postgres:13
        environment:
          POSTGRES_DB: <database_name>
          POSTGRES_USER: <database_user>
          POSTGRES_PASSWORD: <database_password>
    ```

3. Add your database credentials to the `settings.py` file:

    ```python
    DATABASES = {
        'default': {
            'ENGINE': 'django.db.backends.postgresql',
            'NAME': '<database_name>',
            'USER': '<database_user>',
            'PASSWORD': '<database_password>',
            'HOST': 'db',
            'PORT': 5432,
        }
    }
    ```

4. **Build and run the Docker container:**

    ```bash
    docker-compose up --build
    ```

5. **Run database migrations:**

    ```bash
    docker-compose run web python manage.py migrate
    ```

6. **Access the application:**

    Open your browser and navigate to `http://localhost:8000/`.

## Resources

Take a look at the following for more information:

* [Coherence](https://www.withcoherence.com)
* [Why Choose Coherence](https://docs.withcoherence.com/#why-choose-coherence)
* [Coherence Documentation](docs.withcoherence.com)

**Cloud Infrastructure On Autopilot**

_Deploy containerized and serverless apps to your own cloud in minutes, not weeks._
