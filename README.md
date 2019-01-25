#### Create a new project
```bash
poetry new <project-name>
```
#### Add a new lib
```bash
potry add <library>
```
#### Remove a lib
```bash
poetry remove <library>
```
#### Update a lib
```bash
poetry update <library>
```
#### Get venv path
```bash
poetry run which python
```
#### Run app
```bash
poetry run python app.py
```
#### Run tests
```bash
poetry run python -m unittest discover
```
#### Show dependencies
```bash
poetry show
```
#### Create script
1 - Edit `pyproject.toml`:
```toml
[tool.poetry.scripts]
test = 'scripts:test'
```
2 - Create a `scripts.py` file on the root directory of your project:
```python
import subprocess

def test():
    """
    Run all unittests. Equivalent to:
    `poetry run python -u -m unittest discover`
    """
    subprocess.run(
        ['python', '-u', '-m', 'unittest', 'discover']
    )
```
3 - Run script:
```bash
poetry run test
```

### Visual Studio Code interworking

1 - Check your venv python path.

2 - Create a <project-name>.code-workspace file with the following content:
  
  ```json
{
  "folders": [
    {
      "path": "."
    }
  ],
  "settings": {
    "python.pythonPath": "<POETRY-VENV-PATH>/b2sw-py3.6/Scripts/python.exe"
  }
}
```

**Note to Windows users**: use **\\\\** instead of **/** to join paths.
