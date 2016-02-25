## Introduction

All of the configuration files for the Phanbook are store in the ```core/config/config.php``` file. So feel free to look through the files and get familiar with the options available to you.

### Environment Configuration

It is often helpful to have different configuration values based on the environment the application is running in. For example, you may wish to use a debug on your local development machine and it not use on the production server. It is easy to accomplish this using environment based configuration.

You just to change  option debug the ```false``` to ```true`` like below

```
  [...]
  debug'  => false,

```

Also see at https://github.com/phanbook/phanbook/blob/master/core/config/config.example.php#L72

### Github

To authentication via Github you need to created your app on [github](https://github.com/settings/applications/new). Every registered OAuth application is assigned a unique Client ID and Client Secret. The Client Secret should not be shared! That includes checking the string into your repository. See image below

![](/img/github_app.png)

Then go to ```core/config/config.php``` files change to it, some like:

```
/**
 * Your client ID and client secret keys come from
 *
 * @link https://github.com/settings/applications/new
 */
'github'      => array(
    'clientId'     => '7c3724d3a593eff3ebef',
    'clientSecret' => '0dede75fd2351242e51c69b4aa50ce130862ef05',
    'redirectUri'  => 'http://dev.phanbook.com/auth/github/access_token',
    'scopes'       => ['user', 'email']
),
````
Remember you need to change the domain ```http://dev.phanbook.com``` to your domain