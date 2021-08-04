c-integrate
===========

In this repository you can find the implementation of a script 
that integrates stitched and dynamic C-Debian call graphs.

Usage
-----

```bash
usage: Integrate FASTEN static and dynamic call graphs [-h] stitched [dynamic ...] output

positional arguments:
  stitched
  dynamic
  output

optional arguments:
  -h, --help  show this help message and exit
```

Install
-------

* Unix

```bash
cp c-integrate /usr/local/bin
```

Example
-------

```bash
./c-integrate zlib1g-dev.json test-data/minigzip.json test-data/minigzipsh.json out.json
```

Output Format
-------------

```json
{
    "edges": [
        [0, 1, {"static": True, "dynamic": True}]
        [0, 2, {"static": False, "dynamic": True}]
    ],
    "nodes": {
        "0": {
            "URI": "fasten://example$0.1-1/hello;C/main()",
            "metadata": {}
        },
        "1": {
            "URI": "fasten://example$0.1-1/hello;C/local()",
            "metadata": {}
        },
        "2": {
            "URI": "fasten://depshared$0.1-1/libdepsharedb.so;C/dep_shared_fun_b()",
            "metadata": {}
        }
    }
}
```
