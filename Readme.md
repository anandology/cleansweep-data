Cleansweep Data
===============

Data about indian political boundaries to setup instance of
[cleansweep](https://github.com/anandology/cleansweep).

The data is stored in the `data` directory and all the files storing data in TSV format.

`level.txt`
-----------

The `level.txt` provides all the levels in the place hierarchy. Each row will have `short_name` and `name` columns.

Here is a sample:

    STATE	State
    DISTRICT	District
    AC		Assembly Constituency
    PB		Polling Booth


Place Files
-----------

There will be mutliple files for specifying places. Each file will be have 3
columns separated with tabs with `parent`, `key` and `name` fields. 

For example:

    KL/DT01	KL/AC001	Manjeshwar
    KL/DT01	KL/AC002	Kasaragod
    KL/DT01	KL/AC003	Udma
    KL/DT01	KL/AC004	Kanhangad
    ...

The type of the place is infered from the name of the file. if a file is named
as `3-ac.txt`, it is assumed that all the places specified are of level AC.
This should match the `short_name` of the level specified in the `level.txt`
file.

For ease of maintanance, files for each state are stored in a subdirectory,
named as the 2-letter code of the state. Places which are above the state level
are specified as files in the top-level.
