.PHONY: install init lint black tests

GLOBAL_PYTHON_INTERPRETER={{ cookiecutter.python_interpreter }}
VENV_PYTHON_INTERPRETER=$(CURDIR)/.venv/bin/python

install:
	@echo "$(pn)" >> requirements.txt
	${VENV_PYTHON_INTERPRETER} -m pip install -r requirements.txt

install-dev:
	@echo "$(pn)" >> requirements-dev.txt
	${VENV_PYTHON_INTERPRETER} -m pip install -r requirements-dev.txt

init:
	${GLOBAL_PYTHON_INTERPRETER} -m venv .venv
	${VENV_PYTHON_INTERPRETER} -m pip install -r requirements-dev.txt

lint:
	${VENV_PYTHON_INTERPRETER} -m flake8 {{cookiecutter.project_name}}

black:
	${VENV_PYTHON_INTERPRETER} -m black {{cookiecutter.project_name}}

test:
	${VENV_PYTHON_INTERPRETER} -m pytest tests
