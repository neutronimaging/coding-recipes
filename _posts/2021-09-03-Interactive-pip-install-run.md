---
title: "Interactive pip install & run"
date: 2021-09-03
author:
- Jean Bilheux
---
If you are working on a python library that will be installed via `pip` and you need to see
live how your code behave as you are making changes, there is a better way rather than having to
install the package each time

```
pip install -e
```

and now, any changes you make to the code will be automatically updated in the code

```
python -m name_of_package
```
