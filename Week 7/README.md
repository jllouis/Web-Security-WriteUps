# Project 7 - WordPress Pentesting

Time spent: 100 hours spent in total

> Objective: Find, analyze, recreate, and document three vulnerabilities affecting an old version of WordPress

## Pentesting Report

1. CVE-2015-5714 - Cross-site scripting vulnerability when processing shortcode tags
  - [x] Summary: A Cross-site scripting (XSS) vulnerability in WordPress before 4.3.1 allows remote attackers to inject arbitrary web script or HTML by leveraging the mishandling of unclosed HTML elements during processing of shortcode tags.
    - Vulnerability types: XSS
    - Tested in version:4.2
    - Fixed in version: 4.3
  - [x] GIF Walkthrough: 
  - [x] Steps to recreate: In the text editor of a new post, insert the following:
	`[caption width="3" caption='<a href="' ">]</a><a href="http://onmouseover='alert(1)'">XSS!</a>`
  - [x] Affected source code: 
- [Link 1](https://core.trac.wordpress.org/browser/branches/4.1/src/wp-includes/post.php)
2. CVE-2016-7168Authenticated Stored Cross-Site Scripting via Image Filename 
  - [x] Summary: An attacker can create a specially crafted image file name which, when uploaded in WordPress, injects malicious JavaScript code into the application. An attacker can use this vulnerability to perform a wide variety of actions, such as stealing victims' session tokens or login credentials, and performing arbitrary actions on their behalf.
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.6.1
  - [x] GIF Walkthrough: 
  - [x] Steps to recreate: In a new media post, upload an image with the name: `filename<img src=a onerror=alert(1)>.png` 
  - [x] Affected source code: 
- [Link 2](https://core.trac.wordpress.org/browser/branches/4.2/src/wp-admin/includes/media.php)
3. In WordPress before 4.7.3 (wp-includes/embed.php), there is authenticated Cross-Site Scripting (XSS) in YouTube URL Embeds. - CVE 2017-6817
  - [x] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.7.3
  - [x] GIF Walkthrough: 
  - [x] Steps to recreate: Insert the following into the text editor of a post: `[embed src='https://youtube.com/embed/12345\x3csvg onload=alert(1)\x3e'][/embed]`
  - [x] Affected source code:
- [Link 3](https://core.trac.wordpress.org/browser/branches/4.1/src/wp-includes/media.php)
## Assets

List any additional assets, such as scripts or files

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Describe any challenges encountered while doing the work

## License

    Copyright [2017] [Jose L. Louis]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
