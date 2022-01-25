# Automated documentation for Python scripts using Sphinx

This repository includes a template for Sphinx documentation that runs in docker through docker-compose.\
Prior launching the service please review the docker-compose.yml, in particular the port number with the HTML documentation (default is set to 8080) and the folder containing the python scripts to be documented.

The structure of the repository for the automated documentation is the following:
```
├── docs
│   ├── source
│   │   ├── _ext (external interactions, e.g.: edit on gitHub functionality)
│   │   ├── _files (for files to be attached)
│   │   ├── _static (for figures, etc.)
│   │   ├── _templates (for HTML layouts, etc.)
│   │   ├── conf.py
│   │   ├── index.rst
│   │   ├── markdownFile_1.rst
│   │   ├── markdownFile_2.rst
│   │   ├── ...
|   │   └── markdownFile_n.rst
│   ├── Dockerfile
│   ├── requirements.txt
│   └── sphinxConfig.yml
├── pythonScripts (can be renamed)
│   ├── file_1.py
│   ├── file_2.py
│   ├── ...
│   └── file_n.py
├── otherFolder (depends on the project and can be also more than one)
├── .gitignore
├── LICENSE
├── README.md
└── docker-compose.yml
```

To bring the system up and running simply point the repository folder within the terminal/command prompt and run:
```
docker-compose up --build
```
Additional pages to the documentation, edits, etc. will automatically update on the HTML page.

The main folders that are monitor by the automated documentation are:
- docs/source
- pythonScripts

This last one can be renamed and its name should be updated in the docker-compose.yml and sphinxConfig.yml
If the conf.py is updated or some changes in the documentation is not appearing after refreshing the web browser, please consider restart the docker container.

Finally, to bring the system up and running and dethatch it from the terminal run:
```
docker-compose up --build -d
```
