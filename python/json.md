# Read and write to .json

1. Import the ```json``` library.

```py
import json # Since it's a native module.
```

2. Open the .json file with:

```py
with open("file.json") as json_file:
    variable = json.load(json_file)
``` 
and then the file contents will be available as a Python dictionary.

3. To save a dictionary to a .json file:

```py
with open("settings.json", 'w', encoding='utf-8') as json_file:
    json.dump(variable, json_file, ensure_ascii=False, indent=4)

```

## Should I ```ensure_ascii```?


Please refer to this table by user [Mario Corchero](1 "Using json.dumps with ensure_ascii=True") and this answer by user [ahuigo](2 "json string's format: Non-ASCII vs ASCII"):


|         Input         | Ensure_ascii |            output            |
------------------------|--------------|-------------------------------
| u”汉语”                | True         | '"\\u6c49\\u8bed"'           |
| u”汉语”                | False        | u'"\u6c49\u8bed"'            |
| u”汉语".encode("utf-8")| True         | '"\\u6c49\\u8bed"’           |
| u”汉语".encode("utf-8")| False        | '"\xe6\xb1\x89\xe8\xaf\xad"' |

[1]:https://stackoverflow.com/questions/40412714/using-json-dumps-with-ensure-ascii-true
[2]: https://github.com/psf/requests/issues/4580#issuecomment-383796695