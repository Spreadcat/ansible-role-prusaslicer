# Role spreadcat.prusaslicer

A role to install the com.prusa3d.PrusaSlicer flatpack from Github from Prusa Research.

The role supports

- Deployment of additional Filament files
- Automtic login into your Prusa account
- Changing settings of the Prusa Slicer

## Requirements

- Access to the Internet in order download the flatpak package.

## Role Variables

For a detailed description of all supported variables see `./defaults/main.yml`. The file contains all variables and
usaeg examples for each of them.

## Other Variables

The Role uses per default environment variables to determine the right execution parameters.

Unless overwritten, the following environment variables are being used:

- `USER`
- `HOME`

Details on where they are used can be found in `./defaults/main.yml`.

## Dependencies

- None

## Example Playbook

The following playbook will

- Install the latest flatpak `com.prusa3d.PrusaSlicer` from github.com.
- Set the mode in PrusaSlicer to `Export/Advanced`.
- Change the shell command to start the slicer from `PrusaSlicer` (default) to `prusaslicer`).

```yaml
- hosts: localhost
  gather_facts: true
  connection: local
  roles:
    - role: spreadcat.prusaslicer
      prusaslicer_config:
        view_mode: expert
      prusaslicer_shell_command: prusaslicer
```

## License

MIT

## Author Information

This role was created and is maintained by Daniel Buøy-Vehn.
