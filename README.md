Role Name
=========

This role installs Sentry and configures nginx to serve it.

Requirements
------------

- `snapd`

Role Variables
--------------

Variable | Type | Default | Usage
--- | --- | --- | ---
`sentry_hostname_domain` | string | `example.com` | Domain for Sentry
`sentry_hostname_subdomain` | string | sentry | Subdomain for Sentry
`sentry_enable_cloudflare` | boolean | false | Enable Cloudflare DNS update
`sentry_cloudflare_api_token` | string | none | Cloudflare API token
`sentry_cloudflare_account_email` | string | none | Cloudflare account email
`sentry_enable_local_postgres` | boolean | true | Enable local Postgres install
`sentry_db_name` | string | sentry | Sentry database name
`sentry_db_user` | string | sentry | Sentry database user
`sentry_db_password` | string | insecurepassword | Sentry database password
`sentry_db_host` | string | 127.0.0.1 | Sentry database host
`sentry_db_port` | int | 5432 | Sentry database port
`sentry_enable_local_redis` | boolean | true | Enable local Redis install
`sentry_redis_host` | string | 127.0.0.1 | Sentry redis host
`sentry_redis_port` | int | 6379 | Sentry redis port
`sentry_mail_backend` | string | dummy | Sentry mail backend - See Sentry docs for values
`sentry_mail_host` | string | none | Sentry mail host
`sentry_mail_port` | int | none | Sentry mail port
`sentry_mail_username` | string | none | Sentry mail username
`sentry_mail_password` | string | none | Sentry mail password
`sentry_mail_tls` | boolean | false | Enable Sentry mail TLS
`sentry_mail_address` | string | none | Sentry mail from address
`sentry_bind_ip` | string | 127.0.0.1 | IP to bind Sentry's server to
`sentry_bind_port` | int | 9000 | Port to bind Sentry's server to
`sentry_nginx_conf_options` | string | see `default/main.yml` | Extra options for nginx.conf


Dependencies
------------

- `geerlingguy.postgres`: required if `sentry_enable_local_postgres` is true
- `geerlingguy.redis`: required if `sentry_enable_local_redis` is true
- `geerlingguy.nginx`

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

MIT License

Author Information
------------------

Vidur Butalia
