# tastedive-api-documentation
Documentation of the TasteDive API. </br>
Documentation is also available on [readthedocs.io](https://tastedive-api-documentation.readthedocs.io/en/latest/)
## Set-up 

TasteDive API Documentation using Sphinx, a tool to facilitate the generation of nice-looking documentation. Before you install Sphinx, you may want to set-up a virtualized development environment: learn [how to set up virtualenv](http://docs.python-guide.org/en/latest/dev/virtualenvs/).

Then, run the following in your terminal:

```bash
source venv/bin/activate
git clone https://github.com/vivekrj0/tastedive-api-documentation.git
cd tastedive-api-documentation
pip install -r requirements.txt
```

Afterwards, whenever you want to use this virtual environment, run `workon venv`.


Ready to dive in? Edit the `rst` files in the `docs` directory. Then, generate the html by running the Makefile:

```bash
cd docs
make html
```

Then, view your code in a browser:

```bash
open _build/html/index.html
```
## Contribute

You can learn about the process of Sphinx and document creation on the [Read the Docs site](http://docs.readthedocs.io/en/latest/getting_started.html).

