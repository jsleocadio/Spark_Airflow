# Apache Spark and Apache Airflow

This project has a Docker Compose Structure to run Apache Airflow to orchestrate Python scripts and using Apache Spark to Data processing.

To run this project, you have to create a `.env` file with this information:

```
#######################
###     POSTGRES    ###
#######################

POSTGRES_USER="Your Username"
POSTGRES_PASSWORD="Your Password"
POSTGRES_DB="Your DB Name"

#######################
###     AIRFLOW     ###
#######################

AIRFLOW_UID=1000
AIRFLOW__CORE__LOAD_EXAMPLES=False
AIRFLOW__CORE__EXECUTOR=LocalExecutor
AIRFLOW__DATABASE__SQL_ALCHEMY_CONN=postgresql+psycopg2://${POSTGRES_USER}:${POSTGRES_PASSWORD}@postgres:5432/${POSTGRES_DB}
AIRFLOW__WEBSERVER_BASE_URL=http://localhost:8080
AIRFLOW__WEBSERVER__SECRET_KEY="Your Secret Key"

#######################
###    SCHEDULER    ###
#######################

SCHEDULER_USER="Your Username"
SCHEDULER_FNAME="Your First Name"
SCHEDULER_LNAME="Your Last Name"
SCHEDULER_ROLE=Admin
SCHEDULER_EMAIL="Your Email"
SCHEDULER_PASSWORD="Your Password"
```

After that execute `./log_dir_changes.sh` to change permissions and ownership of log directory. Finishing that run `./01_build_n_run.sh` to build the containers.