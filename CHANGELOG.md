# [unreleased]
### Added
- `python3.11-venv-d4tools` Dockerfile - not containing the pyd4 library
- Instructions on how to build/tag/push the images to our Docker Hub
- python3.12-venv Dockerfile, based on python:3.12-slim-bookworm
### Changed
- Issue templates
- Modified d4tools-based images to use GitHub branch master when cargo installs d4tools 
### Fixed
- Installation step of d4tools in python3.11-venv-pyd4
- "GLIBC_2.x not found" error in d4tools image

# [1.6] 2023-11-14
### Added
- Added a `python3.8-slim-bullseye-bedtools-venv` image

# [1.5] 2023-11-08
### Added
- Added a `python3.11-miniconda` Dockerfile

# [1.4] 2023-09-27
### Added
- Added a `lsynd` Dockerfile
- Added a `python3.11-venv` Dockerfile

# [1.3] 2023-08-11
### Added
- Added a `python3.8-slim-bullseye-venv` Dockerfile

# [1.2] 2023-05-22
### Added
- Added a `d4tools` Dockerfile
- Added a `python3.8-venv-pyd4` Dockerfile
- Added a `python3.11-venv-pyd4` Dockerfile

# [1.1] 2022-02-01
- Added a `python3.8-slim-bedtools-venv` Dockerfile

# [1.0.1] 2022-02-01
### Fixed
- Unfreeze cyvcf2 versions

# [1.0.0] -
### Added
- Added a Dockefile for the `python3.8-cyvcf2-venv` image
- Added a Dockefile for the `python3.7.3-slim-stretch-cyvcf2-venv` image
- Added a Dockerfile for the `python3.8-venv` image
