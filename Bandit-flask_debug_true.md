Pattern: Use of flask app with debug set to true

Issue: -

## Description

Running Flask applications in debug mode results in the Werkzeug debugger
being enabled. This includes a feature that allows arbitrary code execution.
Documentation for both Flask [1] and Werkzeug [2] strongly suggests that debug
mode should never be enabled on production systems.

Operating a production server with debug mode enabled was the probable cause
of the Patreon breach in 2015 [3].

Example of **incorrect** code:

```python

>> Issue: A Flask app appears to be run with debug=True, which exposes
the Werkzeug debugger and allows the execution of arbitrary code.
   Severity: High   Confidence: High
  Location: examples/flask_debug.py:10
  9 #bad
  10app.run(debug=True)
  11

```

## Further Reading

[1]

<http://flask.pocoo.org/docs/0.10/quickstart/#debug-mode>

[2]

<http://werkzeug.pocoo.org/docs/0.10/debug/>

[3]

<http://labs.detectify.com/post/130332638391/how-patreon-got-hacked-publicly-
exposed-werkzeug>
* [OpenStack - B201: flask_debug_true](https://docs.openstack.org/developer/bandit/plugins/flask_debug_true.html)
