# Ansible Role: Fonts
[![pre-commit](https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit)](https://github.com/pre-commit/pre-commit)

This role installs and configures fonts on Debian-based Linux systems. It:
 - Ensures that third-party nerd fonts are installed
 - Ensures that fontconfig is configured to use installed fonts
 - Ensures that fontconfig is configured to support emoji ✏️⚙️

See: https://github.com/ryanoasis/nerd-fonts

## Role Variables
See [defaults/main.yml](./defaults/main.yml) for a comprehensive list of role variables.  
Some of the most pertinent variables are:
- `fonts_user`  
- `fonts_xdg_config_home`  
- `fonts_xdg_data_home`  
- `fonts_nerdfont_font_names`

## Dependencies
I recommend using a Python3 virtual environment (venv).  
`python3 -m venv venv`  
`source ./venv/bin/activate`  
`python3 -m pip install -r requirements.txt`

## Testing
Testing is performed using Molecule.  
See the [molecule](./molecule/) directory for more information.

## Linting
Linting is done automatically via [https://pre-commit.com/](https://pre-commit.com/).  
After setting up a virtual environment and installing `requirements.txt`, run  
`pre-commit run --all-files`  
See: https://github.com/ansible/ansible-lint  
See: https://github.com/pre-commit/pre-commit

## Example Playbook
    - hosts: servers
      vars_files:
        - vars/main.yml
      roles:
        - librick.fonts

*Inside `vars/main.yml`*:

    fonts_user: johndoe
    fonts_xdg_config_home: "/home/{{ fonts_user }}/.config"
    fonts_xdg_data_home: "/home/{{ fonts_user }}/.local/share"
    fonts_nerdfont_font_names:
      - "FiraCode"
      - "Hack"
      - "Noto"

## License

MIT Licensed

## Author Information

This role was created in 2023 by [Eric McDonald](https://juniperspring.xyz/).
