[comment]: # "Auto-generated SOAR connector documentation"
# Dossier

Publisher: Splunk Community  
Connector Version: 1\.2\.1  
Product Vendor: Infoblox  
Product Name: Dossier  
Product Version Supported (regex): "\.\*"  
Minimum Product Version: 5\.0\.0  

This app supports investigate actions on the Infoblox Dossier platform

[comment]: # " File: readme.md"
[comment]: # ""
[comment]: # "  Copyright (c) 2019-2021 Splunk Inc."
[comment]: # ""
[comment]: # "  Licensed under the Apache License, Version 2.0 (the 'License');"
[comment]: # "  you may not use this file except in compliance with the License."
[comment]: # "  You may obtain a copy of the License at"
[comment]: # "  "
[comment]: # "      http://www.apache.org/licenses/LICENSE-2.0"
[comment]: # ""
[comment]: # "  Unless required by applicable law or agreed to in writing, software distributed under"
[comment]: # "  the License is distributed on an 'AS IS' BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND,"
[comment]: # "  either express or implied. See the License for the specific language governing permissions"
[comment]: # "  and limitations under the License."
[comment]: # ""
This app requires access to **port 1175** on your Phantom host(s) in order to function properly.

The Infoblox ActiveTrust Platform has been replaced by the Infoblox BloxOne Platform
(csp.infoblox.com). Users need to migrate to the new platform to continue to use Dossier. This
fix/update migrates the phantom dossier integration to the new platform to ensure users are able to
continue to utilize this integration.

**Note:** Users will need a new API key.

Users will need to get a new API key from the BloxOne Platform - ActiveTrust Platform API will now
be invalid.


### Configuration Variables
The below configuration variables are required for this Connector to operate.  These variables are specified when configuring a Dossier asset in SOAR.

VARIABLE | REQUIRED | TYPE | DESCRIPTION
-------- | -------- | ---- | -----------
**api\_key** |  required  | password | API Key for Dossier Service

### Supported Actions  
[test connectivity](#action-test-connectivity) - Validate the asset configuration for connectivity using supplied configuration  
[lookup domain](#action-lookup-domain) - Check for the presence of a domain in a threat intelligence feed  
[lookup ip](#action-lookup-ip) - Check for the presence of an IP in a threat intelligence feed  
[lookup hash](#action-lookup-hash) - Check for the presence of a hash in a threat intelligence feed  
[lookup url](#action-lookup-url) - Check for the presence of a url in a threat intelligence feed  

## action: 'test connectivity'
Validate the asset configuration for connectivity using supplied configuration

Type: **test**  
Read only: **True**

#### Action Parameters
No parameters are required for this action

#### Action Output
No Output  

## action: 'lookup domain'
Check for the presence of a domain in a threat intelligence feed

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**domain** |  required  | Domain to lookup | string |  `domain`  `url` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.domain | string |  `domain`  `url` 
action\_result\.data\.\*\.\*\.data\.record\_count | numeric | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.batch\_id | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.class | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.confidence | numeric | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.detected | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.dga | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.domain | string |  `domain` 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.expiration | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.extended\.audience | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.extended\.etcategory | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.extended\.hash\_md5 | string |  `md5` 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.extended\.hash\_sha1 | string |  `sha1` 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.extended\.hash\_sha256 | string |  `sha256` 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.extended\.intelligencetype | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.extended\.killchain | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.extended\.maliciousconfidence | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.extended\.malware | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.extended\.malwarefamily | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.extended\.networkidentifier | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.extended\.networktype | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.extended\.observationtime | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.extended\.ports | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.extended\.reportid | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.extended\.threatscape | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.extended\.threattype | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.extended\.title | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.extended\.url\_hash | string |  `md5` 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.host | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.id | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.imported | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.ip | string |  `ip` 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.origin | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.profile | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.property | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.received | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.target | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.threat\_level | numeric | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.tld | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.tlp | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.type | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.up | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.url | string |  `url` 
action\_result\.data\.\*\.\*\.params\.source | string | 
action\_result\.data\.\*\.\*\.params\.target | string | 
action\_result\.data\.\*\.\*\.params\.type | string | 
action\_result\.data\.\*\.\*\.status | string | 
action\_result\.data\.\*\.\*\.task\_id | string | 
action\_result\.data\.\*\.\*\.time | numeric | 
action\_result\.data\.\*\.\*\.v | string | 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.summary\.threat\_confidence | numeric | 
action\_result\.summary\.threat\_level | numeric | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'lookup ip'
Check for the presence of an IP in a threat intelligence feed

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**ip** |  required  | IP to lookup | string |  `ip` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.ip | string |  `ip` 
action\_result\.data\.\*\.\*\.data\.record\_count | numeric | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.batch\_id | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.class | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.confidence | numeric | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.confidence\_score | numeric | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.confidence\_score\_rating | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.confidence\_score\_vector | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.detected | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.domain | string |  `domain` 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.expiration | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.extended\.cyberint\_guid | string |  `md5` 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.extended\.etcategory | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.extended\.ports | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.host | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.id | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.imported | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.ip | string |  `ip` 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.origin | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.profile | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.property | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.received | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.target | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.threat\_level | numeric | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.tld | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.tlp | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.type | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.up | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.url | string |  `url` 
action\_result\.data\.\*\.\*\.params\.source | string | 
action\_result\.data\.\*\.\*\.params\.target | string |  `ip` 
action\_result\.data\.\*\.\*\.params\.type | string | 
action\_result\.data\.\*\.\*\.status | string | 
action\_result\.data\.\*\.\*\.task\_id | string | 
action\_result\.data\.\*\.\*\.time | numeric | 
action\_result\.data\.\*\.\*\.v | string | 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.summary\.results | numeric | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'lookup hash'
Check for the presence of a hash in a threat intelligence feed

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**hash** |  required  | Hash to lookup | string |  `sha256`  `sha1`  `md5` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.hash | string |  `sha256`  `sha1`  `md5` 
action\_result\.data\.\*\.\*\.data\.details\.av\_engine\_count | numeric | 
action\_result\.data\.\*\.\*\.data\.details\.av\_match\_count | numeric | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scan\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.ALYac\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.ALYac\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.ALYac\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.ALYac\.version | string |  `ip` 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.APEX\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.APEX\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.APEX\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.APEX\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.AVG\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.AVG\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.AVG\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.AVG\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Acronis\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Acronis\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Acronis\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Acronis\.version | string |  `ip` 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Ad\-Aware\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Ad\-Aware\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Ad\-Aware\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Ad\-Aware\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.AegisLab\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.AegisLab\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.AegisLab\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.AegisLab\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.AhnLab\-V3\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.AhnLab\-V3\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.AhnLab\-V3\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.AhnLab\-V3\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Alibaba\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Alibaba\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Alibaba\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Alibaba\.version | string |  `ip` 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Antiy\-AVL\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Antiy\-AVL\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Antiy\-AVL\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Antiy\-AVL\.version | string |  `ip` 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Arcabit\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Arcabit\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Arcabit\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Arcabit\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Avast\-Mobile\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Avast\-Mobile\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Avast\-Mobile\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Avast\-Mobile\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Avast\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Avast\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Avast\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Avast\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Avira\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Avira\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Avira\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Avira\.version | string |  `ip` 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Baidu\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Baidu\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Baidu\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Baidu\.version | string |  `ip` 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.BitDefender\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.BitDefender\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.BitDefender\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.BitDefender\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Bkav\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Bkav\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Bkav\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Bkav\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.CAT\-QuickHeal\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.CAT\-QuickHeal\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.CAT\-QuickHeal\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.CAT\-QuickHeal\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.CMC\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.CMC\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.CMC\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.CMC\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.ClamAV\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.ClamAV\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.ClamAV\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.ClamAV\.version | string |  `ip` 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Comodo\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Comodo\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Comodo\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Comodo\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.CrowdStrike\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.CrowdStrike\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.CrowdStrike\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.CrowdStrike\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Cybereason\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Cybereason\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Cybereason\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Cybereason\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Cylance\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Cylance\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Cylance\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Cylance\.version | string |  `ip` 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Cyren\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Cyren\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Cyren\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Cyren\.version | string |  `ip` 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.DrWeb\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.DrWeb\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.DrWeb\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.DrWeb\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.ESET\-NOD32\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.ESET\-NOD32\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.ESET\-NOD32\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.ESET\-NOD32\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Emsisoft\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Emsisoft\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Emsisoft\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Emsisoft\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Endgame\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Endgame\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Endgame\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Endgame\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.F\-Prot\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.F\-Prot\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.F\-Prot\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.F\-Prot\.version | string |  `ip` 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.F\-Secure\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.F\-Secure\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.F\-Secure\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.F\-Secure\.version | string |  `ip` 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.FireEye\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.FireEye\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.FireEye\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.FireEye\.version | string |  `ip` 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Fortinet\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Fortinet\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Fortinet\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Fortinet\.version | string |  `ip` 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.GData\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.GData\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.GData\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.GData\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Ikarus\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Ikarus\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Ikarus\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Ikarus\.version | string |  `ip` 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Invincea\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Invincea\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Invincea\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Invincea\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Jiangmin\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Jiangmin\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Jiangmin\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Jiangmin\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.K7AntiVirus\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.K7AntiVirus\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.K7AntiVirus\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.K7AntiVirus\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.K7GW\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.K7GW\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.K7GW\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.K7GW\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Kaspersky\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Kaspersky\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Kaspersky\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Kaspersky\.version | string |  `ip` 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Kingsoft\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Kingsoft\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Kingsoft\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Kingsoft\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.MAX\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.MAX\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.MAX\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.MAX\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Malwarebytes\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Malwarebytes\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Malwarebytes\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Malwarebytes\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.MaxSecure\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.MaxSecure\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.MaxSecure\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.MaxSecure\.version | string |  `ip` 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.McAfee\-GW\-Edition\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.McAfee\-GW\-Edition\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.McAfee\-GW\-Edition\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.McAfee\-GW\-Edition\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.McAfee\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.McAfee\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.McAfee\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.McAfee\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.MicroWorld\-eScan\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.MicroWorld\-eScan\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.MicroWorld\-eScan\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.MicroWorld\-eScan\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Microsoft\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Microsoft\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Microsoft\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Microsoft\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.NANO\-Antivirus\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.NANO\-Antivirus\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.NANO\-Antivirus\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.NANO\-Antivirus\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Paloalto\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Paloalto\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Paloalto\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Paloalto\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Panda\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Panda\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Panda\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Panda\.version | string |  `ip` 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Qihoo\-360\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Qihoo\-360\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Qihoo\-360\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Qihoo\-360\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Rising\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Rising\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Rising\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Rising\.version | string |  `ip` 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.SUPERAntiSpyware\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.SUPERAntiSpyware\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.SUPERAntiSpyware\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.SUPERAntiSpyware\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.SentinelOne\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.SentinelOne\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.SentinelOne\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.SentinelOne\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Sophos\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Sophos\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Sophos\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Sophos\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Symantec\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Symantec\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Symantec\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Symantec\.version | string |  `ip` 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.TACHYON\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.TACHYON\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.TACHYON\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.TACHYON\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Tencent\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Tencent\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Tencent\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Tencent\.version | string |  `ip` 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.TotalDefense\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.TotalDefense\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.TotalDefense\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.TotalDefense\.version | string |  `ip` 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Trapmine\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Trapmine\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Trapmine\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Trapmine\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.TrendMicro\-HouseCall\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.TrendMicro\-HouseCall\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.TrendMicro\-HouseCall\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.TrendMicro\-HouseCall\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.TrendMicro\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.TrendMicro\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.TrendMicro\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.TrendMicro\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Trustlook\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Trustlook\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Trustlook\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Trustlook\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.VBA32\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.VBA32\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.VBA32\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.VBA32\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.VIPRE\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.VIPRE\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.VIPRE\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.VIPRE\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.ViRobot\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.ViRobot\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.ViRobot\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.ViRobot\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Webroot\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Webroot\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Webroot\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Webroot\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Yandex\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Yandex\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Yandex\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Yandex\.version | string |  `ip` 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Zillya\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Zillya\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Zillya\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Zillya\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.ZoneAlarm\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.ZoneAlarm\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.ZoneAlarm\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.ZoneAlarm\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Zoner\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Zoner\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Zoner\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.Zoner\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.eGambit\.detected | boolean | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.eGambit\.result | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.eGambit\.update\_time | string | 
action\_result\.data\.\*\.\*\.data\.details\.av\_scans\.eGambit\.version | string | 
action\_result\.data\.\*\.\*\.data\.details\.md5 | string |  `md5` 
action\_result\.data\.\*\.\*\.data\.details\.sha1 | string |  `sha1` 
action\_result\.data\.\*\.\*\.data\.details\.sha256 | string |  `sha256` 
action\_result\.data\.\*\.\*\.data\.match | boolean | 
action\_result\.data\.\*\.\*\.data\.summary\.av\_engine\_count | numeric | 
action\_result\.data\.\*\.\*\.data\.summary\.av\_match\_count | numeric | 
action\_result\.data\.\*\.\*\.data\.summary\.av\_match\_percent | numeric | 
action\_result\.data\.\*\.\*\.data\.summary\.first\_seen | string | 
action\_result\.data\.\*\.\*\.data\.summary\.last\_seen | string | 
action\_result\.data\.\*\.\*\.data\.summary\.status | string | 
action\_result\.data\.\*\.\*\.data\.summary\.threat\_level | numeric | 
action\_result\.data\.\*\.\*\.data\.summary\.trust\_factor | numeric | 
action\_result\.data\.\*\.\*\.params\.source | string | 
action\_result\.data\.\*\.\*\.params\.target | string |  `md5` 
action\_result\.data\.\*\.\*\.params\.type | string | 
action\_result\.data\.\*\.\*\.status | string | 
action\_result\.data\.\*\.\*\.task\_id | string | 
action\_result\.data\.\*\.\*\.time | numeric | 
action\_result\.data\.\*\.\*\.v | string | 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.summary | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'lookup url'
Check for the presence of a url in a threat intelligence feed

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**url** |  required  | URL to lookup | string |  `url` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.url | string |  `url` 
action\_result\.data\.\*\.\*\.data\.record\_count | numeric | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.batch\_id | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.class | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.confidence\_score | numeric | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.confidence\_score\_rating | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.confidence\_score\_vector | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.detected | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.domain | string |  `domain` 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.expiration | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.extended\.cyberint\_guid | string |  `md5` 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.extended\.protocol | string |  `url` 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.extended\.url\_hash | string |  `md5` 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.host | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.id | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.imported | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.ip | string |  `ip` 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.origin | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.profile | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.property | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.received | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.risk\_score | numeric | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.risk\_score\_rating | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.risk\_score\_vector | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.target | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.threat\_level | numeric | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.threat\_score | numeric | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.threat\_score\_rating | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.threat\_score\_vector | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.tld | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.tlp | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.type | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.up | string | 
action\_result\.data\.\*\.\*\.data\.threat\.\*\.url | string |  `url` 
action\_result\.data\.\*\.\*\.params\.source | string | 
action\_result\.data\.\*\.\*\.params\.target | string |  `url` 
action\_result\.data\.\*\.\*\.params\.type | string | 
action\_result\.data\.\*\.\*\.status | string | 
action\_result\.data\.\*\.\*\.task\_id | string | 
action\_result\.data\.\*\.\*\.time | numeric | 
action\_result\.data\.\*\.\*\.v | string | 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.summary | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric | 