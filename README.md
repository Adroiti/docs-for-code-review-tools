# Docs for code review tools
## How to contribute
### Pylint
1. Download and install latest Python 2.x distribution - https://www.python.org/downloads/
2. Install Pylint - https://www.pylint.org/#install
3. Pick undocumented rule from [Pylint-messages.txt](Pylint-messages.txt)
4. Create file named `Pylint-<code>.md` based on [template.md](template.md)
5. (Optional) See [Pylint docs](http://pylint-messages.wikidot.com/all-codes) for available rule descriptions
6. (Optional) See [PEP 8 style guide](https://www.python.org/dev/peps/pep-0008/) for possible rule description and link
7. (Optional) See other `Pylint-*.md` files for examples
8. (Optional) Run `pylint` against test `*.py` file(s) to get exact issue context and texts
