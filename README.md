## Ansible Playbook for Cisco ASA Forensic Investigation Procedures for First Responders

Automation for the [Cisco ASA Forensic Investigation Procedures for First Responders](https://sec.cloudapps.cisco.com/security/center/resources/forensic_guides/asa_forensic_investigation.html).
- The ```show tech-support detail``` command errors despite returning results. The task for this command is disabled.
- "ASA Core File Generation" and "ROMMON Settings Check" are not implemented since these are disruptive.
- ~~"Step Four – Verify Digitally Signed Image Authenticity" is also not implemented due to lack of HW / SW capabilities to assess against.~~. This is implemented.
- FTDs have different Forensic Investigation Procedures for First Responders depending on series. These may be automated later.
  1. [Cisco Firepower Threat Defense Forensic Investigation Procedures for First Responders](https://sec.cloudapps.cisco.com/security/center/resources/forensic_guides/ftd_forensic_investigation.html).
  2. [Cisco Firepower 1000 Series Forensic Data Collection Procedures](https://sec.cloudapps.cisco.com/security/center/resources/forensic_guides/firepower1000_forensic_investigation.html).
  3. [Cisco Firepower 2100 Series Forensic Investigation Procedures for First Responders](https://sec.cloudapps.cisco.com/security/center/resources/forensic_guides/firepower2100_forensic_investigation.html).
 
The playbook also automate a forensic memory command ```show memory region | include lina``` that exist in [TALOS's blog](https://blog.talosintelligence.com/arcanedoor-new-espionage-focused-campaign-found-targeting-perimeter-network-devices/) but not in any of the above procedures. Read the blog for the significance of this command.

Install the Ansible Cisco ASA collection.

```bash
ansible-galaxy collection install cisco.asa
```

Run the playbook.

```bash
ansible-playbook -i inventory.yml investigate.yml
```

All of the outputs are stored locally per ```inventory_host``` on the control node.
