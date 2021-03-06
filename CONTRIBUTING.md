## Work with Github

```
git clone https://github.com/thib1984/pypodo.git #or your fork repo ;)
cd pypodo
#work with git
git add .
git commit -am "my commit"
git push
```

##  "Manual" tests


After installing the prerequisites

```
pip3 install mutatest
pip3 install coverage
pip3 install pylint
```

You can launch tests, measure coverage, test mutations or evaluate the quality of code with one of the commands :

```
#in the root of the project
python3 -m unittest -v pypodo/__pypodo__test.py #to execute unit tests
coverage run && coverage html #to generate html : report in htmlcov folder
mutatest #to test mutations #to generate mutations
pylint pypodo/__pypodo__.py #to evaluate quality of code unit tests
```

##  Local CI/CD

If you want, you can use "local" CI/CD with pip or docker. Add the "fast" parameter desactivates the mutation testing who takes a lot of time.
So, choose one of these commands :

```
#in the root of the project
./pypodo_ci_cd.sh pip ci #to launch pylint, unit test, coverage and mutation
./pypodo_ci_cd.sh pip ci fast #to launch pylint, unit test and coverage
./pypodo_ci_cd.sh pip cd #to launch unit pylint, test, coverage, and mutation + build pip
./pypodo_ci_cd.sh pip cd fast #to launch pylint, unit test and coverage + build pip
./pypodo_ci_cd.sh docker ci #to launch pylint, unit test, coverage, mutation and end to end test with docker
./pypodo_ci_cd.sh docker ci fast #to pylint, launch unit test, coverage and end to end test with docker
./pypodo_ci_cd.sh docker cd #to launch pylint, unit test, coverage, mutation and end to end test with docker + build image pypodo
./pypodo_ci_cd.sh docker cd fast #to launch pylint, unit test, coverage and end to end test with docker + build image pypodo
./pypodo_ci_cd.sh full #to launch pylint, unit test, coverage, mutation and end to end test with docker + build pip + build image pypodo
./pypodo_ci_cd.sh full fast #to launch pylint, unit test, coverage and end to end test with docker + build pip + build image pypodo

```

You can now verify, at the root of the projetc, the **test.log**, **mutation.log**, **htmlcov** folder and **pylint.log** to view results of the ci/cd.
