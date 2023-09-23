## [1.11.2](https://github.com/de-it-krachten/ansible-role-python/compare/v1.11.1...v1.11.2) (2023-09-23)


### Bug Fixes

* Change loop/label for latest ansible ([1d50ae3](https://github.com/de-it-krachten/ansible-role-python/commit/1d50ae30dc71a15c0c632689515ecbc8d77fdef1))
* Python3 now uses 'python3 -m venv' over 'virtualenv' ([44ea3c4](https://github.com/de-it-krachten/ansible-role-python/commit/44ea3c4dcf12c22ed0d4f8e8683921ff20a774ec))

## [1.11.1](https://github.com/de-it-krachten/ansible-role-python/compare/v1.11.0...v1.11.1) (2023-09-08)


### Bug Fixes

* Fix loop label to string ([794ae09](https://github.com/de-it-krachten/ansible-role-python/commit/794ae09f64910ce96dc89ed35be792503c300760))

# [1.11.0](https://github.com/de-it-krachten/ansible-role-python/compare/v1.10.0...v1.11.0) (2023-08-14)


### Features

* Update supported platforms & CI ([5b9049e](https://github.com/de-it-krachten/ansible-role-python/commit/5b9049efd2d63f1e8813bdab8a39c15c6364203b))

# [1.10.0](https://github.com/de-it-krachten/ansible-role-python/compare/v1.9.0...v1.10.0) (2023-07-03)


### Features

* Add support for SLES/OpenSUSE Leap 15 ([00bc2c7](https://github.com/de-it-krachten/ansible-role-python/commit/00bc2c781b60b9fc054604d8868aabc1722b3a97))

# [1.9.0](https://github.com/de-it-krachten/ansible-role-python/compare/v1.8.0...v1.9.0) (2023-06-28)


### Features

* Add support for alternative pip repository configuration ([45f9259](https://github.com/de-it-krachten/ansible-role-python/commit/45f92593bd583d5641bb50e68c69ec8168a28c4a))

# [1.8.0](https://github.com/de-it-krachten/ansible-role-python/compare/v1.7.6...v1.8.0) (2023-05-31)


### Features

* Add support for Python 3.11 on RHEL 8/9 ([e9eed6a](https://github.com/de-it-krachten/ansible-role-python/commit/e9eed6a2cbe95ff492f170107b3a4b1968319dba))

## [1.7.6](https://github.com/de-it-krachten/ansible-role-python/compare/v1.7.5...v1.7.6) (2023-05-01)


### Bug Fixes

* Restrict additional Python 3.8/3.9 to RHEL8 ([69d508a](https://github.com/de-it-krachten/ansible-role-python/commit/69d508a66846c90a860cccd20e57dc261d60b6e7))

## [1.7.5](https://github.com/de-it-krachten/ansible-role-python/compare/v1.7.4...v1.7.5) (2023-04-28)


### Bug Fixes

* Add pyton3-setuptools for Redhat family ([f12d8d9](https://github.com/de-it-krachten/ansible-role-python/commit/f12d8d98ebd227f500f9b6c4804478fefe24ec44))

## [1.7.4](https://github.com/de-it-krachten/ansible-role-python/compare/v1.7.3...v1.7.4) (2023-01-11)


### Bug Fixes

* Fix for variable definition from inventory/group vars ([91ea1d5](https://github.com/de-it-krachten/ansible-role-python/commit/91ea1d56989f3c8d4f7a154600834ceda2d9ad16))

## [1.7.3](https://github.com/de-it-krachten/ansible-role-python/compare/v1.7.2...v1.7.3) (2022-12-21)


### Bug Fixes

* Disable python2 by default on all platforms ([6359627](https://github.com/de-it-krachten/ansible-role-python/commit/63596278a318164cbeab39151eed6efd44d4eb91))

## [1.7.2](https://github.com/de-it-krachten/ansible-role-python/compare/v1.7.1...v1.7.2) (2022-12-21)


### Bug Fixes

* Add method for skipping virtual environment ([6e0c81c](https://github.com/de-it-krachten/ansible-role-python/commit/6e0c81cba0d57915379433a36b5e51a38d58b484))

## [1.7.1](https://github.com/de-it-krachten/ansible-role-python/compare/v1.7.0...v1.7.1) (2022-11-18)


### Bug Fixes

* Add additional package 'musl-dev' for Alpine 3.x ([5bcc0eb](https://github.com/de-it-krachten/ansible-role-python/commit/5bcc0eb53e54558e08ceb71479c9eaa907fb695c))

# [1.7.0](https://github.com/de-it-krachten/ansible-role-python/compare/v1.6.0...v1.7.0) (2022-11-17)


### Features

* Add support for OracleLinux 9 ([ca2c863](https://github.com/de-it-krachten/ansible-role-python/commit/ca2c8636c34e03fd5985ee0f3be4c8aec5f26249))

# [1.6.0](https://github.com/de-it-krachten/ansible-role-python/compare/v1.5.0...v1.6.0) (2022-10-26)


### Features

* Update default settings to new method ([0464899](https://github.com/de-it-krachten/ansible-role-python/commit/046489902a1688103804997862c8839a0a4b72ea))

# [1.5.0](https://github.com/de-it-krachten/ansible-role-python/compare/v1.4.3...v1.5.0) (2022-10-12)


### Features

* Move to FQCN ([96d26a4](https://github.com/de-it-krachten/ansible-role-python/commit/96d26a4a3adc91103828b78a8084d8618486c284))
* Update CI to latest standards ([d482a4c](https://github.com/de-it-krachten/ansible-role-python/commit/d482a4c1d77578b35ad1d9513bfe761a3ddf2b3d))

## [1.4.3](https://github.com/de-it-krachten/ansible-role-python/compare/v1.4.2...v1.4.3) (2022-09-20)


### Bug Fixes

* fallback on default virtualenv command ([4bcfb2f](https://github.com/de-it-krachten/ansible-role-python/commit/4bcfb2f32de02a9f1973e31cb13a231917839b4a))

## [1.4.2](https://github.com/de-it-krachten/ansible-role-python/compare/v1.4.1...v1.4.2) (2022-08-25)


### Bug Fixes

* Add support for Python 3.8/3.9 on Fedora ([7ab1b87](https://github.com/de-it-krachten/ansible-role-python/commit/7ab1b879cbefeeee1d0319a6a06a44e743bc859f))
* Rename '__reset__<var>' into dict 'reset_vars' ([a3da94f](https://github.com/de-it-krachten/ansible-role-python/commit/a3da94f553548e875b60f56d1817c6c6aa787af2))

## [1.4.1](https://github.com/de-it-krachten/ansible-role-python/compare/v1.4.0...v1.4.1) (2022-08-25)


### Bug Fixes

* add missing python 3.9 code ([c240d22](https://github.com/de-it-krachten/ansible-role-python/commit/c240d2257d413914a91f11995443d1210a833170))

# [1.4.0](https://github.com/de-it-krachten/ansible-role-python/compare/v1.3.0...v1.4.0) (2022-07-28)


### Features

* Implement ansible-lint v6 support ([06d30d1](https://github.com/de-it-krachten/ansible-role-python/commit/06d30d1abb878c969a4eb142e6ce054d66cce08d))

# [1.3.0](https://github.com/de-it-krachten/ansible-role-python/compare/v1.2.0...v1.3.0) (2022-07-04)


### Features

* Add support for RHEL9 ([51ad792](https://github.com/de-it-krachten/ansible-role-python/commit/51ad7922b15f5f3e72dca13bce55ff66f7d5ad7b))

# [1.2.0](https://github.com/de-it-krachten/ansible-role-python/compare/v1.1.0...v1.2.0) (2022-06-26)


### Features

* Add support for Fedora 35/36 ([706c01c](https://github.com/de-it-krachten/ansible-role-python/commit/706c01cf56df3cd6af0f3b22724c719d0f0ef08d))
* Add support for Ubuntu 22.04 LTS ([7f19e9b](https://github.com/de-it-krachten/ansible-role-python/commit/7f19e9ba98c861f15a3e872a7a16fcf8b74dd014))

# [1.1.0](https://github.com/de-it-krachten/ansible-role-python/compare/v1.0.2...v1.1.0) (2022-06-03)


### Features

* Add support for Alpine 3.x ([ca6bfcc](https://github.com/de-it-krachten/ansible-role-python/commit/ca6bfcc07b803ee520c8ebdb5511de8b1866ea24))
* Add support for Ubuntu 22.04 LTS ([7483a95](https://github.com/de-it-krachten/ansible-role-python/commit/7483a954689d1531303feba7fb21886e08a7940b))

## [1.0.2](https://github.com/de-it-krachten/ansible-role-python/compare/v1.0.1...v1.0.2) (2022-05-24)


### Bug Fixes

* global pip (site-packages) is no longer updated by default on RedHat ([8daa551](https://github.com/de-it-krachten/ansible-role-python/commit/8daa551a774070db9cea7f4c7fc0557692f58419))

## [1.0.1](https://github.com/de-it-krachten/ansible-role-python/compare/v1.0.0...v1.0.1) (2022-02-06)


### Bug Fixes

* make pip version check work on Debian ([9ee45ac](https://github.com/de-it-krachten/ansible-role-python/commit/9ee45acb30edf8033fdeb5a6129a2a5c574398bd))

# 1.0.0 (2022-01-19)


### Features

* initial release ([ad78d16](https://github.com/de-it-krachten/ansible-role-python/commit/ad78d1637e3198f4643655851c720e0228492ac7))
