# sheets-hyperlink-proxy

`sheets-hyperlink-proxy` is a simple proxy to allow Google Sheets to open hyperlinks with custom protocols.
Google Sheets only allows certain protocols such as `http://`, `https://`, `mailto:`, `aim://`, `ftp://`, `gopher://`, `telnet://`, and `news://`.

This utility helps to bypass this restriction by redirecting the request to the desired custom protocol URI, sent as a parameter.

## Usage

To use this utility, you can simply append the URI you want to open as a parameter to the URL of the proxy.

```plaintext
https://kladdkaka.github.io/sheets-hyperlink-proxy/?uri=<URI>
```

The URI should be URL-encoded, and will be decoded before redirecting the request.

### Example

To create a hyperlink in Google Sheets that sends an SMS, you can use the following formula:

```plaintext
=HYPERLINK("https://kladdkaka.github.io/sheets-hyperlink-proxy/?uri=" & ENCODEURL("sms:" & D2 & "?&body=" & ENCODEURL(J23)), "Send SMS")
```