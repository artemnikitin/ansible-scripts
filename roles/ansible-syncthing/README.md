# Ansible syncthing

Install and manage a syncthing (http://syncthing.net/) node on Linux.

* download syncthing
* install it in `{{syncthing_home}}/bin/`
* basic configuration
* (optional) manage with supervisor or systemd
* (optional) manage ufw


# Requirements

* supervisor (http://supervisord.org/) or systemd
* ufw


# Role Variables

| Option                       | Description                             | Default           |
| ---------------------------- | --------------------------------------- | ----------------- |
| **syncthing_user**           | The user who runs the syncthing daemon. | `syncthing`
| **syncthing_home**           | Home dir of syncthing.                  | `/home/syncthing`
| **syncthing_address**        | IP:Port for webinterface.               | `0.0.0.0:8080`
| **syncthing_listen**         | IP:Port for remote connections.         | `0.0.0.0:22000`
| **syncthing_localannounce**  | enable/disable localAnnounce.           | `true`
| **syncthing_globalannounce** | enable/disable globaleAnnounce.         | `true`
| **syncthing_upnp**           | enable/disable `upnp`.                  | `true`
| **syncthing_use_ufw**        | Add rule to `ufw`.                      | `true`
| **syncthing_use_systemd**    | Use `systemd` to manage process.        | `false`
| **syncthing_use_supervisor** | Use `supervisor` to manage process.     | `true`


# Example

```yaml
  roles:
    - role: syncthing
      syncthing_user: syncthing
      syncthing_address: 0.0.0.0:8080
      syncthing_listen: 0.0.0.0:22000
      syncthing_home: /home/syncthing
      syncthing_localannounce: true
      syncthing_globalannounce: true
      syncthing_upnp: true
```

# Dependencies

None

# License

Copyright (c) 2014, Alexander Frenzel
All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

1. Redistributions of source code must retain the above copyright notice,
   this list of conditions and the following disclaimer.

2. Redistributions in binary form must reproduce the above copyright notice, 
   this list of conditions and the following disclaimer in the documentation
   and/or other materials provided with the distribution.

3. Neither the name of the copyright holder nor the names of its contributors
   may be used to endorse or promote products derived from this software
   without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND
ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED
WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE
FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR
SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER
CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY,
OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.