[![Actions Status](https://github.com/tbrowder/CSV-Parser-Simple/actions/workflows/test.yml/badge.svg)](https://github.com/tbrowder/CSV-Parser-Simple/actions)

NAME
====

**CSV::Parser::Simple** - A simple CSV file reader

SYNOPSIS
========

```raku
use CSV::Parser::Simple;
my $parser = CSV::Parser::Simple.new: $csv-file-name;
```

DESCRIPTION
===========

**Text::CSV::Simple** is a very simple CSV file reader and parser. It is intended as a makeshift CSV file reader for my use until modules **Text::CSV::LibCSV** can be made to test successfully with **Github workflows** as well as handle header lines with an ending empty field and data lines with trailing whitespace.

As simple as it is, it does have some features that are very useful:

  * Comment lines are allowed

    This feature, which is not usual in CSV parsers, is to ignore comment lines which may have leading whitespace, but it and data at or after a comment character are ignored so the line is treated as a blank line. The comment character is user-definable but must not conflict with the chosen field separator.

  * Text normalization

    Its results are to normalize text in a field, that is: leading and trailing whitespace is trimmed and interior whitespace is collapsed to one space between words. This is the default behavior but can be turned off if desired (`normalize=False`).

Limitations
-----------

It cannot currently handle special characters, backslashes, non-text data, quoted words, named line endings, or multi-line fields.

Constructor signature
---------------------

    new($csv-file-name, :separator=',', :normalize=True, :comment-char='#')

Following are the allowable values for the named arguments. The user is cautioned that unspecified values are probably not tested. File an issue if your value of choice is not specified, and it can be added and tested for.

  * `:$separator`

    * comma (`,`) [default]

    * pipe (`|`)

    * semicolon (`;`)

    * tab (`\t`)

    * others, including multiple characters, are possible

  * `:$normalize`

    * `True` [default]

    * `False`

  * `:$comment-char`

    * `#` [default]

    * others, including multiple characters, are possible

AUTHOR
======

Tom Browder <tbrowder@acm.org>

COPYRIGHT AND LICENSE
=====================

© 2022 Tom Browder

This library is free software; you may redistribute it or modify it under the Artistic License 2.0.

