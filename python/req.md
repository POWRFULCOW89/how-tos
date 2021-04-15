# Generate a requirements.txt for GitHub

More often than not, it is easier to distribute a ```requirements.txt``` file to a peer instead of comparing packages and their versions manually. 

What is more, we're interested in only sharing the relevant libraries relevant to our project, so it is strongly recommended to perform the following steps inside a virtual environment. 

Should you generate a ```requirements.txt```, all of your globally installed packages will be listed, which will only clutter the global module scope of anyone who installs from said file.

So, inside a virtual environment, we do:

```sh
(env) pip freeze > requirements.txt
```

and a ```requirements.txt``` file will be generated. You can now distribute this file or upload to a GitHub repo.

To install all dependencies from a requirements file, we do:

```sh
(env) pip install -r requirements.txt
```
