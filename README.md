# Docs for code review tools
## How to contribute
### Pylint
1. Download and install latest Python 2.x distribution - https://www.python.org/downloads/
2. Install Pylint - https://www.pylint.org/#install
3. Pick undocumented rule from [Pylint-messages.txt](Pylint-messages.txt)
4. Modify file named `Pylint-<code>.md` based on [template.md](template.md)
5. (Optional) See [Pylint docs](http://pylint-messages.wikidot.com/all-codes) for available rule descriptions
6. (Optional) See [PEP 8 style guide](https://www.python.org/dev/peps/pep-0008/) for possible rule description and link
7. (Optional) See [Google Python Style Guide](https://google.github.io/styleguide/pyguide.html?showone=Semicolons#Semicolons) for possible rule description and link
8. (Optional) See other `Pylint-*.md` files for examples
9. (Optional) Run `pylint` against test `*.py` file(s) to get exact issue context and texts

### Govet
1. Download and install latest Go distribution - https://golang.org/dl
2. Pick undocumented rule from [Govet-messages.txt](Govet-messages.txt)
4. Modify file named `Govet-<flag>.md` based on [template.md](template.md)
5. (Optional) See [Govet docs](https://golang.org/cmd/vet) for available rule descriptions
6. (Optional) See [Go Code Review Comments](https://github.com/golang/go/wiki/CodeReviewComments) for possible rule description and link
7. (Optional) See other `Govet-*.md` files for examples
8. (Optional) Run `go tool vet` against test `*.go` file(s) to get exact issue context and texts
