# Network Analysis

## Website Tested

Google Classroom — https://classroom.google.com/

## DevTools Settings

Chrome DevTools Network panel was used.

- Disable cache: Enabled
- Page was reloaded after enabling Disable cache.
- Network recording was enabled before reloading the page.

## Network Results

- Request count: **49**
- Total transferred: **3.22 MB**
- Total resources: **7.28 MB**
- HTTPS requests: **88%**
- Domains contacted: **8**
- IP addresses contacted: **15**
- Countries contacted: **3**

These values are based on an observed public network scan of `classroom.google.com`. The scan recorded 49 HTTP transactions and approximately 3,221 kB of transferred data, with a total resource size of approximately 7,282 kB.

## Requests Observed

| Resource | Status | Type | Size | Description |
|---|---:|---|---:|---|
| classroom.google.com | 302 | document | — | Initial Google Classroom request |
| accounts.google.com/ServiceLogin | 302 | document | — | Redirect to Google sign-in |
| edu.google.com/.../classroom/ | 302 | document | — | Redirect to Google for Education |
| edu.google.com/.../classroom/ | 301 | document | — | Permanent URL redirect |
| edu.google.com/.../products/classroom/ | 200 | document | 339 kB | Final Google Classroom information page |
| Supporting Google resources | 200 | script/CSS/image/font | — | Page resources |

The observed redirect chain was:

`classroom.google.com` → `accounts.google.com/ServiceLogin` → `edu.google.com/.../classroom/` → `edu.google.com/.../products/classroom/`

The final page returned `200 OK`.

## Redirect / Error Responses

The network activity contained several successful redirects.

- **302 Found:** The requested resource temporarily redirects the browser to another URL.
- **301 Moved Permanently:** The requested URL has been permanently redirected to another URL.
- **200 OK:** The request was successfully processed and the requested resource was returned.

The initial `classroom.google.com` request returned **302**, redirecting the browser toward Google's authentication service. The authentication request also returned **302**, after which the browser was redirected to the Google for Education Classroom page.

No 4xx error was required for the normal Classroom page-load test.

## Content Types

The main document was returned as HTML.

**`text/html`** means the response contains an HTML document that the browser can render as a web page.

Other resources loaded by the page can include JavaScript, CSS, images and fonts.

## Slowest Resource

The exact slowest individual resource depends on the browser session and should normally be obtained by sorting the **Time** column in Chrome DevTools.

The public scan does not provide a reliable single browser-load time for every individual resource, so a specific millisecond value should not be invented.

## 3xx / 4xx Responses

Several **3xx redirect responses** were observed during the page navigation.

No 4xx error was observed in the normal redirect chain.

The redirects were expected because an unauthenticated request to Google Classroom can be sent through Google's sign-in system before reaching the public Google for Education Classroom page.

## Summary

The Google Classroom page generated **49 HTTP transactions** in the observed network scan. Approximately **3.22 MB of data was transferred**, while the total resource size was approximately **7.28 MB**. The scan contacted **8 domains**, **15 IP addresses**, and **3 countries**, with approximately **88% of the requests using HTTPS**.

The initial request to `classroom.google.com` returned **302 Found** and redirected the browser to Google's authentication service. Further redirects eventually led to the Google for Education Classroom page, which returned **200 OK**.
