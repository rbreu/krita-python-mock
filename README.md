# krita-python-mock

A mock Krita Python module for use in unit tests of Krita plugins.

With this module, Python plugins for Krita can be imported outside of Krita without any import or name errors, and all `krita` API calls become no-ops. This allows to write unit tests for code units that are independent of the Krita API.

Install this module as follows into your unit test environment:

```
pip install git+https://github.com/rbreu/krita-python-mock.git
```

Caveat: The  mock krita module doesn't work with wildcard imports (`from krita import *`), but those should be avoided anyway. Instead, use:

```python
from krita import Krita
```

or

```python
import krita
krita.Krita.instance()
```

etc.