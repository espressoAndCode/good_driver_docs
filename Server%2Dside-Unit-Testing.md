## Overview
This project uses [Pytest](https://docs.pytest.org/en/stable/) for server side unit testing.

### Setup

All server side unit tests will be located in the directory:
```
|_ services
   |_ server
      |_ project
         |_ tests
```

Pytest will auto discover test files that start or end with test, for example, `test_*.py` or `*_test.py`. Test functions must begin with `test_`, and classes must begin with `Test`.

### A Sample Test
```
# content of test_sample.py
def inc(x):
    return x + 1


def test_answer():
    assert inc(3) == 5
```

### Running the Tests

Unit tests can be run with the command:
```
docker-compose exec server python -m pytest "project/tests" -p no:warnings --cov="project"
```