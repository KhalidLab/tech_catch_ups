---
tags:
  - Software Design
  - Testing
---

# 2026-10-16 — Python CLI tested with pytest

## Resource watched

**Title:** [Python cli tested with pytest](https://www.youtube.com/watch?v=sv46294LoP8)

**Type:** Video

## Summary and takeaways

Here are the key points for developing Command Line Interface tool with Python:

- The machanism of `if __name__ == 'name'` is the key step to separate executable and importable parts in the .py module.

- Write `def main()` and call it from under `if __name__ == 'name'` 

- To parse arguments, `sys.argv` is the most basic mechanism, but it's so basic that it requires a lot of code around it to validate and control it. `argparse` is a much better built-in solution with a lot of utilities.

- Passing argument namespace to main `main(argv)` makes it more testable.

- Another good practice is to **exit with a return code**. This can become particularly relevant if your tool has many executions cenarios and failure modes. 

  - `int` return code can be programmed manually or you can use `argparse` error message built-ins. 

  - Return codes have to be produced with `sys.exit` or `raise SystemExit(...)`

  - Another option is to return `int` from `main` and do `exit(main())`. However this approach will depend on `site` and that has some edge cases.

- Helpful for working in `bash`: command `echo $?` will display the exit code of the previous task.

- **Add type annotations for your CLI!**

- **What about testing?** 

  - Test with `pytest.raises(SystemExit, ...)`
  - If you want to test for stdout/err output you can use `capsys` fixture in the pytest.
  - Check both stdout and sterr (e.g. we can expect that stderr is empty)
  - Check the exit code.
  - Look for examples on CLI testing in other packages. 

- When you prompt GenAI for CLI or tests for CLI you have to understand what you are asking for, otherwise your output can be dramatically overengineered.

Minimal example:

```python
import sys
import argparse

def main(argv: Optional[Sequence[str]] = None) -> int:
  parser = argparse.ArgumentParser()
  parser.add_argument()
  args = parser.parse_args(argv)

  if args.person == '':
    print('Person argument cannot be empty?', file=sys.stderr)
    return 1

  print(f"Hello, {args.person}!")
  return 0

if __name__ == 'name'
  exit(main())
```

## Resources

- [`argparse` documentation](https://docs.python.org/3/library/argparse.html). It has **many** capabilities. Particularly valuable sections:

  - Adding arguments with [`add_argument`](https://docs.python.org/3/library/argparse.html#the-add-argument-method) has plenty of useful tools. E.g. you can specify types of the arguments and validation of the type through `action` parameter.

  - [Other utilities](https://docs.python.org/3/library/argparse.html#other-utilities)

- python docs on [`SystemExit`](https://docs.python.org/3/builtins/exceptions.html#SystemExit)

- An example of CLI testing can be found in the [`cookiecutter` project](https://github.com/cookiecutter/cookiecutter/tree/main). For example, here is a link to [`tests_cli.py`](https://github.com/cookiecutter/cookiecutter/blob/main/tests/test_cli.py)

- An example of [integration tests with `martinize`](https://github.com/marrink-lab/vermouth-martinize/blob/master/vermouth/tests/integration_tests/test_integration.py)
