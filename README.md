# codepath-week-7
Time Spent: Almost 10 Hours
Objective: Find, analyze, recreate, and document **3 vulnerabilities** affecting an old version of WordPress

## Pentesting Report
1. WordPress <= 4.2 - Unauthenticated Stored Cross-Site Scripting
Summary:
- Vulnerability types: XSS
- Tested in version: 4.2
- Fixed in version: 4.2
- Gif Walkthrough: https://imgur.com/a/pOemO

Steps to recreate - In order to recreate this hack, you need to go to the comments section of the page and enter in <script>while(true){alert("anything you want");}</script> in the comments section. Next you click submit and it should alert whatever you typed inside the alert function. Also since its  while true so it will keeping alerting the user.

2. WordPress 2.5-4.6 - Authenticated Stored Cross-Site Scripting (XSS) via Image Filename
Summary:
- Vulnerability types: XSS
- Tested in version: 4.2.2
- Fixed in version: 4.2.10
- Gif Walkthrough: https://imgur.com/a/8m21v

Steps to recreate - In order to recreate this hack, you need to first upload a img file that has .jpg at the end. Next you click on the image and set the title as <img src=a onerror=alert(document.cookie)>.jpg. Next you click the view attachment page and the alert function will appear with the current cookie infomation.

3. WordPress 4.0-4.7.2 - Authenticated Stored Cross-Site Scripting (XSS) in YouTube URL Embeds
Summary:
- Vulnerability types: XSS 
- Tested in version: 4.2.2
- Fixed in version: 4.2.15
- Gif Walkthrough: https://imgur.com/a/cxzHZ

Steps to recreate - In order to recreate this hack, you need to first create a new post, then you paste this url "[embed src='https://youtube.com/embed/12345\x3csvg onload=alert(1)\x3e'][/embed]". As soon as you paste you should see a number 1 appear on the screen.

## Resources
GIFs created with [LiceCap](http://www.cockos.com/licecap/)

## License

    Copyright  [Brandon Innis]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
