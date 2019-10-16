# How to use Airflow 

### Keywords:
- DAG:
  - A directed acyclic graph that represent data pipeline
- Operator:
  - Describe a single task in the data pipeline 
- Task:
  - An instance of a operator 
- TaskInstance:
  - Representation a specific run of a task = DAG + TASK + POINT IN TIME
- Workflow:
  - Combination of all above 
- Scheduler:
  - Responsible for scheduling your jobs
- Executor:
  - Message queuing process tightly bound to the Scheduler and dtermines the worker processes that actually execute each task. 
- Workers:
  - Processes taht execute the tasks, determined by the executor
- Metadatabase:
  - A database where allt he metadata related to your jobs are stored.

![img1][img/af_single.png]
