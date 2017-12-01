# Ansible role for Grafana

Ansible role for [Grafana](http://grafana.org/) on EL 7.x

[![License](http://img.shields.io/:license-mit-blue.svg)](http://doge.mit-license.org)

## Installation
```
$ ansible-galaxy install jmartin.grafana
```

## Getting started
```
---
- hosts: grafana.example.com
  roles:
  - { # Grafana
      role: jmartin.grafana,
      #----- Variables Example
      grafana_ip: "0.0.0.0",
      grafana_port: 3000,
      grafana_admin_password: "password",
      grafana_secret_key: "18Z98oGhk95Oo72OmuG484eBP4g2774c",
      grafana_data_source: {
        isDefault: yes,
        database: telegraf,
        user: root,
        password: root,
        name: training,
        type: influxdb,
        url: 'http://localhost:8086',
        access: proxy,
        basicAuth: false
      }
      #-----/Variables Example
    }
```

## Configurables
```
---
# Packages
grafana_packages:
  - grafana
  - git

# Server Configuration
grafana_ip: "0.0.0.0"
grafana_port: 3000
grafana_admin_password: "password"
grafana_secret_key: "18Z98oGhk95Oo72OmuG484eBP4g2774c"
grafana_session_provider: "memory"
grafana_sessions_provider_config: ""
grafana_custom_dashboars: []

# Data Source
grafana_data_source: {
  isDefault: yes,
  database: telegraf,
  user: root,
  password: root,
  name: training,
  type: influxdb,
  url: 'http://localhost:8086',
  access: proxy,
  basicAuth: false
}

# Plugins
grafana_zabbix_plugin: false
grafana_zabbix_version: "master"

# Google Auth
grafana_auth_google: false
grafana_auth_google_allow_sign_up: "false"
grafana_auth_google_client_id: "some_client_id"
grafana_auth_google_client_secret: "some_client_secret"
grafana_auth_google_allowed_domains: "petalmd.com"
```

## Contributing
Contributions, questions, and comments are all welcomed and encouraged!

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

## Credits
Fork Maintainer:
- [James Martin](https://github.com/jsmartin)

Fork Maintenance:
- [Louis T. Getterman IV](https://github.com/LTGIV)

Forked from:
- [Julien Maitrehenry](https://github.com/jmaitrehenry)

## License

The MIT License

Copyright (c) 2015 PetalMD https://www.petalmd.com

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
