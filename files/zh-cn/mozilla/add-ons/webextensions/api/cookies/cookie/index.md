---
title: cookies.Cookie
slug: Mozilla/Add-ons/WebExtensions/API/cookies/Cookie
---

{{AddonSidebar()}}

The `Cookie` type of the {{WebExtAPIRef("cookies")}} API represents information about an HTTP cookie.

## 类型

这玩意是一个 Object，可以包含以下的属性：

- `domain`
  - : 储存这个 cookie 对应网站的字符串 (例如 "www\.tengxun.com")。
- `expirationDate`{{optional_inline}}
  - : A `number` representing the expiration date of the cookie as the number of seconds since the UNIX epoch. Not provided for session cookies.
- `firstPartyDomain`
  - : A `string` representing the first-party domain associated with the cookie. This will be an empty string if the cookie was set while first-party isolation was off. See [First-party isolation](/zh-CN/Add-ons/WebExtensions/API/cookies#First-party_isolation).
- `hostOnly`
  - : A `boolean`, `true` if the cookie is a host-only cookie (i.e. the request's host must exactly match the domain of the cookie), or `false` otherwise.
- `httpOnly`
  - : A `boolean`, `true` if the cookie is marked as HttpOnly (i.e. the cookie is inaccessible to client-side scripts), or `false` otherwise.
- `name`
  - : A `string` representing the name of the cookie.
- `path`
  - : A `string` representing the path of the cookie.
- `secure`
  - : A `boolean`, `true` if the cookie is marked as secure (i.e. its scope is limited to secure channels, typically HTTPS), or `false` otherwise.
- `session`
  - : A `boolean`, `true` if the cookie is a session cookie, or `false` if it is a persistent cookie with an expiration date.
- `sameSite`
  - : A {{WebExtAPIRef("cookies.SameSiteStatus")}} value that indicates the SameSite state of the cookie.
- `storeId`
  - : A `string` representing the ID of the cookie store containing this cookie, as provided by {{WebExtAPIRef("cookies.getAllCookieStores()")}}.
- `value`
  - : 代表 cookie 的值的一个字符串。

## Browser compatibility

{{Compat("webextensions.api.cookies.Cookie")}}

## 举例

Cookies API 中的大多数方法都将 `Cookie` 对象用作输入参数或用作返回值的一部分。例如调用 {{WebExtAPIRef("cookies.getAll()")}} 将会返回一个 `Cookie` 对象的数组。

在下面的例子中我们将会获取所有的 cookie，然后 `console.log()` 出这些 `Cookie` 对象所对应的值。

```js
function logCookies(cookies) {
  for (cookie of cookies) {
    console.log(`Domain: ${cookie.domain}`);
    console.log(`Name: ${cookie.name}`);
    console.log(`Value: ${cookie.value}`);
    console.log(`Persistent: ${!cookie.session}`);
  }
}

var gettingAll = browser.cookies.getAll({});
gettingAll.then(logCookies);
```

{{WebExtExamples}}

> **备注：** 这 API 是基于 Chromium 的 [`chrome.cookies`](https://developer.chrome.com/extensions/cookies#type-Cookie) API 的。这个文档来自于 Chromium code 中的 [`cookies.json`](https://chromium.googlesource.com/chromium/src/+/master/chrome/common/extensions/api/cookies.json) 。
>
> Microsoft Edge compatibility data is supplied by Microsoft Corporation and is included here under the Creative Commons Attribution 3.0 United States License.

<!--
// Copyright 2015 The Chromium Authors. All rights reserved.
//
// Redistribution and use in source and binary forms, with or without
// modification, are permitted provided that the following conditions are
// met:
//
//    * Redistributions of source code must retain the above copyright
// notice, this list of conditions and the following disclaimer.
//    * Redistributions in binary form must reproduce the above
// copyright notice, this list of conditions and the following disclaimer
// in the documentation and/or other materials provided with the
// distribution.
//    * Neither the name of Google Inc. nor the names of its
// contributors may be used to endorse or promote products derived from
// this software without specific prior written permission.
//
// THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
// "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT
// LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR
// A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT
// OWNER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
// SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT
// LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE,
// DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY
// THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
// (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
// OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
-->
