.PHONY: install init lint black test

GLOBAL_PYTHON_INTERPRETER={{ cookiecutter.python_interpreter }}
VENV_PYTHON_INTERPRETER=$(CURDIR)/.venv/bin/python

install:
	${VENV_PYTHON_INTERPRETER} -m pip install $(package_name)

install-dev:
	echo "$(package_name)" >> requirements-dev.txt
	${VENV_PYTHON_INTERPRETER} -m pip install -r requirements-dev.txt

init:
	${GLOBAL_PYTHON_INTERPRETER} -m venv .venv
	${VENV_PYTHON_INTERPRETER} -m pip install -r requirements-dev.txt

lint:
	${VENV_PYTHON_INTERPRETER} -m flake8 {{ cookiecutter.project_name }}*.py

black:
	${VENV_PYTHON_INTERPRETER} -m black {{ cookiecutter.project_name }}*.py

test:
	${VENV_PYTHON_INTERPRETER} -m pytest tests
