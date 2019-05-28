
django internal self checks
--------------------------------
run manage.py check --deploy

https://docs.djangoproject.com/en/2.1/howto/deployment/checklist/

https://docs.djangoproject.com/en/2.1/topics/security/


Basic plays
-------------
outside enumeration

	nmap -sC -sV -vv -Pn -oA ipaddress

	gobuster -u ipaddressURL -fw -w wordlist -o sitefile.txt

django middleware checks
django version CVE check
nginx/apache front end
file inclusions
code sanity - python code checkers/fuzzers
server setup/config checks

Other checks
----------------
any php
any database issues in configurations

TLS checks
-----------
https://testssl.sh/

code checks
---------------
https://github.com/python-security/pyt
https://github.com/PyCQA/bandit
https://www.kitploit.com/2017/08/spaghetti-web-application-security.html

web app scan checks
--------------------
nickto
owasp zap
fuzzer
https://github.com/m4ll0k/WAScan

If able to run from 3rd party source
https://observatory.mozilla.org/


privsec
--------
**Unix privesc**

http://pentestmonkey.net/tools/audit/unix-privesc-check

Run the script and save the output in a file, and then grep for warning in it.

**Linprivchecker.py** - safe to run

https://github.com/reider-roque/linpostexp/blob/master/linprivchecker.py

**LinEnum** - same as Ians basher.sh script - safe to run

https://github.com/rebootuser/LinEnum

**run as**

	python <(curl -ks https://github.com/reider-roque/linpostexp/blob/master/linprivchecker.py)

	python <(curl -ks https://github.com/ianneilsen/firstresponder/blob/master/basher.sh)

