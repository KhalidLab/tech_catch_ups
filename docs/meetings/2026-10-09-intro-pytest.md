---
tags:
  - Testing
  - Unit Testing
---

# 2026-10-09 — Getting started with pytest

## Resource watched

**Title:** [Getting started with pytest](https://youtu.be/mzlH8lp4ISA?si=PJ9kc9Jzw3xnKJok)

**Type:** Video

## Summary and takeaways

Testing is crucial for validating code, making it reliable, reusable and maintainable. 

`pytest` is a popular, easy-to-use testing framework for Python that is replacing (phasing out) built-in `unittest` module. 

`pytest` has a lot of features. Some key features to know/learn about (most of them are briefly discussed in the video):

- test functions and test classes *(writing test functions is the colloquially preferred option)*

- [parametrization](https://docs.pytest.org/en/stable/example/parametrize.html)

- fixturres (see this [YouTube video](https://youtu.be/ScEQRKwUePI?si=1sHxfxfJ-rCByMPc) or [pytest docs](https://docs.pytest.org/en/stable/explanation/fixtures.html))

- patching (see [pytest docs](https://docs.pytest.org/en/stable/how-to/monkeypatch.html), but look into other resources as well because pytest built-ins, especially `Monkeypatch` are not always the most robust solutions)

- coverage reports (see [Python Developers Guide](https://devguide.python.org/testing/coverage/)). [CodeCov](https://docs.codecov.com/docs/code-coverage-with-python) is a popular resource that can be used to generate reports and badges for public repositories.

- random execution using [`pytest-randomly`](https://github.com/pytest-dev/pytest-randomly)

- there are many paradigms and strategies in testing (unit tests, integration tests etc), there is polenty to explore. 

**What should I test and how?**

- Test the key pieces that are central algorithm and workflow. E.g. if you are writing a module that calculates SASA test that it produces correct results. On the other hand you may want to test that your CLI workflow is running correctly depending on the input options.

- **Test for errors and edge cases!** E.g. incorrect inputs, inputs producing numerical instability etc.

- Look for examples in other scientific packages. E.g. this is a [test suite for MDAnalysis](https://github.com/MDAnalysis/mdanalysis/tree/develop/testsuite); it's huge, so you can inspect overall structure and maybe small code details for helpful examples. 

- Also take a look beyound scientific packages, because those can lag behind best practices established in industry. There are also [general test samples like this one](http://github.com/hectorcanto/pytest-samples).


## Resources

- [pytest documentation](https://docs.pytest.org/en/stable/)
- [antonywritescode](https://www.youtube.com/@anthonywritescode) channel has a lot of videos dedicated to pytest and testing more generally. E.g. 
    - [Testing exceptions](https://youtu.be/6nRxZyQwwlE?si=eSQ2I5p2z5FcZc8y)
    - [Pytest parametrize](https://youtu.be/aQH7hyJn-No?si=ll_eYDnlviza-GYU)
    - [Testing output](https://youtu.be/dN-pVt7i4Us?si=dCnRsHemPd43nSoC)
- Another interesting library: [`Hypopthesis`](https://hypothesis.readthedocs.io/en/latest/), property-based testing library for Python.
