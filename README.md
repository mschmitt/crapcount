# crapcount

## Name

**crapcount** - Cookie and Request Analyzer ++

(formerly known as **cookiecount**)

## Description

**crapcount** allows generation of an automated report of cookies and all the 3rd party domains the given website makes a browser talk to.

The tool is here and it's freely available, don't say you had no way of knowing about all that crap.

## Synopsis

```
usage: crapcount [-h] [--browser BROWSER] [--nocookies]
                 [--nohosts] [--nourls]
                 [--waituntil WAITUNTIL] [--reportonly]
                 [--json]
                 url

Cookie and Request Analyzer ++

positional arguments:
  url                   An full URL including scheme
                        (https:// etc.)

optional arguments:
  -h, --help            show this help message and exit
  --browser BROWSER     name of browser binary, default
                        chromium
  --nocookies           show cookies
  --nohosts             show hosts
  --nourls              show urls
  --waituntil WAITUNTIL
                        page event to wait for, default
                        networkidle2; other events: load,
                        domcontentloaded, networkidle0 - see
                        https://pptr.dev/api/puppeteer.page.
                        goto
  --reportonly          in non-JSON mode, only report
                        numbers.
  --json                json output
```

## Examples

crapcount https://example.com

crapcount https://google.com --json

crapcount https://reddit.com --json --nourls --nocookies --waituntil=load

## Running into timeouts?

The `--waituntil` option may need to be adjusted depending on the page's architecture. See the [Puppeteer documentation](https://pptr.dev/api/puppeteer.page) about the available options.

## Dependencies

- **Python 3**
- **Chrome** or **Chromium**
- **pyppeteer** for remote controlling *Chrome/Chromium*
  - The ancient "embedded" Chromium which pyppeteer uses by default is untested and unsupported.


## See also

- Pyppeteer - https://github.com/pyppeteer/pyppeteer
- Puppeteer - https://pptr.dev/

# Copyright and License

```
MIT License

Copyright (c) 2022 Martin Schmitt

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
