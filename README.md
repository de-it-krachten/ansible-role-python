[![semantic-release](https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg)](https://github.com/semantic-release/semantic-release)

# ansible-role-python

Installs python 2 and/or 3 from repository


Platform defaults
--------------

<sub>**platform**</sub> |<sub>**python2**</sub> |<sub>**python3**</sub>
:--- |:--- |:---
<sub>Fedora</sub> |<sub>False</sub> |<sub>True</sub>
<sub>RedHat7</sub> |<sub>True</sub> |<sub>False</sub>


Role Variables
--------------

<sub>**variable**</sub> |<sub>**required**</sub> |<sub>**type**</sub> |<sub>**default**</sub> |<sub>**description**</sub>
:--- |:--- |:--- |:--- |:---
<sub>python_virtualenv_root</sub> |<sub>False</sub> |<sub>string</sub> |<sub>/virtualenv</sub> |<sub>Base directory where to place virtual environments.  All virtual environments will be placed underneath</sub>
<sub>python_package_install</sub> |<sub>False</sub> |<sub>boolean</sub> |<sub>True</sub> |<sub>If the Python OS packes should be installed</sub>
<sub>python2</sub> |<sub>False</sub> |<sub>boolean</sub> |<sub>See vars/{{ ansible_distribution }}.yml</sub> |<sub>If Python2 should be installed</sub>
<sub>python2_command</sub> |<sub>False</sub> |<sub>string</sub> |<sub>See vars/{{ ansible_distribution }}.yml</sub> |<sub>Full path to the python2 executable</sub>
<sub>python2_virtualenv</sub> |<sub>False</sub> |<sub>string</sub> |<sub>See vars/{{ ansible_distribution }}.yml</sub> |<sub>Full path to the python2 virtualenv executable</sub>
<sub>python2_packages</sub> |<sub>False</sub> |<sub>list</sub> |<sub>See vars/{{ ansible_distribution }}.yml</sub> |<sub>List of packages required to install Python</sub>
<sub>python_virtualenv</sub> |<sub>False</sub> |<sub>list</sub> |<sub>[]</sub> |<sub>List of virtual environments to create</sub>
<sub>python3</sub> |<sub>False</sub> |<sub>boolean</sub> |<sub>See vars/{{ ansible_distribution }}.yml</sub> |<sub>If Python3 should be installed</sub>
<sub>python3_command</sub> |<sub>False</sub> |<sub>string</sub> |<sub>See vars/{{ ansible_distribution }}.yml</sub> |<sub>Full path to the python3 executable</sub>
<sub>python3_virtualenv</sub> |<sub>False</sub> |<sub>string</sub> |<sub>See vars/{{ ansible_distribution }}.yml</sub> |<sub>Full path to the python3 virtualenv executable</sub>
<sub>python3_packages</sub> |<sub>False</sub> |<sub>list</sub> |<sub>See vars/{{ ansible_distribution }}.yml</sub> |<sub>List of packages required to install Python</sub>
<sub>python_virtualenv</sub> |<sub>False</sub> |<sub>list</sub> |<sub>[]</sub> |<sub>List of virtual environments to create</sub>
<sub>&nbsp;&nbsp;&nbsp;&nbsp;name</sub> |<sub>True</sub> |<sub>string</sub> |<sub>N/A</sub> |<sub>Name of the virtual environment.</sub>
<sub>&nbsp;&nbsp;&nbsp;&nbsp;path</sub> |<sub>False</sub> |<sub>string</sub> |<sub>{{ python_virtualenv_root }}/python[23]/{{ name }}</sub> |<sub>Full path to the virtual env</sub>
<sub>&nbsp;&nbsp;&nbsp;&nbsp;packages</sub> |<sub>False</sub> |<sub>list</sub> |<sub>[]</sub> |<sub>List of pip packages to install</sub>
<sub>&nbsp;&nbsp;&nbsp;&nbsp;site_packages</sub> |<sub>False</sub> |<sub>boolean</sub> |<sub>False</sub> |<sub>If Python site packages should be made available to the virtualenv</sub>
<sub>&nbsp;&nbsp;&nbsp;&nbsp;pip_upgrade</sub> |<sub>False</sub> |<sub>boolean</sub> |<sub>True</sub> |<sub>Upgrade pip inside virtualenv</sub>
<sub>&nbsp;&nbsp;&nbsp;&nbsp;source</sub> |<sub>False</sub> |<sub>string</sub> |<sub>N/A</sub> |<sub>Name of virtual environment to clone to new</sub>
<sub>&nbsp;&nbsp;&nbsp;&nbsp;label</sub> |<sub>False</sub> |<sub>string</sub> |<sub>N/A</sub> |<sub>symlink to create to point to this virtualenv</sub>
<sub>&nbsp;&nbsp;&nbsp;&nbsp;recreate</sub> |<sub>False</sub> |<sub>boolean</sub> |<sub>False</sub> |<sub>Force virtualenv to be recreated</sub>




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

