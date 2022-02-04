### Technical Challenge

Use any language / framework to accomplish the task. Time-boxed to 2 hours; Do as much as you can in 2 hours.

#### Application requirements

1. Acceptance Criteria 1: Provide documentation on how to setup and run the application.

2. Acceptance Criteria 2: Application must download encrypted file from https://kjtrane.github.io/kjtrane/data-file.etf

3. Acceptance Criteria 3: Application should not cache encrypted file. (Each time the application is ran, it must download the encrypted file).

4. Acceptance Criteria 4: Application must output all “Data blocks” that are appended to the end of the encrypted file.


#### Data blocks explained

Appended to the end of the encrypted file contents, are an unknown number of “data blocks”.

The very last 12 bytes of the encrypted file is a “file meta block”, where:

The first 8 bytes is a signature (string) that must match “ValidSig”

The last 4 bytes is the actual file size of the encrypted file’s contents (unsigned 32 bit int).

There are an unknown number of (but at most 12) “data blocks” appended (as hex) to the end of the encrypted file contents. The data structure for a single “data block” is:

The first 8 bytes is the block type (as a string)

The next 4 bytes is the “data block” size (unsigned 16 bit int)

The “data block” data, which is variable in length depending on the 4 bytes that indicates the “data block” size.

There are three “data block” types: string, json and date.


#### Bonus

Decrypt the file.


#### Questions?

Feel free to message me with any questions.
