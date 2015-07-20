# Contribution Guide

- [Bug Reports](#bug-reports)
- [Core Development Discussion](#core-development-discussion)
- [Which Branch?](#which-branch)
- [Security Vulnerabilities](#security-vulnerabilities)
- [Coding Style](#coding-style)

<a name="bug-reports"></a>
## Bug Reports

To encourage active collaboration, Phanbook strongly encourages pull requests, not just bug reports. "Bug reports" may also be sent in the form of a pull request containing a failing test.

However, if you file a bug report, your issue should contain a title and a clear description of the issue. You should also include as much relevant information as possible and a code sample that demonstrates the issue. The goal of a bug report is to make it easy for yourself - and others - to replicate the bug and develop a fix.

Remember, bug reports are created in the hope that others with the same problem will be able to collaborate with you on solving it. Do not expect that the bug report will automatically see any activity or that others will jump to fix it. Creating a bug report serves to help yourself and others start on the path of fixing the problem.

The Phanbook source code is managed on Github, and there are repositories for each of the Phanbook projects:

- [Phanbook Application](https://github.com/Phanbook/Phanbook)
- [Phanbook Documentation](https://github.com/Phanbook/docs)
- [Phanbook Cashier](https://github.com/Phanbook/cashier)
- [Phanbook Envoy](https://github.com/Phanbook/envoy)
- [Phanbook Homestead](https://github.com/Phanbook/homestead)
- [Phanbook Website](https://github.com/Phanbook/portal.phanbook)
- [Phalcon Framework](https://github.com/phalcon/cphalcon)


<a name="core-development-discussion"></a>
## Core Development Discussion

Discussion regarding bugs, new features, and implementation of existing features takes place in the `#internals` channel of the [Phalconchats](http://chat.phalcontip.com) Slack team. Phanbook, the maintainer of Phanbook, is typically present in the channel on weekdays from 8am-5pm (UTC-06:00 or America/Chicago), and sporadically present in the channel at other times.

<a name="which-branch"></a>
## Which Branch?

**All** bug fixes should be sent to the latest stable branch. Bug fixes should **never** be sent to the `master` branch unless they fix features that exist only in the upcoming release.

**Minor** features that are **fully backwards compatible** with the current Phanbook release may be sent to the latest stable branch.

**Major** new features should always be sent to the `master` branch, which contains the upcoming Phanbook release.


<a name="security-vulnerabilities"></a>
## Security Vulnerabilities

If you discover a security vulnerability within Phanbook, please send an e-mail to us at <a href="mailto:hello@phanbook.com">helllo@phanbook.com</a>. All security vulnerabilities will be promptly addressed.

<a name="coding-style"></a>
## Coding Style

Phanbook follows the [PSR-2](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-2-coding-style-guide.md) coding standard and the [PSR-4](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-4-autoloader.md) autoloading standard.
