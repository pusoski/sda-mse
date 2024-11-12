# Macedonian Stock Analyzer

An application that provides a platform for investors and analysts to analyze historical data for stocks on the Macedonian Stock Exchange, allowing users to have daily access to stock market data covering the last 10 years. User will be able to track performance trends, compare companize, visualize data, and generate insights to support their financial decisions. Project for the course Software Design and Architecture at FCSE Skopje.

The application sources its information from: https://www.mse.mk/en. 

Contributors (The students working on this project):
- Hristijan Pusoski, Index: 221524
- Iskra Stojchevska, Index: 221535
- Irinej Ilievski, Index: 211554

## Running the Application (Homework One)

### 1. Clone the Repository
> Requires a Git installation to be present on the system.
```bash
git clone https://github.com/pusoski/sda-mse.git
cd sda-mse
```

### 2. Run Through Docker / Docker Compose
> Requires a Docker installation to be present on the system.
```bash
docker-compose up --build
```

## Note About the Dockerized Application - Where to Find the Data...

Once run using Docker / Docker Compose, the application (Homework One) stores the data in a volume for MongoDB. The data can then be accessed using software like JetBrains DataGrip or PyCharm's built-in database functionalities, **without authentication on localhost:27017** (see [docker-compose.yml](https://github.com/pusoski/sda-mse/blob/main/docker-compose.yml)).

![image info](https://i.ibb.co/JnvSZt6/image.png)

To insert data with unformatted prices (English, original format), before building the app (Step 2), in the [Dockerfile](https://github.com/pusoski/sda-mse/blob/main/Dockerfile) change the format argument value to 0 (last line of the file). Otherwise, to use the Macedonian format of the prices, keep the format value argument as it is (`--format=1`).

If decided to go from `--format=1` to `--format=0`, or vice versa, please ensure that you have exported the scraped records, and that the Docker image of the app and the volume for the database have been deleted (ensure that you have a clean environment), before building the app again.
