# letsencrypt-watch

`certwatch` cron-check implementation for letsencrypt certificates


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
