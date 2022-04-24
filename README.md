# Learn DBT from Scratch
### JR Tests
## I. The proposed environment setup
- conda as environment manager
- pypi/pip as package repository and manager 
- Poetry as the dependency manager.

https://ealizadeh.com/blog/guide-to-python-env-pkg-dependency-using-conda-poetry


## II. Envirioment prepare

### 

'''
$ conda env create -f environment.yaml
$ conda activate dbt
'''

### Install Poetry

'''
$ curl -sSL https://raw.githubusercontent.com/python-poetry/poetry/master/get-poetry.py | python -
'''

Setup path 
'''
$HOME/.local/bin for Unix
%APPDATA%\Python\Scripts on Windows
'''


poetry initial
'''
$ poetry init
'''


## III. Setup DBT

This repository accompanies my Learn DBT from Scratch course. Throughout the course, some of the topics we cover include:
1. Setting up DBT
'''
$ poetry add  dbt-core  dbt-postgres  dbt-snowflake 
'''

3. Connecting DBT to Snowflake
4. Getting Started with DBT Models & Tests
5. Deploying on a Schedule & DBT Cloud
6. Advanced DBT Topics
7. Best Practices

The files found in this repository are the same ones that are used throughout the course. Feel free to reference any of the code here if you like. I do recommend trying to code along with the course before copying from this repository. Also, some of the models (such as the example models) get used over and over again, so the final code here might not match the code in a given lesson.
