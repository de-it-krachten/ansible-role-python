[![CI](https://github.com/de-it-krachten/ansible-role-python/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-python/actions?query=workflow%3ACI)


# ansible-role-python

Installs python2/python3 from repository


Platforms
--------------

Supported platforms

- Red Hat Enterprise Linux 7<sup>1</sup>
- Red Hat Enterprise Linux 8<sup>1</sup>
- CentOS 7
- RockyLinux 8
- AlmaLinux 8<sup>1</sup>
- Debian 10 (Buster)
- Debian 11 (Bullseye)
- Ubuntu 18.04 LTS
- Ubuntu 20.04 LTS

Note:
<sup>1</sup> : no automated testing is performed on these platforms

Role Variables
--------------
<pre><code>
# Default root-directory for virtual environments
python_virtualenv_root: "{{ ansible_env['HOME'] }}/.virtualenv"

# Install default python packages
python_package_install: True

# Install additional python packages (might be required when compilation is required)
python_package_install_optional: False

# Use list of trusted hosts as defined under python_trusted_hosts
python_trust_hosts: False

# List of trusted hosts
python_trusted_hosts: >
  --trusted-host pypi.org
  --trusted-host files.pythonhosted.org
  --trusted-host pypi.python.org

# Use to become when setting up virtual environments
python_venv_become: root

# Define pip executable
pip_executable: pip

# List of additional pip clients
pip_clients:
  - pip
  - pip3

# Upgrade pip (site-packages) when out-dated
pip_site_upgrade: false

# Upgrade pip (venv) when out-dated
pip_upgrade: false

# Python (from source)
python_from_source: false
python_version: 3.8.12
python_version_minor: "{{ python_version | regex_replace('^(\\d\\.\\d)(.*)', '\\1') }}"

python_binary: python{{ python_version_minor }}
python_binary_full: /usr/local/bin/{{ python_binary }}

python_url: https://www.python.org/ftp/python/{{ python_version }}/Python-{{ python_version }}.tgz
</pre></code>


Example Playbook
----------------

<pre><code>
- name: sample playbook for role 'python'
  hosts: all
  vars:
    python2: false
    python3: true
    python_virtualenv_root: /tmp/venv
    python_virtualenvs:
      - name: sample
        user: sample
        recreate: false
        python: /usr/bin/python3
        site_packages: false
        packages:
          - lxml
          - dnspython
  tasks:
    - name: Create user sample
      user:
        name: sample

    - name: Include role 'python'
      include_role:
        name: python
</pre></code>
