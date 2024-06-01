# Ansible Role: ludus_sysmon ([Ludus](https://ludus.cloud))

An Ansible Role that installs [Sysmon](https://learn.microsoft.com/en-us/sysinternals/downloads/sysmon) on Windows hosts and configures it based on [sysmonconfig.xml](https://github.com/olafhartong/sysmon-modular/blob/master/sysmonconfig.xml) provided by [olafhartong/sysmon-modular](https://github.com/olafhartong/sysmon-modular).

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    # This is a comment explaining the variable below
    ludus_sysmon_config_file_url: "https://github.com/olafhartong/sysmon-modular/raw/master/sysmonconfig.xml"

## Dependencies

None.

## Example Playbook

```yaml
- hosts: ludus_sysmon_hosts
  roles:
    - polluxtroy3758.ludus_sysmon
```

## Example Ludus Range Config

```yaml
ludus:
  - vm_name: "{{ range_id }}-ad-dc-win2022-server-x64-1"
    hostname: "{{ range_id }}-DC01-2022"
    template: win2022-server-x64-template
    vlan: 10
    ip_last_octet: 11
    ram_gb: 6
    cpus: 4
    windows:
      sysprep: true
    domain:
      fqdn: ludus.domain
      role: primary-dc
    roles:
      - polluxtroy3758.ludus_sysmon
```

## License

GPLv3

## Author Information

This role was created by [polluxtroy3758](https://github.com/polluxtroy3758), for [Ludus](https://ludus.cloud/).
