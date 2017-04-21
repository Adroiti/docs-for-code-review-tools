Pattern: Use of `Flask` app with debug set to `True`

Issue: -

## Description

Running `Flask` applications in debug mode results in the `Werkzeug` debugger
being enabled. This includes a feature that allows arbitrary code execution.
Documentation for both `Flask` and `Werkzeug` strongly suggests that debug
mode should never be enabled on production systems.


Example of **insecure** code:

```python
from flask import Flask

app = Flask(__name__)
app.run(debug=True)
```

Example of **secure** code:

```python
from flask import Flask

app = Flask(__name__)
app.run()
```

## Further Reading

* [Flask - Debug Mode](http://flask.pocoo.org/docs/latest/quickstart/#debug-mode)
* [Werkzeug - Debugging Applications](http://werkzeug.pocoo.org/docs/latest/debug)
* [OpenStack - B201: flask_debug_true](https://docs.openstack.org/developer/bandit/plugins/flask_debug_true.html)
