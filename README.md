# Ansible Role: Set up TeamCity agents

Install and configure a number of TeamCity agents

Applying this role will set up a set of TeamCity agents on the build machine. This will download the package and set up
a service to start it, as well as configure it to connect to a TeamCity server.

## Requirements

- lean_delivery.java: to install java on Windows/Linux
- geerlingguy.homebrew: to install java on MacOS

## Role Variables

- teamcity_server_url: The url that the teamcity server responds to
- teamcity_build_username: Name of the local user that will be running the teamcity agent
- teamcity_build_user_password: Password of the local user that will be running the teamcity agent (only useful on Windows)
- teamcity_downloaded_buildagent_zip: Where to download the buildAgent.zip file that will be unpacked
- teamcity_buildagent_zip_url: Where to download the buildAgent.zip file from
- teamcity_number_of_agents: 4 How many agents to install on a single machine. NOTE: The agents will run under the same username.
- teamcity_agent_java_home_macos: string; (macOS only) the Java home directory to use for the TeamCity agent.

## Dependencies

None.

## Example Playbook

    - hosts: all
      vars:
        homebrew_prefix: '/opt/homebrew'
      roles:
        - ccdc.teamcity_agent

## Example Playbook with specific java version

    - hosts: all
      vars:
        homebrew_prefix: '/opt/homebrew'
        java_version: '18'
      roles:
        - ccdc.teamcity_agent

## License

MIT / BSD

## Author Information

This role was created in 2020 by Claudio Bantaloukas/Florian Piesche, based on existing roles at CCDC, by Jeff Geerling and google searches
