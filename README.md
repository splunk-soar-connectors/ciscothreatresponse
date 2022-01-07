[comment]: # "Auto-generated SOAR connector documentation"
# Cisco SecureX Threat Response

Publisher: Splunk  
Connector Version: 1\.0\.0  
Product Vendor: Cisco Security  
Product Name: Cisco SecureX Threat Response  
Product Version Supported (regex): "\.\*"  
Minimum Product Version: 4\.6\.19142  

Cisco SecureX Threat Response app for Phantom provides actions allowing users to query Cisco SecureX Threat Response for verdicts and context on observables within a Phantom instance

[comment]: # " File: readme.md"
[comment]: # "  Copyright (c) 2020 Splunk Inc."
[comment]: # ""
[comment]: # "  Licensed under Apache 2.0 (https://www.apache.org/licenses/LICENSE-2.0.txt)"
[comment]: # ""
\- \`client_id\` and \`client_password\` credentials must be taken from an existing API client for
accessing the Cisco SecureX Threat Response APIs. The official documentation on how to create such a
client can be found here(https://visibility.amp.cisco.com/#/help/integration). Make sure to properly
set some scopes which will grant the client different (ideally minimum) privileges.

Make sure you have this scopes specified:

\- Enrich

\- Inspect

\- \`region\` must be one of: \`''\` (default), \`'eu'\`, \`'apjc'\`. Other regions are not
supported yet.


### Configuration Variables
The below configuration variables are required for this Connector to operate.  These variables are specified when configuring a Cisco SecureX Threat Response asset in SOAR.

VARIABLE | REQUIRED | TYPE | DESCRIPTION
-------- | -------- | ---- | -----------
**client\_id** |  required  | string | Client ID
**client\_password** |  required  | password | Client Password
**region** |  optional  | string | Region

### Supported Actions  
[test connectivity](#action-test-connectivity) - Validate the asset configuration for connectivity using supplied configuration  
[context query](#action-context-query) - Query Threat Response for Context  
[verdict query](#action-verdict-query) - Query Threat Response for Verdict  

## action: 'test connectivity'
Validate the asset configuration for connectivity using supplied configuration

Type: **test**  
Read only: **True**

#### Action Parameters
No parameters are required for this action

#### Action Output
No Output  

## action: 'context query'
Query Threat Response for Context

Type: **investigate**  
Read only: **True**

Contextualizes an observable with Cisco SecureX Threat Response info\. <hr><p> Examples of observables\: </p><p> 0b4eefc0d815ac0fdc20f22add8fd2d8113be99578a4e5189122b28b201ccbd9 \- clean,</p> <p> b1380fd95bc5c0729738dcda2696aa0a7c6ee97a93d992931ce717a0df523967 \- malicious, </p><p> f90cbce099715cfc41d793bfba4f03f8a735c0b549e1bc4d29c48dd03bbd13d0 \- unkown,</p><p>  91\.217\.162\[\.\]158 \- suspicious, </p><p> 111\.26\.23\[\.\]2 \- suspicious\. </p>

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**observable** |  required  | Observable to query | string |  `ip`  `ipv6`  `user name`  `domain`  `hash`  `sha256`  `md5`  `sha1`  `url`  `email`  `host name`  `mac address`  `file name`  `file path`  `email id`  `cisco securex threat response email subject`  `cisco securex threat response cisco mid`  `cisco securex threat response mutex`  `cisco securex threat response device`  `cisco securex threat response pki serial`  `cisco securex threat response imei`  `cisco securex threat response imsi`  `cisco securex threat response amp computer guid`  `cisco securex threat response odns identity`  `cisco securex threat response odns identity label` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.observable | string |  `ip`  `ipv6`  `user name`  `domain`  `hash`  `sha256`  `md5`  `sha1`  `url`  `email`  `host name`  `mac address`  `file name`  `file path`  `email id`  `cisco securex threat response email subject`  `cisco securex threat response cisco mid`  `cisco securex threat response mutex`  `cisco securex threat response device`  `cisco securex threat response pki serial`  `cisco securex threat response imei`  `cisco securex threat response imsi`  `cisco securex threat response amp computer guid`  `cisco securex threat response odns identity`  `cisco securex threat response odns identity label` 
action\_result\.data\.\*\.context\.\*\.disposition | string | 
action\_result\.data\.\*\.context\.\*\.module | string | 
action\_result\.data\.\*\.context\.\*\.observable | string |  `ip`  `ipv6`  `user name`  `domain`  `hash`  `sha256`  `md5`  `sha1`  `url`  `email`  `host name`  `mac address`  `file name`  `file path`  `email id`  `cisco securex threat response email subject`  `cisco securex threat response cisco mid`  `cisco securex threat response mutex`  `cisco securex threat response device`  `cisco securex threat response pki serial`  `cisco securex threat response imei`  `cisco securex threat response imsi`  `cisco securex threat response amp computer guid`  `cisco securex threat response odns identity`  `cisco securex threat response odns identity label` 
action\_result\.data\.\*\.context\.\*\.observed | string | 
action\_result\.data\.\*\.context\.\*\.sensor | string | 
action\_result\.data\.\*\.context\.\*\.target | string | 
action\_result\.data\.\*\.context\.\*\.type | string | 
action\_result\.data\.\*\.summary\.\*\.domains | numeric | 
action\_result\.data\.\*\.summary\.\*\.file\_hash | numeric | 
action\_result\.data\.\*\.summary\.\*\.ip\_address | numeric | 
action\_result\.data\.\*\.summary\.\*\.observables | numeric | 
action\_result\.data\.\*\.summary\.\*\.targets | numeric | 
action\_result\.data\.\*\.summary\.\*\.urls | numeric | 
action\_result\.summary | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'verdict query'
Query Threat Response for Verdict

Type: **investigate**  
Read only: **True**

Provides Cisco SecureX Threat Response verdict for an observable\. <hr><p> Examples of observables\: </p><p> 0b4eefc0d815ac0fdc20f22add8fd2d8113be99578a4e5189122b28b201ccbd9 \- clean,</p> <p> b1380fd95bc5c0729738dcda2696aa0a7c6ee97a93d992931ce717a0df523967 \- malicious, </p><p> f90cbce099715cfc41d793bfba4f03f8a735c0b549e1bc4d29c48dd03bbd13d0 \- unkown,</p><p>  91\.217\.162\[\.\]158 \- suspicious, </p><p> 111\.26\.23\[\.\]2 \- suspicious\. </p>

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**observable** |  required  | Observable to query | string |  `ip`  `ipv6`  `user name`  `domain`  `hash`  `sha256`  `md5`  `sha1`  `url`  `email`  `host name`  `mac address`  `file name`  `file path`  `email id`  `cisco securex threat response email subject`  `cisco securex threat response cisco mid`  `cisco securex threat response mutex`  `cisco securex threat response device`  `cisco securex threat response pki serial`  `cisco securex threat response imei`  `cisco securex threat response imsi`  `cisco securex threat response amp computer guid`  `cisco securex threat response odns identity`  `cisco securex threat response odns identity label` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.observable | string |  `ip`  `ipv6`  `user name`  `domain`  `hash`  `sha256`  `md5`  `sha1`  `url`  `email`  `host name`  `mac address`  `file name`  `file path`  `email id`  `cisco securex threat response email subject`  `cisco securex threat response cisco mid`  `cisco securex threat response mutex`  `cisco securex threat response device`  `cisco securex threat response pki serial`  `cisco securex threat response imei`  `cisco securex threat response imsi`  `cisco securex threat response amp computer guid`  `cisco securex threat response odns identity`  `cisco securex threat response odns identity label` 
action\_result\.data\.\*\.verdicts\.\*\.disposition\_name | string | 
action\_result\.data\.\*\.verdicts\.\*\.expiration | string | 
action\_result\.data\.\*\.verdicts\.\*\.module | string | 
action\_result\.data\.\*\.verdicts\.\*\.observable\_type | string | 
action\_result\.data\.\*\.verdicts\.\*\.observable\_value | string |  `ip`  `ipv6`  `user name`  `domain`  `hash`  `sha256`  `md5`  `sha1`  `url`  `email`  `host name`  `mac address`  `file name`  `file path`  `email id`  `cisco securex threat response email subject`  `cisco securex threat response cisco mid`  `cisco securex threat response mutex`  `cisco securex threat response device`  `cisco securex threat response pki serial`  `cisco securex threat response imei`  `cisco securex threat response imsi`  `cisco securex threat response amp computer guid`  `cisco securex threat response odns identity`  `cisco securex threat response odns identity label` 
action\_result\.summary | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric | 