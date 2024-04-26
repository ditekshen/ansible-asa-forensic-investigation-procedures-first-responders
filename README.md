## Ansible Playbook for Cisco ASA Forensic Investigation Procedures for First Responders

Automation for the [Cisco ASA Forensic Investigation Procedures for First Responders](https://sec.cloudapps.cisco.com/security/center/resources/forensic_guides/asa_forensic_investigation.html)

Install the Ansible Cisco ASA collection.

```bash
ansible-galaxy collection install cisco.asa
```

Run the playbook.

```bash
ansible-playbook -i inventory.yml investigate.yml
```

All of the outputs are stored locally per device on the control host.
