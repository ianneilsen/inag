
django internal self checks
--------------------------------
run manage.py check --deploy

https://docs.djangoproject.com/en/2.1/howto/deployment/checklist/

https://docs.djangoproject.com/en/2.1/topics/security/

https://pypi.org/project/django-secure/


Last resort scanner
https://www.ponycheckup.com/
https://github.com/mxsasha/ponycheckup

Basic plays
-------------
outside enumeration

	nmap -sC -sV -vv -Pn -oA ipaddress

	gobuster -u ipaddressURL -fw -w wordlist -o sitefile.txt

django middleware checks
django version CVE check
nginx/apache front end

	Check for x-forward headers from http to https
	we can fake Host header if django allows this
	html file inculsions using the django media or user-upload content
	It was discovered that Django incorrectly handled the default 404 page. A remote attacker could use this issue to spoof content using a malicious UR

file inclusions
code sanity - python code checkers/fuzzers
server setup/config checks

Other checks
----------------
any php
any database issues in configurations
* sql injection maybe - doubt it though with the django orm - but not impossible

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
https://www.kitploit.com/2017/08/spaghetti-web-application-security.html

If able to run from 3rd party source
https://observatory.mozilla.org/


Vul databases
---------------
https://snyk.io/vuln/pip:django
https://www.upguard.com/articles/top-10-django-security-vulnerabilities-and-how-to-fix-them



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


Specific code checks
----------------------

xss vulnerable

(form.errors.as_text())
(form.errors.as_json())
payload = foo.<img src=x onerror=alert(1)>

grep -R "ValidationError"
