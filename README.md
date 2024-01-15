[![CI](https://github.com/de-it-krachten/ansible-role-python/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-python/actions?query=workflow%3ACI)


# ansible-role-python

Installs python from repository



## Dependencies

#### Roles
None

#### Collections
- {'name': 'community.general'}

## Platforms

Supported platforms

- Red Hat Enterprise Linux 7<sup>1</sup>
- Red Hat Enterprise Linux 8<sup>1</sup>
- Red Hat Enterprise Linux 9<sup>1</sup>
- CentOS 7
- RockyLinux 8
- RockyLinux 9
- OracleLinux 8
- OracleLinux 9
- AlmaLinux 8
- AlmaLinux 9
- SUSE Linux Enterprise 15<sup>1</sup>
- openSUSE Leap 15
- Debian 11 (Bullseye)
- Debian 12 (Bookworm)
- Ubuntu 20.04 LTS
- Ubuntu 22.04 LTS
- Fedora 37
- Fedora 38
- Alpine 3

Note:
<sup>1</sup> : no automated testing is performed on these platforms

## Role Variables
### defaults/main.yml
<pre><code>
# Python versions to install
python2: false
python3: true

# Default root-directory for virtual environments
python_virtualenv_root: "{{ ansible_env['HOME'] }}/.virtualenv"

# Install default python packages
python_package_install: true

# Install additional python packages (might be required when compilation is required)
python_package_install_optional: false

# List of pypi packages that should exist in the virtualenv
python_virtualenv_packages:
  - pip
  - setuptools
  - wheel

# Upgrade main package for new virtual environments
python_virtualenv_upgrade: true

# Execute code for venv creation only
python_virtualenv_only: false

# Use list of trusted hosts as defined under python_trusted_hosts
python_trust_hosts: false

# List of trusted hosts
python_trusted_hosts: >
  --trusted-host pypi.org
  --trusted-host files.pythonhosted.org
  --trusted-host pypi.python.org

# Use to become when setting up virtual environments
python_venv_become: root

# Custom template for /etc/pip.conf file
# python_custom_pip_conf: templates/pip.conf.j2

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

# virtual environments to set-up
python_virtualenvs: []

# virtual env command
python_virtualenv_command: /usr/bin/virtualenv

# Python (from source)
python_from_source: false
python_version: 3.8.12
python_version_minor: "{{ python_version | regex_replace('^(\\d\\.\\d)(.*)', '\\1') }}"

python_binary: python{{ python_version_minor }}
python_binary_full: /usr/local/bin/{{ python_binary }}

python_url: https://www.python.org/ftp/python/{{ python_version }}/Python-{{ python_version }}.tgz
</pre></code>

### defaults/Ubuntu-20.yml
<pre><code>
# Python 3.9
python39: false
python39_command: /usr/bin/python3.9
python39_virtualenv: /usr/bin/virtualenv
python39_packages:
  - python3.9
  - python3.9-venv

python39_packages_optional:
  - python3.9-dev
</pre></code>

### defaults/Fedora.yml
<pre><code>
# Python2
python2: false
python2_command: /usr/bin/python2
python2_virtualenv: /usr/bin/virtualenv
python2_packages:
  - python2
  - python2-libs
  - python2-devel
  - python2-pip
  - python2-virtualenv
  - libselinux-python
python2_packages_optional:
  - gcc
  - glibc-devel
  - openssl-devel

# Python3
python3: true
python3_command: /usr/bin/python3
python3_virtualenv: /usr/bin/virtualenv
python3_packages:
  - python3
  - python3-libs
  - python3-pip
  - python3-virtualenv
  - python3-libselinux
python3_packages_optional:
  - gcc
  - python3-devel
  - glibc-devel
  - openssl-devel
  - libffi-devel

# Python 3.8
python38: false
python38_command: /usr/bin/python3.8
python38_virtualenv: /usr/bin/virtualenv
python38_packages:
  - python3.8
python38_packages_optional: []

# Python 3.9
python39: false
python39_command: /usr/bin/python3.9
python39_virtualenv: /usr/bin/virtualenv
python39_packages:
  - python3.9
python39_packages_optional: []
</pre></code>

### defaults/family-RedHat-7.yml
<pre><code>
# Python2
python2: false
python2_command: /usr/bin/python2
python2_virtualenv: /usr/bin/virtualenv-2.7
python2_packages:
  - python
  - python-libs
  - python-pip
  - python-virtualenv
  - libselinux-python
python2_packages_optional:
  - gcc
  - glibc-devel
  - python-devel
  - openssl-devel
  - libffi-devel

# Python3
python3: true
python3_command: /usr/bin/python3
python3_virtualenv: /usr/bin/virtualenv-3.6
python3_packages:
  - python36
  - python36-libs
  - python36-pip
  - python36-virtualenv
  - libselinux-python3
python3_packages_optional:
  - gcc
  - python36-devel
  - glibc-devel
  - openssl-devel
  - libffi-devel

# Python from source
python3_packages_src:
  - '@Development Tools'
  - gcc
  - openssl-devel
  - bzip2-devel
  - libffi-devel
  - xz-devel

# Python 3.8
python38: false

# Python 3.9
python39: false
</pre></code>

### defaults/family-RedHat-8.yml
<pre><code>
# Python2
python2: false
python2_command: /usr/bin/python2
python2_virtualenv: /usr/bin/virtualenv-2.7
python2_packages:
  - python
  - python-libs
  - python-pip
  - python-virtualenv
  - libselinux-python
python2_packages_optional:
  - gcc
  - glibc-devel
  - python-devel
  - openssl-devel
  - libffi-devel

# Python3
python3: true
python3_command: /usr/bin/python3
python3_virtualenv: /usr/bin/virtualenv-3.6
python3_packages:
  - python36
  - python3-libs
  - python3-pip
  - python3-virtualenv
  - python3-setuptools
  - libselinux-python3
python3_packages_optional:
  - gcc
  - python36-devel
  - glibc-devel
  - openssl-devel
  - libffi-devel

# Python 3.8
python38: true
python38_command: /usr/bin/python3.8
python38_virtualenv: /usr/bin/virtualenv
python38_packages:
  - python38
  - python38-libs
  - python38-pip
  - python3-virtualenv
python38_packages_optional:
  - python38-devel

# Python 3.9
python39: false
python39_command: /usr/bin/python3.9
python39_virtualenv: /usr/bin/virtualenv
python39_packages:
  - python39
  - python39-libs
  - python39-pip
  - python3-virtualenv
python39_packages_optional:
  - python39-devel

# Python 3.11
python311: false
python311_command: /usr/bin/python3.11
python311_virtualenv: /usr/bin/virtualenv
python311_packages:
  - python3.11
  - python3.11-libs
  - python3.11-pip
  - python3.11-setuptools
  - python3-virtualenv
python311_packages_optional:
  - python3.11-devel

# Python from source
python3_packages_src:
  - '@Development Tools'
  - gcc
  - openssl-devel
  - bzip2-devel
  - libffi-devel
  - xz-devel
</pre></code>

### defaults/family-Suse.yml
<pre><code>
# Python2
python2: false
python2_command: /usr/bin/python2
python2_virtualenv: /usr/bin/virtualenv-2.7
python2_packages:
  - python
  - python-libs
  - python-pip
  - python-virtualenv
  - libselinux-python
python2_packages_optional:
  - gcc
  - glibc-devel
  - python-devel
  - openssl-devel
  - libffi-devel

# Python3
python3: true
python3_command: /usr/bin/python3
python3_virtualenv: /usr/bin/virtualenv
python3_packages:
  - python3
  - python3-base
  - python3-setuptools
  - python3-pip
  - python3-virtualenv
  - python3-devel

python3_packages_optional:
  - gcc
  - python3-devel
  - glibc-devel
  - openssl-devel
  - libffi-devel

# Python from source
python3_packages_src:
  - '@Development Tools'
  - gcc
  - openssl-devel
  - bzip2-devel
  - libffi-devel
  - xz-devel

# Python 3.8
python38: false

# Python 3.9
python39: false
python39_command: /usr/bin/python3.9
python39_virtualenv: /usr/bin/virtualenv
python39_packages:
  - python39
  - python39-pip
  - python3-virtualenv
python39_packages_optional:
  - python39-devel

# Python 3.10
python310: false
python310_command: /usr/bin/python3.10
python310_virtualenv: /usr/bin/virtualenv
python310_packages:
  - python310
  - python310-pip
  - python310-setuptools
  - python3-virtualenv
python310_packages_optional:
  - python310-devel

# Python 3.11
python311: false
python311_command: /usr/bin/python3.11
python311_virtualenv: /usr/bin/virtualenv
python311_packages:
  - python311
  - python311-pip
  - python311-setuptools
  - python3-virtualenv
python311_packages_optional:
  - python311-devel
</pre></code>

### defaults/family-RedHat-9.yml
<pre><code>
# Python2
python2: false
python2_command: /usr/bin/python2
python2_virtualenv: /usr/bin/virtualenv-2.7
python2_packages:
  - python
  - python-libs
  - python-pip
  - python-virtualenv
  - libselinux-python
python2_packages_optional:
  - gcc
  - glibc-devel
  - python-devel
  - openssl-devel
  - libffi-devel

# Python3
python3: true
python3_command: /usr/bin/python3
python3_virtualenv: /usr/bin/virtualenv
python3_packages:
  - python3
  - python3-libs
  - python3-pip
  - python3-virtualenv
  - python3-setuptools
  - libselinux-python3
python3_packages_optional:
  - gcc
  - python3-devel
  - glibc-devel
  - openssl-devel
  - libffi-devel

# Python 3.11
python311: false
python311_command: /usr/bin/python3.11
python311_virtualenv: /usr/bin/virtualenv
python311_packages:
  - python3.11
  - python3.11-libs
  - python3.11-pip
  - python3.11-setuptools
  - python3-virtualenv
python311_packages_optional:
  - python3.11-devel
</pre></code>

### defaults/family-Debian.yml
<pre><code>
# Python2
python2: false
python2_command: /usr/bin/python2
python2_virtualenv: /usr/bin/virtualenv
python2_packages:
  - python
  - python-pip
  - python-virtualenv
python2_packages_optional: []

# Python3
python3: true
python3_command: /usr/bin/python3
python3_virtualenv: /usr/bin/virtualenv
python3_packages:
  - python3
  - python3-pip
  - python3-virtualenv
  - python3-venv
  - python3-setuptools
  - virtualenv
  - python3-virtualenv
python3_packages_optional:
  - gcc
  - libffi-dev
  - python3-dev

python3_packages_src:
  - build-essential
  - zlib1g-dev
  - libncurses5-dev
  - libgdbm-dev
  - libnss3-dev
  - libssl-dev
  - libsqlite3-dev
  - libreadline-dev
  - libffi-dev
  - curl
  - libbz2-dev

# Python 3.8
python38: false

# Python 3.9
python39: false
</pre></code>

### defaults/family-Alpine.yml
<pre><code>
# Python2
python2: false
python2_command: /usr/bin/python2
python2_virtualenv: /usr/bin/virtualenv
python2_packages:
  - python2
python2_packages_optional: []

# Python3
python3: true
python3_command: /usr/bin/python3
python3_virtualenv: /usr/bin/virtualenv
python3_packages:
  - python3
  - py3-pip
  - py3-virtualenv
python3_packages_optional:
  - build-base
  - gcc
  - g++
  - libffi-dev
  - musl-dev
  - openssl-dev
  - python3-dev
</pre></code>




## Example Playbook
### molecule/default/converge.yml
<pre><code>
- name: sample playbook for role 'python' pre playbook
  ansible.builtin.import_playbook: converge-pre.yml
  when: molecule_converge_pre is undefined or molecule_converge_pre | bool
- name: sample playbook for role 'python'
  hosts: all
  become: 'yes'
  vars:
    python311: true
    python_package_install_optional: true
    python_virtualenv_root: /tmp/venv
    python_virtualenvs:
      - name: sample
        packages:
          - dnspython
        packages_rm:
          - selinux
        python: /usr/bin/python3
        recreate: false
        site_packages: false
        user: sample
        pip_upgrade: true
  tasks:
    - name: Include role 'python'
      ansible.builtin.include_role:
        name: python
</pre></code>
