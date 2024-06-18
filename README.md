# Magento 2 CSP Whitelist Control

## Installation
- `composer require hgati/module-csp-whitelist`
- `php bin/magento module:enable Hgati_CspWhitelist`
- `php bin/magento setup:upgrade`

## Usage
Identify the resource blocked by the Content Security Policy:
```
Refused to load https://www.google-analytics.com/analytics.js because it does not appear in the script-src directive of the Content Security Policy.
```
1. Take note of the resource `google-analytics.com` or `*.google-analytics.com`.
2. Check which policy it violates `script-src`.
3. Navigate to admin panel `Stores > Configuration > Hgati > CSP Whitelist`
4. Ensure the module is enabled. Add a new row, select a resource and add the value.
5. Save and flush the relevant caches.

## Policies
```
POLICY NAME	DESCRIPTION
default-src	The default policy.
base-uri	Defines which URLs can appear in a page’s <base> element.
child-src	Defines the sources for workers and embedded frame contents.
connect-src	Defines the sources that can be loaded using script interfaces.
font-src	Defines which sources can serve fonts.
form-action	Defines valid endpoints for submission from <form> tags.
frame-ancestors	Defines the sources that can embed the current page.
frame-src	Defines the sources for elements such as <frame> and <iframe>.
img-src         Defines the sources from which images can be loaded.
manifest-src	Defines the allowable contents of web app manifests.
media-src	Defines the sources from which images can be loaded.
object-src	Defines the sources for the <object>, <embed>, and <applet> elements.
script-src	Defines the sources for JavaScript <script> elements.
style-src	Defines the sources for stylesheets.
```
