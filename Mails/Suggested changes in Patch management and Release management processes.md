
Dear colleagues,

We want to implement some new changes in Patch management process and Vulnerability scanning requirements within Release management process.

**1)Patch management**
All vulnerabilities with CVSSv3 (in some cases CVSS) score within **7.0-10** range will be divided in 2 categories - **exploitable** and **non-exploitable** **All** **exploitable** vulnerabilities (**7.0-10**) should be remediated within **30 days** after discovering **Non-exploitable** vulnerabilities will be also divided into **2** categories - **CDE/Published services** and **Others** 
**All** **non-exploitable** vulnerabilities (**7.0-10**) from the **CDE/Published services** category also should be remediated within **30 days** after discovering **Other non-exploitable** vulnerabilities (**7.0-10**) should be remediated maximum within **59 days** after discovering

**Databases** should be patched within **60 days** (**except DBs in CDE**)

![[Pasted image 20231127113156.png]]

**2) Release management**

In case if new server will be released **internally** (**without publishing to internet**) it can be released with vulnerabilities not above CVSS score **3.9** (low severity) (of course taking into account all mitigation factors)

In case if server will be **published** **all** vulnerabilities should be remediated
Colleagues, please share your thoughts and comments regarding this new approach
[@Nigar Mammadova](mailto:nigar.mammadova@pashabank.az "mailto:nigar.mammadova@pashabank.az") plz support how such kind of changes can be reflected in Bank’s official documents


Best Regards,

**Timur Huseynov |** **Head of Cyber Threats Detection and Response Division**
**SOC Department**
2, Mardanov Gardashlari Street, Baku, AZ1000, Azerbaijan
tel.: +994.12.496.51.00 (2113) | cell: +994.51.250.33.60email: [timur.huseynov@pashabank.az](mailto:timur.huseynov@pashabank.az "mailto:timur.huseynov@pashabank.az") | [www.pashabank.az](http://www.pashabank.az/ "http://www.pashabank.az/")