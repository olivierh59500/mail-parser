# mail-parser

## Overview

mail-parser is a wrapper for [email](https://docs.python.org/2/library/email.message.html) Python Standard Library.

## Description

mail-parser takes as input a raw mail and generates a parsed object. This object is a tokenized mail with the all parts of mail and some indicator:
  - body
  - headers
  - subject
  - from
  - to
  - attachments
  - message id
  - date
  - charset mail

We have also two indicator:
  - anomalies: mail without message id or date
  - defects: mail with some not compliance RFC part

### Apache 2 Open Source License
mail-parser can be downloaded, used, and modified free of charge. It is available under the Apache 2 license.


## Authors

### Main Author
Fedele Mantuano (**Twitter**: [@fedelemantuano](https://twitter.com/fedelemantuano))


## Installation

Clone repository

```
git clone https://github.com/SpamScope/mail-parser.git
```

and install mail-parser with `setup.py`:

```
cd mail-parser

python setup.py install
```

or use `pip`:

```
pip install mail-parser
```

## Usage

Import `MailParser` class:

```
from mailparser import MailParser

parser = MailParser()
parser.parse_from_file(f)
parser.parse_from_string(raw_mail)
```

Then you can get all parts

```
parser.body
parser.headers
parser.message_id
parser.to_
parser.from_
parser.subject
parser.text_plain_list: only text plain mail parts in a list
parser.attachments_list: list of all attachments
parser.charset
parser.date_mail
parser.parsed_mail_obj: tokenized mail in a object
parser.parsed_mail_json: tokenized mail in a JSON
parser.defects: defect RFC non compliance
parser.has_defects
parser.anomalies
parser.has_anomalies
```