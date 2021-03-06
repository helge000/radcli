# Description
The radcli library provides a Ruby interface for performin actions on a Active Directory domain using the realmd/adcli tool.
(adcli: https://www.freedesktop.org/software/realmd/adcli/devel-building.html)

# Requirements
OpenLDAP client libraries and MIT Kerberos libraries.

# Synposis
```ruby
  require 'radcli'

  # Connnect to the domain as a admin user with a password.
  adconn = Adcli::AdConn.new("ad.example.com")

  adconn.set_login_user("admin")
  adconn.set_user_password("p@ssw0rd")
  adconn.set_domain_realm("AD.EXAMPLE.COM")
  adconn.set_domain_controller("dc.ad.example.com")

  res = adconn.connect

  # Join a new computer to the domain. Set a default password.
  enroll = AdCli::AdEnroll.new(adconn)
  enroll.set_computer_name("adconn")
  enroll.set_computer_password("p@ssw0rd")
  enroll.join()

  # Delete the computer from the domain.ö
  enroll.delete()
```

# Notes
...

# Authors
* Mårten Cassel

# TODO
* Add tests
* Rake and gemspec

# License
TODO
  
