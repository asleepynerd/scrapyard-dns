# Scrapyard London DNS
We got the domain [scrapyard.london](https://scrapyard.london) for this event, and this is the repo to manage it!

[![test](https://github.com/scrapyard-london/dns/workflows/test/badge.svg)](https://github.com/scrapyard-london/dns/actions?query=workflow%3Atest)
[![deploy](https://github.com/scrapyard-london/dns/workflows/deploy/badge.svg)](https://github.com/scrapyard-london/dns/actions?query=workflow%3Adeploy)

This repository is used for managing my DNS configuration through OctoDNS. Please see its documentation for more information.

## Adding a subdomain

1. [Create a fork](https://docs.github.com/en/free-pro-team@latest/github/getting-started-with-github/fork-a-repo) of this repository.
2. In your fork open the [scrapyard.london.yaml](./scrapyard.london.yaml) file and add the following alphabetically based off the subdomain name:

```yaml
SUBDOMAIN_NAME:
  - ttl: 600
    type: CNAME
    value: SOURCE_DOMAIN_OR_IP.
```

3. Replace `SUBDOMAIN_NAME` with the name of the sub-domain. So if the name was `registration` then the subdomain would be `registration.scrapyard.london`.
4. Replace `SOURCE_DOMAIN_OR_IP` with the domain or IP address of the website you want the subdomain to go. If you are using an IP address change `type: CNAME` to `type: A`. Remember to leave that `.` at the end!
5. Commit your changes and [create the PR](https://docs.github.com/en/free-pro-team@latest/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request-from-a-fork)!

That's it! [@Leo](https://github.com/leowilkin) will then review your PR.

If you're asked to make any changes to your pull request, please amend it by commiting to your fork, instead of closing it and creating another.

_Thanks to [revolution-hacks/dns](https://github.com/Revolution-Hacks/dns) and their team for doing ~~most~~ all of the work for me, orig: [hackclub/dns](https://github.com/hackclub/dns)_
