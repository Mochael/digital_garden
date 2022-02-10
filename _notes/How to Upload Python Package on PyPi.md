---
title: How to Upload Python Package on PyPi
tree_state: 🌱
---

Let's assume that at this point you have a some directory that you want to turn into a package that's hosted on PyPi.

1. Make sure you configure your `setup.py` (most people use `setup.cfg` to hold the data that's used when executing `setup.py`).
	- You need to specify things like the `name`, `version`, `url`, etc. Also, as a note, the name of the actual package that people install can have a different name than the actual main package module, like how you import `sklearn` even though you install `scikit-learn`.
2. Make sure you have `wheel`, `bdist_wheel`, and `twine` all installed through pip
3. Now let's say you are making a change to your package:
	1. When making a change, make sure that you edit the version number of the package, whereever it needs to be edited (most likely in the `setup.cfg`)
	2. If you have a zip source archive and wheel files in a dist folder, delete the dist folder because these are for older versions of your package
	3. Run `python setup.py sdist bdist_wheel` to recreate updated zip source archive and wheel files in the dist folder
	4. Run `twine upload --skip-existing --repository-url https://test.pypi.org/legacy/ dist/*` in order to upload your zip source archive and wheel files to PyPi's test server.
	5. Try installing the package from the test server to make sure it's working properly
4. Let's say the version on the test server was working, so now we are ready to launch the package to PyPi. Run `twine upload dist/*` to upload the package to PyPi, and it should be ready to go.