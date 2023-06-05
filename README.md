# aap-meraki-demo-setup

This repository contains the playbooks to configure Ansible Automation Controller or Ansible AWX as demonstrated during the **"Using Ansible to automate edge site infrastructure at scale"** talk delivered in Red Hat's booth during Cisco Live US 2023.

The companion repo that contains the demo playbooks and configuration is available at <https://github.com/wwt/ansible-meraki-demo>.

## Demo Setup

> :warning: The following are the basic settings that need to be changed.  Your environment requirements may vary.

1. Update `controller_configs/controller_auth.yml` with appropriate hostname of your AAP or AWX instance.
2. Update `controller_configs/controller_projects.yml` with the appropriate `scm_url` for your environment.
3. Copy `ENVEXAMPLE` to `.env` and update settings as necessary.
4. Run `ansible-playbook create_token.yml` to authenticate with your AAP or AWX instance and add an OAuth token to .env.
5. Run `source .env` command to load Environment Variables
6. Run `ansible-playbook configure_controller.yml` to push configuration to your AAP or AWX instance.

### Template Surveys

`template_surveys/claim_meraki.json` - Survey to prompt user for information required to execute `claim_devices.yml` playbook.

### Additional Playbooks

`playbooks/delete_token.yml` - Playbook to delete OAuth token from AAP or AWX.

## Contributors

Nick Thompson - <https://github.com/nsthompson>
