# Security

## Overview
- Factors
    - Confidentiality: only authorized subject can access data
    - Integrity: only authorized subject and update data
    - Availability: data available for subject
 - Principle
    + Authentication
    + Authorization
    + Audit
- Crypto
    + Symmetric encryption: encrypt/decrypt by same key
        + DES: US gov, week encrypt, fast
        + IDES: Switzerland, strong encrypt, slow
        + AES: US, strong encrypt, fast
    + Public-key: encrypt/decrypt by public/private key
        + RSA: week encrypt, fast
        + ECC: strong encrypt, slow
    + Hash
        + MD5: 128 bit, medium security, medium performance
        + SHA: 160/256 bit, hight security, slow
- Identification
    + CAS
        + user access app
        + app redirect to identification centre
        + identification identify user and return access token
        + user access app with access token
        + app verify the access token from identification centre
    + JWT
        + store access token in client
    + OAuth
        + after identify by identification centre, app issue its own access token
- Access Control
    + DAC
        + owner control the access
        + linux access
    + Role base access control
        + access base on role
        + admin central management
    + Rule base access control
        + base on rule
        + firewall rule
    + Mandatory access control
        + access by data label
***


​        
## Web Security
- XSS Cross-Site Scripting
    + category
        + Reflection XSS: inject java script
        + Dom XSS: modify the dom
        + Persist XSS: persist script into database
    + result
        + stole cookie
        + unauthorized operation
        + record input
    + protection
        + validate the output
        + parse content
        + filter
        + Content Security Policy: contains HTTP header
```html
Relection 
</h3><script>alert('xss');</script><h3>

DOM
document.write('Search result：' + decodeURIComponent(search));

Persist 
comment </h3><script>alert('xss');</script><h3>

CSP
Content-Security-Policy:default-src ‘none’; script-src ‘self’; 
connect-src ‘self’; img-src ‘self’; style-src ‘self’;
```
