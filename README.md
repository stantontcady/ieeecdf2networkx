# IEEE Common Data Format (CDF) Parser

This is a simple script that takes a text file formatted in the IEEE CDF as input and generates a NetworkX graph-theoretic model of the power system with the final power flow states.

## Requirements

ieeecdf2networkx was developed and tested using Python version 2.7.6, but should be compatible with most versions of Python 2. The only dependency is on the third-party [NetworkX](networkx.github.io) library.

##Usage

##Gotchas and Other Known Issues
The code written for this parser is based off the [format outline](https://www.ee.washington.edu/research/pstca/formats/cdf.txt) provided at the [Power Systems Test Case Archive](https://www.ee.washington.edu/research/pstca/) maintained by the University of Washington.  It was developed and tested using the [118-bus test case](https://www.ee.washington.edu/research/pstca/pf118/pg_tca118bus.htm), and, during development, it was found that some of the column numbers in the format outline did not match the test case.  Specifically, the following discrepancies were found.

* Bus name in bus data section should start at character (column) 7; in the test case, the bus name started at the 6th character.
* Loss zone in the branch data section should start at character (column) 14; in the test case, the loss zone started at the 13th character.

##Incomplete Features
In it's current implementation, only the bus and branch data is accounted for. Loss zone data, interchange data, and tie line data are all ignored.