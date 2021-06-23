# TIL

> Today I Learned

Inspired by [Swyx's blog post](https://www.swyx.io/learn-in-public/) I created this repository to share my notes about programming in gereral.

If you find any mistake of typo feel free to let me know.


_10 TILs and counting..._

---

### Categories

* [Data-structure](#data-structure)
* [Go](#go)
* [Tdd](#tdd)

---

### Data-structure

- [Bloom Filter](data-structure//bloom-filter.md)

### Go

- [Choose Dependency Injection over Context](go//choose-di-over-context.md)
- [Choose method over functions if there's any state](go//method-over-func.md)
- [Don't Test JSON String](go//dont-test-json-string.md)
- [Embedding might be a security issue](go//embedding-might-be-security-issue.md)
- [Errors.Is() and its customization](go//implementing-errors-is.md)
- [Passing value in URL path with fmt.Sprintf](go//passing-value-in-url-path.md)
- [Simplified Router](go//simplified-router.md)
- [Testing Content-type](go//testing-content-type.md)

### Tdd

- [Writing the minimum amount of code in TDD is good](tdd//write-minimum-amnt-code-tdd.md)

## Usage

After creating a new entry, run `./createReadme.py > README.md` to regenerate
the readme with the new data.

If you are using git, you can install this script as a pre-commit git hook so
that it is autogenerated on each commit.  Use the following command:
    cd .git/hooks/ && ln -s ../../createReadme.py pre-commit && cd -


## About

I shamelessly stole this idea from
[jbranchaud/til](https://github.com/jbranchaud/til) who claims to have stolen
it from others.

