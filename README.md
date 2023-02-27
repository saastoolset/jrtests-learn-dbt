# Learn DBT from Scratch
### JR Tests
## I. The proposed environment setup
- conda as environment manager
- pypi/pip as package repository and manager 
- Poetry as the dependency manager.

https://ealizadeh.com/blog/guide-to-python-env-pkg-dependency-using-conda-poetry


## II. Environment prepare

### 

```
$ conda env create -f environment.yaml
$ conda activate dbt

```

### Install Poetry

```
$ curl -sSL https://raw.githubusercontent.com/python-poetry/poetry/master/get-poetry.py | python -
```

Setup path 
```
$HOME/.local/bin for Unix
%APPDATA%\Python\Scripts on Windows
```


poetry initial
```
$ poetry init
```


## III. Setup DBT

This repository accompanies my Learn DBT from Scratch course. Throughout the course, some of the topics we cover include:
1. Setting up DBT
```
$ poetry add  dbt-core  dbt-postgres  dbt-snowflake 
```

2. Init dbt
- cd jrtest and dbt init
```
$ dbt init jrtest
```

3. Connecting DBT to Snowflake

  3.1 sign in snowflake
  https://www.snowflake.com/

  3.2 change role to ACCOUNTADMIN
  
  
  3.3 create user/role/db/warehouse
  - TRANSFORM_USER / Password123
  - TRANSFORM_ROLE 
    -> parent ACCOUNTADMIN
    - ACCESS: USERNAME /TRANSFORM_USER
  - Database: Analytics
    - grant CREATE SCHEMA, MODIFY, USAGE to ACCOUNTADMIN
    - grant CREATE SCHEMA, MODIFY, USAGE to TRANSFORM_ROLE
  - Schema
    - create schema analytics.dbt;
  - warehouse TRANSFORM_WH
    - grant to TRANSFORM_ROLE
  - Extract permission in worksheet
  ```
    grant create schema on database analytics to role transform_role;
    grant usage on all schemas in database analytics  to role transform_role;
    grant usage  on future schemas in database analytics  to role transform_role;
    grant select on all tables in database analytics to role transform_role;
    grant select on future tables in database analytics to role transform_role;
    grant select on all views in database analytics to role transform_role;
    grant select on future views in database analytics to role transform_role;
  ```

  3.4 test connet
    - show profile
    '''
    $ dbt debug --config-dir
    '''
    - edit   %USERPROFILE%\.dbt\profiles.yml
    
    
4. Getting Started with DBT Models & Tests
- Check connectivity
    '''
    $ dbt debug 
    '''
- Run
    '''
    $ dbt run
    '''

5.  Deploying on a Schedule & DBT Cloud
7.  Advanced DBT Topics
8.  Best Practices

The files found in this repository are the same ones that are used throughout the course. Feel free to reference any of the code here if you like. I do recommend trying to code along with the course before copying from this repository. Also, some of the models (such as the example models) get used over and over again, so the final code here might not match the code in a given lesson.
