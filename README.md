# letsencrypt-watch

`certwatch` cron implementation for letsencrypt certificates.

Add this shell script to your cronjob to be notified via email when your certificates reach expiry.
The default is to notify user root, once the expiry reaches 30 days.


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
