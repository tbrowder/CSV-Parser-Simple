[![Actions Status](https://github.com/tbrowder/Text-CSV-Simple/actions/workflows/test.yml/badge.svg)](https://github.com/tbrowder/Text-CSV-Simple/actions)

NAME
====

**Text::CSV::Simple** - A simple CSV file reader

SYNOPSIS
========

```raku
use Text::CSV::Simple;
```

DESCRIPTION
===========

**Text::CSV::Simple** is a very simple CSV file reader which is not very robust. It is intended as a makeshift CSV file reader for my use until modules **Text::CSV::LibCSV** can be made to test successfully with **Github workflows** as well as handle header lines with an ending empty field and data lines with trailing whitespace.

One other feature it has, which is not usual in CSV parsers, is to ignore comment lines which may have leading whitespace but it and data at or after a comment character is ignored so the line is treated as a blank line.

Another feature it has is to normalize text in a field, that is: leading and trailing whitespace is trimmed and interior whitespace is collapsed to one space between words.

Legal field separators
----------------------

  * comma (`,`)

  * pipe (`|`)

  * tab (`;`)

Limitations
-----------

It cannot currently handle special characters, backslashes, non-text data, quoted words, or multi-line fields.

API
---

The module attempts to mimic the line-by-line parsing algorithm in module `CSV::Parser` which is demonstrated here:

AUTHOR
======

Tom Browder <tbrowder@acm.org>

COPYRIGHT AND LICENSE
=====================

Copyright 2022 Tom Browder

This library is free software; you may redistribute it or modify it under the Artistic License 2.0.

