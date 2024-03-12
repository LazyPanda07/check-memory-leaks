# @LazyPanda07/get-gtest
Detect memory leaks in C/C++ programs

# Usage
```yaml
- uses: LazyPanda07/check-memory-leaks@v1
  with:
    # Path directory with executable file.
    # Required.
    path:

    # Executable file name.
    # Required.
    name:

    # Some bash commands or scripts from 'path' directory
    # Optional. Default is ""
    pre-execute:

    # Executable arguments
    # Optional. Default is ""
    args:

    # By default, Valgrind can handle to up to 500 threads. Occasionally, that number is too small. Use this option to provide a different limit. E.g. max-threads: 3000.
    # Optional. Default is 500
    max-threads:
```

## Source
See [action.yml](https://github.com/LazyPanda07/check-memory-leaks/blob/master/action.yml)

# Example
```yaml
on:
  push:
    branches: [master]
  workflow_dispatch:

jobs:
  test:
    runs-on: ubuntu-latest

    steps:
    - uses: LazyPanda07/check-memory-leaks@1.1
      with:
        path: path/to/executable_directory
        name: executable
        pre-execute: export LD_LIBRARY_PATH=${LD_LIBRARY_PATH}:$(pwd) # for *.so loading
        args: "first" "second" "third"
```
