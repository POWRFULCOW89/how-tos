# Create an .exe file

1. Initialize a virtual environment:

```sh
python -m venv env
env\Scripts\activate
```

2. Install ```pyinstaller```.

```sh
(env) pip install pyinstaller
```

3. Create the .exe file:

```sh
(env) pyinstaller --onefile script.py
```

4. Optionally, if a virtual environment was not initialized:

```sh
py -3.9 -m PyInstaller --onefile 'script.py'
```

5. ```pyinstaller``` will generate two new directories: ```build``` and  ```dist```. The .exe file will be generated in ```dist```, based on the source files compiled at ```build```.

6. Execute with:

```sh
cd dist
script.exe
```

