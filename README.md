# airflow-maintenance-dags
A series of DAGs/Workflows to help maintain the operation of Airflow

https://github.com/epicmobile18/airflow-maintenance-dags (forked from [teamclairvoyant/airflow-maintenance-dags](https://github.com/teamclairvoyant/airflow-maintenance-dags))



## DAGs/Workflows

* backup-configs
    * A maintenance workflow that you can deploy into Airflow to periodically take backups of various Airflow configurations and files.
* clear-missing-dags
    * A maintenance workflow that you can deploy into Airflow to periodically clean out entries in the DAG table of which there is no longer a corresponding Python File for it. This ensures that the DAG table doesn't have needless items in it and that the Airflow Web Server displays only those available DAGs.  
* db-cleanup
    * A maintenance workflow that you can deploy into Airflow to periodically clean out the DagRun, TaskInstance, Log, XCom, Job DB and SlaMiss entries to avoid having too much data in your Airflow MetaStore.
* kill-halted-tasks
    * A maintenance workflow that you can deploy into Airflow to periodically kill off tasks that are running in the background that don't correspond to a running task in the DB.
    * This is useful because when you kill off a DAG Run or Task through the Airflow Web Server, the task still runs in the background on one of the executors until the task is complete.
* log-cleanup
    * A maintenance workflow that you can deploy into Airflow to periodically clean out the task logs to avoid those getting too big.
* delete-broken-dags
    * A maintenance workflow that you can deploy into Airflow to periodically delete DAG files and clean out entries in the ImportError table for DAGs which Airflow cannot parse or import properly. This ensures that the ImportError table is cleaned every day.
