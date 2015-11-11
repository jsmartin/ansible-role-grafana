# Ansible role for Grafana

Ansible role for [Grafana](http://grafana.org/) on RHEL 7.x

[![License](http://img.shields.io/:license-mit-blue.svg)](http://doge.mit-license.org)

## Installation
```
$ ansible-galaxy install jmaitrehenry.grafana
```

## Getting started
```
---
- hosts: grafana.example.com
  roles:
    - jmaitrehenry.grafana
```

## Configurables
```
---
grafana_packages:
  - "https://grafanarel.s3.amazonaws.com/builds/grafana-2.5.0-1.x86_64.rpm"
  - git

grafana_ip: "0.0.0.0"
grafana_port: 3000
grafana_admin_password: "password"
grafana_secret_key: "18Z98oGhk95Oo72OmuG484eBP4g2774c"
grafana_session_provider: "memory"
grafana_sessions_provider_config: ""
grafana_custom_dashboard: false

# Plugins
grafana_zabbix_plugin: false
grafana_zabbix_version: "master"

# Google Auth
grafana_auth_google: false
grafana_auth_google_allow_sign_up: "false"
grafana_auth_google_client_id: "some_client_id"
grafana_auth_google_client_secret: "some_client_secret"
grafana_auth_google_allowed_domains: "petalmd.com"

# Nginx
grafana_nginx: true
grafana_nginx_ssl: false
grafana_nginx_ssl_certificate: "/etc/nginx/ssl/cert"
grafana_nginx_ssl_certificate_key: "/etc/nginx/ssl/key"
grafana_nginx_ssl_dhparam: "/etc/nginx/ssl/dhparam.pem"
grafana_nginx_ssl_trusted_certificate: "/etc/nginx/ssl/provider.crt"
```

## Contributing
Contributions, questions, and comments are all welcomed and encouraged!

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

## Credits

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