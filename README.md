# Two ways to stop writing Docker files

If l'm being honest with myself, writing `Dockerfile` and `docker-compose.yml` is a pain and surely, l can't be the only one
out there experiencing this pain. Fortunately we have two of our friends that have created solution to stop our pain.

In this article l will be mainly focusing on Django, showcasing two ways to avoid creating docker files. The first and the most recommended way is using a CLI command `docker init`. The second option is to use [Django cookiecutter]("https://cookiecutter-django.readthedocs.io/").

## Prerequisites
- Django
- Git
- Virtual environment
- bash

## Docket init
If you are familiar with git you must be aware of a command called `git init` which initialises a local repository. In the same breath we have got an a similar CLI command called `docket init` which also initialises your projects. Docket init which l discovered a few days ago can help you to create project resources within your project. It creates Dockerfiles, docker compose files and well as well copied `.dockerignore`. Not only is this good news but it is a life saver, because now you are getting configurations directly from the system
meaning you will be getting the best configurations.


### How to use it?
As mention before we will be using Django. [Create]("https://docs.github.com/en/repositories/creating-and-managing-repositories/quickstart-for-repositories") a repository on github and add a readme file, then clone the repository locally. It's always best practise to create a virtual environment. Create a `requirement.txt` file so that your directory structure looks as follows.

```md
computername/clonerepository
├── readme.md
├── requirement.txt
└── myvenv/
```

#### Installation
1. Install docker follow instruction [here]("https://docs.docker.com/get-docker/").
2. Open `requirement.txt` file
3. Add `django` and save
4. With your virtual environment active run `pip install -r requirement.txt`


#### Setup
Now that you have installed everything, ensure that all of them are properly installed. For django use `django-admin help` and for docker use `docker help`. If all of them return results that you are all set.

- Start your django project using `django-admin startproject myproject .`
- Run `docket init`
- You will be asked a few questions:
    - What application platform does your project use? (use arrows to move and select with <kbd>Enter</kbd> ) select **Python**
    - What version of python do you want to use? ( this is the version used in docker) at the time of writing select 3.10.10
    - What port do you want to listen to? 8000
    - What is the command you use to run your app? `python manage.py runserver` (if you want to use gunicorn it auto selects.)
- Your docker files are now created.

You see how easy it is, imagine all that time you spend creating docker files. You can go through the docker files that is has created for you.