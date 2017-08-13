# Week7Lab

-Exploit #1: WordPress 4.2 - Persistent Cross-Site Scripting:

1. Description: WordPress 4.2 is vulnerable to a stored XSS. A user can inject JavaScript code in WordPress comments. The user first makes the comment text too long (at least 64 KB because The MySQL TEXT type size limit is 64 kilobytes) such that it is inserted into the database as truncated. The truncation results in malformed HTML generated on the page. The script is triggered when the comment is viewed. When admin triggers the comment under default settings, the vulnerability executes an arbitrary code on the server via the plugin and theme editors. 

2. The types / classes of vulnerabilities involved and any related CVE identifiers: 
CVE-2015-3440 (https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2015-3440)

3. Identify affected versions and patches: WordPress 4.2

4. Links to the source code:
  Enter the following as a comment text: 
  <a title='x onmouseover=alert(unescape(/hello%20world/.source)) style=position:absolute;left:0;top:0;width:5000px;height:5000px  AAAAAAAAAAAA...[64 kb]..AAA'></a>

5. Screen cap: exploit1-1.jpg and exploit1-2.jpg

Source: http://klikki.fi/adv/wordpress2.html
Ref: https://www.exploit-db.com/exploits/36844/


-Exploit #2: WordPress < 4.2.3 Stored XSS

1. Description: Under default configuration, the attack requires a Contributor or Author level account. The attacker would insert specially formatted HTML code containing JavaScript on a WordPress page or post. The malicious script is executed when an administrator views the page or the post.

2. The types / classes of vulnerabilities involved and any related CVE identifiers: 
CVE-2015-5622 (https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2015-5622)

3. Identify affected versions and patches: Versions before 4.2.3 starting from at least 3.0 are vulnerable.

4. Links to the source code:
The following code demonstrates the vulnerability. It should be entered in a page or posting using the HTML edit mode:
 <a href="[caption code=">]</a><a title=" onmouseover=alert('test')  ">link</a>A 

5. Screen cap: : exploit2-1.jpg and exploit2-2.jpg

Ref: https://klikki.fi/adv/wordpress3.html

-Exploit #3: WordPress 2.5-4.6 - Authenticated Stored Cross-Site Scripting via Image Filename

1. Description: An attacker can exploit this vulnerability by crafting an image file name with Cross-Site Scripting payload. He includes some javascript code as the filename such that an admin uploads or views the image with the malicious file name. When admin views the attachment file in WordPress, it injects malicious JavaScript code into the application. An attacker can use this vulnerability to perform a wide variety of actions, such as stealing victims' session tokens or login credentials, and performing arbitrary actions on their behalf.

2. The types / classes of vulnerabilities involved and any related CVE identifiers: 
CVE-2016-7168 (http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2016-7168)

3. Identify affected versions and patches: Wordpress 4.2

4. Links to the source code:
When an image with a file name such as "andy<img src=a onerror=alert(document.cookie)>.jpg" is uploaded and viewed within WordPress the script code is executed:

5. Screen cap: : exploit3-1.jpg and exploit3-2.jpg

Ref: https://wpvulndb.com/vulnerabilities/8615

## Video Walkthrough

Here's a walkthrough of implemented user stories:

<img src='https://github.com/zakia00/Week2Lab/blob/master/week7.gif' title='Video Walkthrough of Week7 Lab' width='' alt='Video Walkthrough' />

GIF created with [LiceCap](http://www.cockos.com/licecap/).

## License

    Copyright [2017] [Kazi Zakia Sultana]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
