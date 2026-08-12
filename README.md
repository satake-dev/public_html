# public_html

🌐 **[https://satake.me/~thiago](https://satake.me/~thiago)** 
[![Deploy](https://github.com/satake-dev/public_html/actions/workflows/azure-static-web-apps-red-ocean-0c82af80f.yml/badge.svg)](https://github.com/satake-dev/public_html/actions/workflows/azure-static-web-apps-red-ocean-0c82af80f.yml)

## From local user folders to cloud-native publishing

This repository is both a personal website and a small historical tribute to how web publishing has evolved.

### The old model: Linux users, Apache, and ~/public_html

For many years, especially from the late 1990s through the 2000s (and in many places into the early 2010s), a common web hosting pattern was built around Linux multi-user servers and Apache HTTP Server.

Each person had a Unix account under /home, and Apache could expose content from a per-user folder named public_html. The classic URL pattern was:

- http://server/~username

For example, if a user account was thiago, Apache could serve files from:

- /home/thiago/public_html

This behavior was usually enabled by the Apache UserDir mechanism and controlled by configuration files such as:

- /etc/apache2/mods-enabled/userdir.conf (Debian/Ubuntu style)
- /etc/httpd/conf.d/userdir.conf (RHEL/CentOS style)
- /etc/apache2/apache2.conf or /etc/httpd/conf/httpd.conf
- Virtual host files under /etc/apache2/sites-available/

In many environments, maintainers also relied on .htaccess files for per-directory overrides (rewrites, basic auth, cache policies, and access controls).

This approach was practical and democratized publishing: universities, research labs, companies, and shared-hosting providers could let many users publish pages quickly without provisioning separate servers for each site.

### The current model: Static Web Apps integrated with GitHub

Today, this project uses a modern cloud delivery path:

- Source code stored in GitHub
- Automated deployment through GitHub Actions
- Hosting on Azure Static Web Apps

Instead of manually copying files via SSH/SCP to a server directory, every change is versioned, reviewed, and deployed by pipeline. The platform handles distribution and secure delivery, while the repository remains the single source of truth.

This project also includes routing behavior to emulate the classic user-path experience under /~thiago, preserving the old-school identity while using a fully modern deployment architecture.

### Why this project exists

This repository is intentionally simple in technology and strong in meaning: it connects two eras.

I am very happy to see this evolution. What once required manual server administration, Apache module tuning, and per-user filesystem conventions can now be delivered reliably from cloud-native services tightly integrated with Git workflows.

This project is a concrete proof of that evolution.
