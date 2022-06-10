# PoC for Sourcegraph Gitserver < 3.37.0 RCE (CVE-2022-23642)

Sourcegraph prior to 3.37.0 has a remote code execution vulnerability on its gitserver service. This is due to lack of restriction on git config execution thus "core.sshCommand" can be passed on the HTTP arguments which can contain arbitrary bash commands. Note that this is only possible if gitserver is exposed to the attacker. This is tested on [Sourcegraph 3.36.3](https://github.com/sourcegraph/sourcegraph/releases/tag/v3.36.3)

## Setup for testing docker

A Sourcegraph docker container version 3.63.3 has been used for the testing. The gitserver port 3178 has also been exposed

## Exploitation parameters:
- Exposed Sourcegraph gitserver
- Existing repo on sourcegraph

## POC

![gif](CVE-2022-23642.gif)


## References:
- https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2022-23642
- https://github.com/sourcegraph/sourcegraph