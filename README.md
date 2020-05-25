# mumble-server

This role installs and configures a [mumble](https://mumble.info/) server.

## Requirements

Debian.

## Role Variables


| Name| Required/Default | Description |
|-----|:----------------:|-------------|
| `mumble_server.superuser_pw`  | **required** | The superuser password for the mumble server |
| `mumble_server.config` | The same as the configuration shipped with the apt package at the time of writing this role. _see [vars](vars/main.yml) or the exact values_ | The configuration options for the mumble server. See [the wiki](https://wiki.mumble.info/wiki/Murmur.ini) for possible options. This should be a dict containing the key value pairs for the config. |
| `mumble_server.ice_config` | The same as the configuration shipped with the apt package at the time of writing this role. _see [vars](vars/main.yml) or the exact values_ | The options for the special [`[Ice]` section](https://wiki.mumble.info/wiki/Murmur.ini#Ice_Configuration_Section) in the configuration file. This should be a dict containing the key value pairs for the config. |

## Example

```yml
mumble_server:
  superuser_pw: "supersecret"
  config:
    welcometext: '"Welcome!<br />Enjoy!"'
    password: letmein
  ice_config:
    Ice.MessageSizeMax: 2048
```

## License

This work is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-sa/4.0/).

## Author Information

- [Tim Neumann (neumantm)](https://github.com/neumantm) _tim.neumann@stuvus.uni-stuttgart.de_
