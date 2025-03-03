# MLOps-project
Complete end to end MLOps Project

----------------------------------------------------
Setting up project structure
1. Create repo, clone it in local
2. Create a virtual environment named 'atlas' - conda create -n atlas python=3.10
3. Activate the virtual environment - conda activate atlas
4. pip install cookiecutter
5. cookiecutter -c v1 https://github.com/drivendata/cookiecutter-data-science
6. Setup the project and cut paste files to root directory.
7. Rename src/models -> src/model
8. git add - commit - push

-------------------------Setup MLFlow on Dagshub---------------------------
1. Go to: https://dagshub.com/dashboard
2. Create > New Repo > Connect a repo > (Github) Connect > Select your repo > Connect
3. Copy experiment tracking url and code snippet. (Also try: Go To MLFlow UI)
4. pip install dagshub & mlflow

5. Run the exp notebooks
6. git add - commit - push

7. dvc init
8. create a local folder as "local_s3" (temporary work)
9. on terminal - "dvc remote add -d mylocal local_s3"

10. Add code to below files/folders inside src dir:
    - logger
    - data_ingestion.py
    - data_preprocessing.py
    - feature_engineering.py
    - model_building.py
    - model_evaluation.py
    - register_model.py
11. add file - dvc.yaml (till model evaluation.metrics)
12. add file - params.yaml
13. DVC pipeline is ready to run - dvc repro
14. Once do - dvc status
15. git add - commit - push

16. Need to add S3 as remote storage - Create IAM User(keep cred) and S3 bucket
17. pip install - dvc[s3] & awscli
18. Checking/deleting dvc remote (optional) - [dvc remote list & dvc remote remove <name>] 
19. Set aws cred - aws configure
20. Add s3 as dvc remote storage - dvc remote add -d myremote s3://<bucket-name>

21. Create new dir - flask_app | Inside that, add rest of the files and dir
22. pip install flask and run the app (dvc push - to push data to S3)