# GitHub

This plugin allows GitHub users to authenticate to Xen-Orchestra.

The first time a user signs in, XO will create a new XO user with the same identifier, without any permission.

First you need to configure a new app in your GitHub account:

![](https://github.com/vatesfr/xo-server-auth-github/blob/master/github.png)

When you got your `clientID` and your `clientSecret`, you can configure them in the GitHub Plugin inside "Settings/Plugins" view of Xen Orchestra.

Be sure to activate the plugin. When it's done, you'll see a link in the log in view, this is where you'll go to authenticate:

![]()

## Debugging

If you can't log in with your GitHub settings, please check the logs of `xo-server` while you attempt to connect. It will give you hints about the error encountered. You can do that with a `tail -f /var/log/syslog -n 100` on your XOA.

## Missing plugin?

If you don't find the GitHub plugin in the list, be sure to have it displayed in your Xen Orchestra configuration (in `/etc/xo-server/config.yaml`):

```
plugins:

  auth-github:
```

If it's not the case, don't forget to restart the service after your modification, with `systemctl restart xo-server.service`.