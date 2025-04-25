# CloudFail

CloudFail is a tactical reconnaissance tool which aims to gather enough information about a target protected by Cloudflare in the hopes of discovering the location of the server. Using Tor to mask all requests, the tool as of right now has 3 different attack phases.

1. Misconfigured DNS scan using DNSDumpster.com.
2. Scan the Crimeflare.com database.
3. Bruteforce scan over 2500 subdomains.

![Example usage](http://puu.sh/pq7vH/62d56aa41f.png "Example usage")

> Please feel free to contribute to this project. If you have an idea or improvement, issue a pull request!

#### Disclaimer
This tool is a PoC (Proof of Concept) and does not guarantee results. It is possible to setup Cloudflare properly so that the IP is never released or logged anywhere; this is not often the case and hence why this tool exists.
This tool is only for academic purposes and testing under controlled environments. Do not use without obtaining proper authorization from the network owner of the network under testing.
The author bears no responsibility for any misuse of the tool.

#### Install on Kali/Debian

First, we need to install pip3 for Python3 dependencies:

```bash
sudo apt-get install python3-pip
```

Then we can run through dependency checks:

```bash
pip3 install -r requirements.txt
```

If this fails because of missing setuptools, do this:

```bash
sudo apt-get install python3-setuptools
```

### Additional Configuration Step
To use the DNSDumpster API, you must add your API key to the `config.py` file:

1. Open `config.py` in any text editor.
2. Locate the `API_KEY` variable.
3. Insert your API key as a string. ***The config.py file must be in the format API_KEY: "XXXXXXXXXXXXXXXXXXXXXX", or CloudFail will not read the API key correctly***
4. Save and close the file.

#### Usage

To run a scan against a target:

```bash
python3 cloudfail.py --target seo.com
```

To run a scan against a target using Tor:

```bash
service tor start
```

(or if you are using Windows or Mac, install Vidalia or just run the Tor browser)

```bash
python3 cloudfail.py --target seo.com --tor
```

> Please make sure you are running with Python3 and not Python2.*.

#### Dependencies
**Python3**
* argparse
* colorama
* socket
* binascii
* datetime
* requests
* win_inet_pton
* dnspython
* time

## Contributions
### 🚀 CloudFail: Fixed Errors with DNSDumpter API key not being read from config.py. Added rate limiting on the subdomain scanning

### **Key Improvements:**
✅ **Fixed API Key bug** Key wasn't being read from config.py properly    
✅ **Added rate limiting** to slow down subdomain scanning 

 Contributions and feedback are welcome! 🔥

## Credits
- **Updated & Fixed by:** brenscar2020
- **Updated & Fixed by:** SUKH-X
- **Original Author:** m0trem


