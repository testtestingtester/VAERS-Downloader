# [VAERS Downloader](https://github.com/McFlat/vaers-downloader)

This project downloads VAERS Data from [https://vaers.hhs.gov/data.html](https://vaers.hhs.gov/data.html) it depends on tensorflow to automatically trained models to solve the captcha and download data into `VAERS/` directory.

# Install

```sh
pip install vaers_downloader
```

# Usage

```sh
vaers_downloader [--start=2019] [--end=2019] [--directory=/tmp]
```

This will create a new directory named `VAERS` in the currect directory where you ran the above command.

Pass a parameter or two for the start and end year as below to download data for those years only. 

Default: basically will download all data from 2019 to whatever the year it is when you run it.


```sh
python -m vaers_downloader.download -s 2000
python -m vaers_downloader.download --start 1990  -e 1999 -d /tmp
```

# Development

```sh
python3 -m venv .venv
source .venv/bin/activate
pip3 install -r requirements.txt
```

```py
import os
import sys
sys.path.insert(0, './vaers_downloader')
from VAERSFileDownloader import updateVAERSFiles

updateVAERSFiles(
        needsUpdate = True,
        years = [2019, 2020, 2021, 2022],
        workingDirectory = os.getcwd())
```

> Thanks to Frank Knoll for the original code... https://github.com/KnollFrank/HowBadIsMyBatch

# Tests

```sh
python setup.py test
```

# License

See [LICENSE](LICENSE)

# Authors

- Frank Knoll (https://github.com/KnollFrank)
- Alex Goretoy (https://github.com/McFlat)
