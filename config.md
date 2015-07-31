## Introduction

All of the configuration files for the Phanbook are store in the ```common/config/config.php``` file. So feel free to look through the files and get familiar with the options available to you.

### Environment Configuration

It is often helpful to have different configuration values based on the environment the application is running in. For example, you may wish to use a debug on your local development machine and it not use on the production server. It is easy to accomplish this using environment based configuration.

You just to change  option debug the ```false``` to ```true`` like below

```
  [...]
  debug'  => false,

```

Also see at https://github.com/phanbook/phanbook/blob/master/common/config/config.example.php#L72