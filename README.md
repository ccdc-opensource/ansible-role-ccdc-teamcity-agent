# Ansible Role: Set up TeamCity agent

Install and configure CCDC TeamCity agent

Applying this role will set up the TeamCity agent on the build machine. This will download the package and set up
a service to start it, as well as configure it to connect to a TeamCity server.

## Requirements

None.

## Role Variables

local_buildagent_zip_path: /Users/build/teamcity/buildagent-zip
teamcity_agent_install_dir: string; the installation directory for the TeamCity agent.
teamcity_agent_server_hostname: string; the host name for the TeamCity server to connect to.
teamcity_agent_server_port: int; the port on the TeamCity server to use.
teamcity_agent_hostname: string; the hostname to register the agent on the TeamCity server with.
teamcity_agent_launchd_label: string; (macOS only) the label for the launchd service for the TeamCity agent.
teamcity_agent_launchd_filename: string; (macOS only) the file in which to save the launchd service for the TeamCity agent.
teamcity_agent_java_home_macos: string; (macOS only) the Java home directory to use for the TeamCity agent.

## Dependencies

None.

## Example Playbook

    - hosts: all
      roles:
        - ccdc-cpp-buildmachine-teamcity-agent

## License

MIT / BSD

## Author Information

This role was created in 2020 by Claudio Bantaloukas, based on existing roles at CCDC, by Jeff Geerling and google searches