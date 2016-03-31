# letsencrypt-watch

Independent `certwatch` cron script for [letsencrypt](https://letsencrypt.org) certificates.

This was mainly built as I am using [nginx](http://nginx.org/) and the normal `/etc/cron.daily/certwatch` script is not picking up the SSL certificates in my vhosts as it relies on [apache](apache.org) and quits if it is not found:
```shell
test -x /etc/httpd/modules/libmodnss.so || return 0
# and
test -r /etc/httpd/conf/httpd.conf    || return 0
```

Add this shell script to your cronjob to be notified via email when your certificates reach expiry.
The default (without arguments) is to notify the root user, once the certificates will expire in 30 days.


## Usage

All command line arguments are optional and if not specified, the default values are used.

```shell
$ letsencrypt-watch [--period=30] [--email=user@mail.tld] [--path=/etc/letsencryt]

 --period=XX       specify period in days to check for (Default: 30)
 --email=root      specify email to send notifications if period expires (Default: root)
 --path=/etc/path  specify letsencrypt base path (Default: /etc/letsencrypt) 

```

## Example

Put the following example in your cron daily and replace the email with your own.

```shell
@daily /path/to/letsencrypt-watch --email=cytopia@everythingcli.org
```
or
```shell
0 0 * * * /path/to/letsencrypt-watch --email=cytopia@everythingcli.org
```
