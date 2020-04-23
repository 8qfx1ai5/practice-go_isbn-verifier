
# This project is an exercise to develop a simple cli program

The task was created from [Tino](https://github.com/pandorasNox) according to his [go-workshop](https://github.com/pandorasNox/go-workshop).

## Task

As a (skilled) user I want to be able to pass an ISBN number via command line to a programm,
which returns the same ISBN and if it's a valid ISBN-10.

### Acceptance criteria

- you can run it via cli
- you can pass an ISBN string
- you can pass a path to a CSV-file with ISBNs
- passes all test-cases
- input, output and behavior matches the following examples

#### Example Valid single ISBN

    $ validateisbn "1-24325435-3435-X"
    the given input '1-24325435-3435-X' to be expected an isbn is: valid

#### Example Invalid single ISBN

    $ validateisbn "1-thisisnotanISBN-X"
    the given input '1-thisisnotanISBN-X' to be expected an isbn is: invalid

#### Example CSV file (input.csv)

    ""
    0-8436-1072-7
    0843610727
    thisisnotanISBN

#### Example run with CSV file

    $ validateisbn -f "input.csv"
    ;false;
    0-8436-1072-7;true;
    0843610727;true
    thisisnotanISBN;false;

## Steps

- define function signiture
- write unit tests for the function
- implement the function
- implement cli wrapper with one input argument for the possible isbn
- implement integration tests for the CLI
- implement input argument to pass a csv file-path with a list of possible ISBNs
- expend integration tests for the CLI with CSV file

### Hints

- [What is an ISBN](https://web.archive.org/web/20130522043458/http://www.isbn.org/standards/home/isbn/international/html/usm4.htm)
- [How to use GO for CLI](https://gobyexample.com/command-line-arguments)

## The final result

### How to build

    $ go build -o validateisbn isbn.go

### How to run

    $ ./validateisbn "thisisnotanISBN"

### How to test

    $ go test isbn.go isbn_test.go

## Conclusion

This was a very nice exercise. I learned a lot about go development. The hight frequent code reviews and advices from Tino helped me a lot to speed up my learning curve.
