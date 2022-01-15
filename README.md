[![CI](https://github.com/de-it-krachten/ansible-role-python/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-python/actions?query=workflow%3ACI)


# ansible-role-python

Installs python2/python3 from repository


Platforms
--------------

Supported platforms

- CentOS 7
- CentOS 8
- Debian 10 (Buster)
- Debian 11 (Bullseye)
- Ubuntu 18.04 LTS
- Ubuntu 20.04 LTS
- Fedora 34



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

# Upgrade pip when out-dated
pip_upgrade: false
</pre></code>


Example Playbook
----------------

<pre><code>
- name: Converge
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

    - name: Include role 'ansible-role-python'
      include_role:
        name: ansible-role-python
</pre></code>
