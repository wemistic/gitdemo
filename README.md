This is a demo git project.
Please ignore.
Steps to add github caches to prevent putting the git-access token everytime.
1. verify your linux dnf using dnf --version command
2. Install the approriate gh client from the https://github.com/cli/cli/blob/trunk/docs/install_linux.md
3. then gh auth login will prompts you them input the git access token for the password.
========================================================================================================
[student@controlnode gitdemo]$ dnf --version
4.14.0
  Installed: dnf-0:4.14.0-17.el9.noarch at Fri 21 Feb 2025 04:41:22 AM GMT
  Built    : Red Hat, Inc. <http://bugzilla.redhat.com/bugzilla> at Tue 06 Aug 2024 11:11:05 AM GMT

  Installed: rpm-0:4.16.1.3-34.el9.x86_64 at Fri 21 Feb 2025 04:35:42 AM GMT
  Built    : Red Hat, Inc. <http://bugzilla.redhat.com/bugzilla> at Thu 15 Aug 2024 09:07:36 AM GMT
[student@controlnode gitdemo]$ dnf --version
4.14.0
  Installed: dnf-0:4.14.0-17.el9.noarch at Fri 21 Feb 2025 04:41:22 AM GMT
  Built    : Red Hat, Inc. <http://bugzilla.redhat.com/bugzilla> at Tue 06 Aug 2024 11:11:05 AM GMT

  Installed: rpm-0:4.16.1.3-34.el9.x86_64 at Fri 21 Feb 2025 04:35:42 AM GMT
  Built    : Red Hat, Inc. <http://bugzilla.redhat.com/bugzilla> at Thu 15 Aug 2024 09:07:36 AM GMT
[student@controlnode gitdemo]$ # DNF4 installation commands
sudo dnf install 'dnf-command(config-manager)'
sudo dnf config-manager --add-repo https://cli.github.com/packages/rpm/gh-cli.repo
sudo dnf install gh --repo gh-cli
Updating Subscription Management repositories.
Last metadata expiration check: 4:34:51 ago on Wed 30 Apr 2025 06:10:45 PM EDT.
Package dnf-plugins-core-4.3.0-16.el9.noarch is already installed.
Dependencies resolved.
Nothing to do.
Complete!
Updating Subscription Management repositories.
Adding repo from: https://cli.github.com/packages/rpm/gh-cli.repo
Updating Subscription Management repositories.
packages for the GitHub CLI                                                                                                              13 kB/s | 2.8 kB     00:00
Dependencies resolved.
========================================================================================================================================================================
 Package                             Architecture                            Version                                      Repository                               Size
========================================================================================================================================================================
Installing:
 gh                                  x86_64                                  2.72.0-1                                     gh-cli                                   14 M

Transaction Summary
========================================================================================================================================================================
Install  1 Package

Total download size: 14 M
Installed size: 37 M
Is this ok [y/N]: y
Downloading Packages:
gh_2.72.0_linux_amd64.rpm                                                                                                               7.4 MB/s |  14 MB     00:01
------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Total                                                                                                                                   7.4 MB/s |  14 MB     00:01
packages for the GitHub CLI                                                                                                              12 kB/s | 4.7 kB     00:00
Importing GPG key 0x75716059:
 Userid     : "GitHub CLI <opensource+cli@github.com>"
 Fingerprint: 2C61 0620 1985 B60E 6C7A C873 23F3 D4EA 7571 6059
 From       : https://keyserver.ubuntu.com/pks/lookup?op=get&search=0x23F3D4EA75716059
Is this ok [y/N]: y
Key imported successfully
Running transaction check
Transaction check succeeded.
Running transaction test
Transaction test succeeded.
Running transaction
  Preparing        :                                                                                                                                                1/1
  Installing       : gh-2.72.0-1.x86_64                                                                                                                             1/1
  Running scriptlet: gh-2.72.0-1.x86_64                                                                                                                             1/1
  Verifying        : gh-2.72.0-1.x86_64                                                                                                                             1/1
Installed products updated.

Installed:
  gh-2.72.0-1.x86_64

Complete!
[student@controlnode gitdemo]$ gh auth login
? Where do you use GitHub? GitHub.com
? What is your preferred protocol for Git operations on this host? HTTPS
? Authenticate Git with your GitHub credentials? Yes
? How would you like to authenticate GitHub CLI? Paste an authentication token
Tip: you can generate a Personal Access Token here https://github.com/settings/tokens
The minimum required scopes are 'repo', 'read:org', 'workflow'.
? Paste your authentication token:
X Sorry, your reply was invalid: Value is required
? Paste your authentication token: ****************************************
- gh config set -h github.com git_protocol https
✓ Configured git protocol
! Authentication credentials saved in plain text
✓ Logged in as wemistic

