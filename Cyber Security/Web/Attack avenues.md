
# Request

Basic format:
```
VERB /resource/locator HTTP/1.1
Header1: Value1
Header2: Value2
.
.
<Body>
```

Request headers:

| Header          | Use                                       |
| --------------- | ----------------------------------------- |
| `Host`          | desired host handling the request         |
| `Accept`        | Indicates MIME type(s) accepted by client |
| `Cookie`        | pass cookie data to server                |
| `Referer`       | Which pages lead to this url              |
| `Authorization` | Authorization tokens,etc                  |
- Basic authentication is easily broken.

---
# Cookies

scope:
- reside on client for fixed period of time.
- cookies added for `.example.com` can be read by any subdomain of `example.com`.
- `test.example.com` can set cookies for its own subdomains `*.test.example.com` and also for its parent `example.com` but not for siblings e.g., `prod.example.com`.

important flags:
- `secure`: accessible to HTTPS pages only
- `HTTPOnly`: cannot be read by javascript

----
# HTML
- HTML needs to be parsed according to relevant specs, discrepancies in parsing between different network components may create vulnerability.
- The leniency of browsers for HTML is exploitable.
- If types are not specified, heuristics are applied to determine type. Thus garbled data can change lead to another type being determined leading to vulnerability.

----
# Same Origin Policy

Origin matching:
- protocols should match
- port numbers should match
- domain names must be exact match - no wildcards or subdomain walking

Enabling CORS(Cross Origin Resource Sharing) loosens SOP, leading to many vulnerabilities.  
- enables XMLHTTPRequests to domains outside origin
- allows passing of receiving domain's cookies

----
# CSRF
Cross Site Request Forgery

mitigation: user CSIRF tokens

----
