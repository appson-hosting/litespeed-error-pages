# Customise LiteSpeed error pages

### Apache / cPanel
**Create new error folder**
```
mkdir /usr/local/apache/htdocs_error
```

**CD into new folder**
```
cd /usr/local/apache/htdocs_error
```

**Clone repository**
```
git clone https://github.com/joejordanbrown/litespeed-error-pages.git .
```

To customise the pages fork this repository and make changes and follow steps above but cloning your forked repository.


**Including Error Pages**

Add the following to your `pre_virtualhost_global.conf`

On cPanel this can be found at `WHM >> Service Configuration >> Apache Configuration >> Include Editor >> Pre VirtualHost Include >> All Versions`
```
Alias /htdocs_error /usr/local/apache/htdocs_error/
ErrorDocument 400 /htdocs_error/400.shtml
ErrorDocument 401 /htdocs_error/401.shtml
ErrorDocument 403 /htdocs_error/403.shtml
ErrorDocument 404 /htdocs_error/404.shtml
ErrorDocument 405 /htdocs_error/405.shtml
ErrorDocument 406 /htdocs_error/406.shtml
ErrorDocument 409 /htdocs_error/409.shtml
ErrorDocument 410 /htdocs_error/410.shtml
ErrorDocument 411 /htdocs_error/411.shtml
ErrorDocument 413 /htdocs_error/413.shtml
ErrorDocument 414 /htdocs_error/414.shtml
ErrorDocument 415 /htdocs_error/415.shtml
ErrorDocument 416 /htdocs_error/416.shtml
ErrorDocument 422 /htdocs_error/422.shtml
ErrorDocument 500 /htdocs_error/500.shtml
ErrorDocument 501 /htdocs_error/501.shtml
ErrorDocument 503 /htdocs_error/503.shtml
ErrorDocument 505 /htdocs_error/505.shtml
ErrorDocument 508 /htdocs_error/508.shtml
ErrorDocument 509 /htdocs_error/509.shtml
```

### Preview Error Page

Create `.htaccess` file, replace `***ERROR CODE***` with for example 403

```
RewriteEngine on

RewriteRule ^error - [L,R=***ERROR CODE***]
```
Visit http://domain.tld/error to preview error page.