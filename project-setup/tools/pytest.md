# Pytest

The [pytest](https://docs.pytest.org/en/stable/) framework makes it easy to write small, readable tests, and can scale to support complex functional testing for applications and libraries.


- Add the pytest dev dependency and add config instructions to the pyproject.toml -
```bash
uv add --dev pytest pytest-cov
```
```toml
[tool.pytest.ini_options]
pythonpath = "src"
log_file = "logs/tests.log"
log_file_date_format = "%Y-%m-%dT%H:%M:%S.%f%z"
log_file_format = "%(asctime)s %(levelname)s:%(funcName)s: %(message)s [in %(pathname)s:%(lineno)d]"
log_file_level = "INFO"

[tool.coverage.run]
branch = true
parallel = true
# omit = [""]
```