# git-stale-code

Tool to find stale code based on last modification time.

## Usage

```
usage: git-stale-code [-h] [--age-days AGE_DAYS]
                      [--path-filters PATH_FILTERS [PATH_FILTERS ...]]
                      [--debug]

optional arguments:
  -h, --help            show this help message and exit
  --age-days AGE_DAYS   Print files that haven't been modified for this number
                        of days.
  --path-filters PATH_FILTERS [PATH_FILTERS ...]
                        Optional list of path filters e.g. 'src' 'test'
  --debug               Print out debug information.
```

## Installation

`git-stale-code` is a single file binary that can be run directly without
installation.

## Development

Formatted with [black] and type checked with [mypy].

[black]: https://black.readthedocs.io/en/stable/
[mypy]: http://mypy-lang.org/

## Example Output

Output from running
`git-stale-code --age-days 4000 --path-filters actionmailer` on
[`rails/rails`][rails]:

```
File    Last modified (days)    Last author     Primary author  Primary author ratio
actionmailer/test/fixtures/asset_host_mailer/email_with_asset.html.erb  4190    Tekin Suleyman  Tekin Suleyman  1.0
actionmailer/test/fixtures/auto_layout_mailer/hello.html.erb    4276    Pratik Naik     Pratik Naik     1.0
actionmailer/test/fixtures/auto_layout_mailer/multipart.html.erb        4042    Yehuda Katz + Carl Lerche       Colin Curtin    1.0
actionmailer/test/fixtures/auto_layout_mailer/multipart.text.erb        4042    Yehuda Katz + Carl Lerche       Colin Curtin    1.0
actionmailer/test/fixtures/explicit_layout_mailer/logout.html.erb       4276    Pratik Naik     Pratik Naik     1.0
actionmailer/test/fixtures/explicit_layout_mailer/signup.html.erb       4276    Pratik Naik     Pratik Naik     1.0
actionmailer/test/fixtures/layouts/auto_layout_mailer.html.erb  4276    Pratik Naik     Pratik Naik     1.0
actionmailer/test/fixtures/layouts/auto_layout_mailer.text.erb  4195    Colin Curtin    Colin Curtin    1.0
actionmailer/test/fixtures/layouts/spam.html.erb        4276    Pratik Naik     Pratik Naik     1.0
actionmailer/test/fixtures/raw_email    5493    David Heinemeier Hansson        David Heinemeier Hansson        1.0
```

[rails]: https://github.com/rails/rails
