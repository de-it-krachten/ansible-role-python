[![semantic-release](https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg)](https://github.com/semantic-release/semantic-release)

# ansible-role-python

Installs python 2 and/or 3 from repository


Platform defaults
--------------

<sub>**platform**</sub> |<sub>**python2**</sub> |<sub>**python3**</sub>
:--- |:--- |:---
<sub>Fedora</sub> |<sub>False</sub> |<sub>True</sub>
<sub>RedHat7</sub> |<sub>True</sub> |<sub>False</sub>
<sub>RedHat8</sub> |<sub>False</sub> |<sub>True</sub>


Role Variables
--------------

<sub>**variable**</sub> |<sub>**required**</sub> |<sub>**type**</sub> |<sub>**default**</sub> |<sub>**description**</sub>
:--- |:--- |:--- |:--- |:---
<sub>python_virtualenv_root<br></sub> |<sub>false<br></sub> |<sub>string<br></sub> |<sub>/virtualenv<br></sub> |<sub>Base directory where to place virtual environments.  All virtual environments will<br>    be placed underneath<br></sub>
<sub>python_package_install<br></sub> |<sub>false<br></sub> |<sub>boolean<br></sub> |<sub>true<br></sub> |<sub>If the Python OS packes should be installed<br></sub>
<sub>python_http_proxy<br></sub> |<sub>false<br></sub> |<sub>string<br></sub> |<sub>N/A<br></sub> |<sub>HTTP proxy to use for HTTP protocol<br></sub>
<sub>python_https_proxy<br></sub> |<sub>false<br></sub> |<sub>string<br></sub> |<sub>N/A<br></sub> |<sub>HTTP proxy to use for HTTPS protocol<br></sub>
<sub>python2<br></sub> |<sub>false<br></sub> |<sub>boolean<br></sub> |<sub>See vars/{{ ansible_distribution }}.yml<br></sub> |<sub>If Python2 should be installed<br></sub>
<sub>python2_command<br></sub> |<sub>false<br></sub> |<sub>string<br></sub> |<sub>See vars/{{ ansible_distribution }}.yml<br></sub> |<sub>Full path to the python2 executable<br></sub>
<sub>python2_virtualenv<br></sub> |<sub>false<br></sub> |<sub>string<br></sub> |<sub>See vars/{{ ansible_distribution }}.yml<br></sub> |<sub>Full path to the python2 virtualenv executable<br></sub>
<sub>python2_packages<br></sub> |<sub>false<br></sub> |<sub>list<br></sub> |<sub>See vars/{{ ansible_distribution }}.yml<br></sub> |<sub>List of packages required to install Python<br></sub>
<sub>python_virtualenv<br></sub> |<sub>false<br></sub> |<sub>list<br></sub> |<sub>[]<br></sub> |<sub>List of virtual environments to create<br></sub>
<sub>python3<br></sub> |<sub>false<br></sub> |<sub>boolean<br></sub> |<sub>See vars/{{ ansible_distribution }}.yml<br></sub> |<sub>If Python3 should be installed<br></sub>
<sub>python3_command<br></sub> |<sub>false<br></sub> |<sub>string<br></sub> |<sub>See vars/{{ ansible_distribution }}.yml<br></sub> |<sub>Full path to the python3 executable<br></sub>
<sub>python3_virtualenv<br></sub> |<sub>false<br></sub> |<sub>string<br></sub> |<sub>See vars/{{ ansible_distribution }}.yml<br></sub> |<sub>Full path to the python3 virtualenv executable<br></sub>
<sub>python3_packages<br></sub> |<sub>false<br></sub> |<sub>list<br></sub> |<sub>See vars/{{ ansible_distribution }}.yml<br></sub> |<sub>List of packages required to install Python<br></sub>
<sub>python_virtualenv<br></sub> |<sub>false<br></sub> |<sub>list<br></sub> |<sub>[]<br></sub> |<sub>List of virtual environments to create<br></sub>
<sub>&nbsp;&nbsp;&nbsp;&nbsp;name<br></sub> |<sub>&nbsp;&nbsp;&nbsp;&nbsp;true<br></sub> |<sub>&nbsp;&nbsp;&nbsp;&nbsp;string<br></sub> |<sub>&nbsp;&nbsp;&nbsp;&nbsp;N/A<br></sub> |<sub>&nbsp;&nbsp;&nbsp;&nbsp;Name of the virtual environment.<br></sub>
<sub>&nbsp;&nbsp;&nbsp;&nbsp;path<br></sub> |<sub>&nbsp;&nbsp;&nbsp;&nbsp;false<br></sub> |<sub>&nbsp;&nbsp;&nbsp;&nbsp;string<br></sub> |<sub>&nbsp;&nbsp;&nbsp;&nbsp;{{ python_virtualenv_root }}/pythonX/{{ name }}<br></sub> |<sub>&nbsp;&nbsp;&nbsp;&nbsp;Full path to the virtual env<br></sub>
<sub>&nbsp;&nbsp;&nbsp;&nbsp;packages<br></sub> |<sub>&nbsp;&nbsp;&nbsp;&nbsp;false<br></sub> |<sub>&nbsp;&nbsp;&nbsp;&nbsp;list<br></sub> |<sub>&nbsp;&nbsp;&nbsp;&nbsp;[]<br></sub> |<sub>&nbsp;&nbsp;&nbsp;&nbsp;List of pip packages to install<br></sub>
<sub>&nbsp;&nbsp;&nbsp;&nbsp;site_packages<br></sub> |<sub>&nbsp;&nbsp;&nbsp;&nbsp;false<br></sub> |<sub>&nbsp;&nbsp;&nbsp;&nbsp;boolean<br></sub> |<sub>&nbsp;&nbsp;&nbsp;&nbsp;false<br></sub> |<sub>&nbsp;&nbsp;&nbsp;&nbsp;If Python site packages should be made available to the virtualenv<br></sub>
<sub>&nbsp;&nbsp;&nbsp;&nbsp;pip_upgrade<br></sub> |<sub>&nbsp;&nbsp;&nbsp;&nbsp;false<br></sub> |<sub>&nbsp;&nbsp;&nbsp;&nbsp;boolean<br></sub> |<sub>&nbsp;&nbsp;&nbsp;&nbsp;true<br></sub> |<sub>&nbsp;&nbsp;&nbsp;&nbsp;Upgrade pip inside virtualenv<br></sub>
<sub>&nbsp;&nbsp;&nbsp;&nbsp;source<br></sub> |<sub>&nbsp;&nbsp;&nbsp;&nbsp;false<br></sub> |<sub>&nbsp;&nbsp;&nbsp;&nbsp;string<br></sub> |<sub>&nbsp;&nbsp;&nbsp;&nbsp;N/A<br></sub> |<sub>&nbsp;&nbsp;&nbsp;&nbsp;Name of virtual environment to clone to new<br></sub>
<sub>&nbsp;&nbsp;&nbsp;&nbsp;label<br></sub> |<sub>&nbsp;&nbsp;&nbsp;&nbsp;false<br></sub> |<sub>&nbsp;&nbsp;&nbsp;&nbsp;string<br></sub> |<sub>&nbsp;&nbsp;&nbsp;&nbsp;N/A<br></sub> |<sub>&nbsp;&nbsp;&nbsp;&nbsp;symlink to create to point to this virtualenv<br></sub>
<sub>&nbsp;&nbsp;&nbsp;&nbsp;recreate<br></sub> |<sub>&nbsp;&nbsp;&nbsp;&nbsp;false<br></sub> |<sub>&nbsp;&nbsp;&nbsp;&nbsp;boolean<br></sub> |<sub>&nbsp;&nbsp;&nbsp;&nbsp;false<br></sub> |<sub>&nbsp;&nbsp;&nbsp;&nbsp;Force virtualenv to be recreated<br></sub>



Example Playbook
----------------

+ Install Python2
+ Install Python3
+ Setup virtualenv 'ansible27' from scratch
+ Setup virtualenv 'ansible28' by cloning it from 'ansible27'


<pre><code>
- hosts: all
  vars:
    python2: true
    python3: true
    python_virtualenv:
      - name: ansible27
        label: ansible_current
        packages:
          - ansible==2.7.15
          - ansible-tower-cli==3.3.6
      - name: ansible28
        source: ansible27
        label: ansible_future
        packages:
          - ansible==2.8.5
          - lxml
  roles:
    - ansible-role-python
</pre></code>

