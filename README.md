This repository hosts [PolyLaue][polylaue] documentation using the
[MkDocs][mkdocs] package. It can be built locally, and it is also hosted at
[polylaue.github.io][site]. To contribute, please fork the repository, create
a feature branch, and open a pull request.

Building Locally
----------------

First clone the repository, and then get your environment set up.

    git clone https://github.com/polylaue/polylaue.github.io
    cd polylaue.github.io

Using Python 3, run the following commands to install the documentation
requirements and start the server:

    pip install -r requirements.txt
    mkdocs serve -a localhost:8090

This will set up a local server on port 8090 which you can view in your
preferred browser at: http://localhost:8090/.

Alternatively, you may run the `serve.sh` script, which does essentially
the same thing.

Developed by [Kitware, Inc.][kitware]

  [polylaue]: https://github.com/polylaue/polylaue/ "The PolyLaue project"
  [kitware]: https://www.kitware.com/ "Kitware, Inc."
  [mkdocs]: https://www.mkdocs.org/
  [site]: https://polylaue.github.io/
