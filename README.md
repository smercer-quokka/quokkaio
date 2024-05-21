# Quokka.io

Quokka.io is an API wrapper for Quokka SaaS Software written in Python. https://www.quokka.io/

This library uses API key authentication for requests.

## Installing
```
pip install quokkaio
```

## Usage
```
from quokkaio.quokka import Quokka

quokka = Quokka(key=apiKey)
```

Get group ID from Sub Group Name
```
subgroupID = quokka.get_sub_groups(subGroupName)

subGroupName - The name of the Sub Group
```

Upload an app with optional subgroup IDs
```
scan_response, platform = quokka.push_scan(theFile, subGroupList)

theFile - the filename of the binary

subGroupList - a python list of subgroup IDs
```

Download a PDF of the Quokka Analysis
```
quokka.download_pdf(uuid, platform)

uuid - UUID of the Quokka analysis. Can be found from scan_response["uuid"]

platform - "android" or "ios"
```

Retrieve app issues in JSON format
```
quokka.get_app_issue(uuid)

uuid - UUID of the Quokka analysis. Can be found from scan_response["uuid"]
```

Retrieve analytics results in JSON format
```
quokka.get_results(start_date)

start_date - date to retrieve the results as python datetime

Note: limitation on analytics API, can only do days from today, no end date
```

Retrieve a list of submitted apps in JSON format
```
quokka.get_apps(start_date, end_date)

start_date, end_date - date to retrieve the results as python datetime
```

## Contributing
We are always grateful for any kind of contribution including but not limited to bug reports, code enhancements, bug fixes, and even functionality suggestions.
#### You can report any bug you find or suggest new functionality with a new [issue](https://github.com/generalgau/quokka-python/issues).
#### If you want to add some functionality to the wrapper:
1. Fork it ( https://github.com/smercer-quokka/quokka-python )
2. Create your feature branch (git checkout -b my-new-feature)
3. Commit your changes (git commit -am 'Adds my new feature')
4. Push to the branch (git push origin my-new-feature)
5. Create a new Pull Request
