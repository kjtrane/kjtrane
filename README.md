### Technical Challenge

#### Application requirements

1. Acceptance Criteria 1: Use any language / framework to accomplish the task.

2. Acceptance Criteria 2: Provide documentation on how to run the code.

3. Acceptance Criteria 3: Application must download encrypted file from https://kjtrane.github.io/kjtrane/data-file.etf

4. Acceptance Criteria 4: Application must cache encrypted file locally, but for no longer than 24 hours.

5. Acceptance Criteria 5: Application must output all “Data blocks” that are appended to the end of the encrypted file.

6. Acceptance Criteria 6: Time-boxed to 2 hours; Do as much as you can in 2 hours.

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