# PlagCheck ✅




## Installation

Install using `pip` from PyPI

```bash
pip install plagcheck
```

or directly from GitHub if you cannot wait to test new features

```bash
pip install git+https://github.com/codeclassroom/PlagCheck.git
```

## Usage

```python

"""Usage example"""
import os
import pprint
from plagcheck.plagcheck import check, insights, share_scores

from dotenv import load_dotenv
load_dotenv()

language = "java"
userid = os.environ["USER_ID"]


moss = check(language, userid)

moss.addFilesByWildCard("testfiles/test_java*.java")

# or moss.addFile("testfiles/test_python.py")

moss.submit()

print(moss.getHomePage())

result = moss.getResults()

pprint.pprint(result)

# print potential distributor-culprit relationships
pprint.pprint(insights(result))
# print frequency of each shared solution
pprint.pprint(share_scores(result))

```

## Documentation

> [PlagCheck Documentation](https://plagcheck.readthedocs.io/en/latest/)


## Development

##### Prerequisites
- Python 3.6+
- virtualenv

1. Create virtual environment.
```bash
virtualenv -p python3 venv && cd venv && source bin/activate
```
2. Clone the repository.
```bash
git https://github.com/codeclassroom/PlagCheck.git
```
3. Install Dependencies.
```bash
pip install -r requirements-dev.txt
```
4. Run tests.
```bash
pytest plagcheck
```
5. Lint the project with
```bash
flake8 plagcheck --max-line-length=88 --ignore=F401
black --check --diff plagcheck
```

## 📝 Changelog

See the [CHANGELOG.md](CHANGELOG.md) file for details.


## Author

👥 **Ansh verma**







