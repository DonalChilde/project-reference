# Ruff


```toml
[tool.ruff.lint]
select = ["B", "UP", "D", "DOC", "FIX", "I", "F401"]
# non-imperative-mood (D401)
ignore = ["D401", "D101"]
# extend-select = ["I"]


[tool.ruff.lint.pydocstyle]
convention = "google"

[tool.ruff.format]
docstring-code-format = true
docstring-code-line-length = 88
```