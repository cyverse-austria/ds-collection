# branch main of https://github.com/cyverse/ds-collection
only playbook - irods_resource_server.yml is avaliable.

## irods_resource_server.yml
```bash
PLAY [Ensure catalog service providers are started] ****************************
TASK [Gathering Facts] *********************************************************
ok: [latest-ies.cyverse.at]
TASK [Start iRODS] *************************************************************
fatal: [latest-ies.cyverse.at]: FAILED! => {"changed": false, "msg": "b'Traceback (most recent call last):\\n  File \"/var/lib/irods/scripts/irods_control.py\", line 42, in <module>\\n    wrap_if_necessary()\\n  File \"/var/lib/irods/scripts/irods_control.py\", line 21, in wrap_if_necessary\\n    with open(irods.paths.server_config_path()) as server_config_path:\\nFileNotFoundError: [Errno 2] No such file or directory: \\'/etc/irods/server_config.json\\'\\n'"}
```

# Branch DS-476 of https://github.com/cyverse/ds-collection

## irods_catalog_provider.yml

```bash

TASK [Ensure service user type doesn't exist] **********************************
fatal: [latest-ies.cyverse.at]: FAILED! => {"changed": false, "msg": "CAT_NO_ROWS_FOUND: Nothing was found matching your query"}
```

```bash
TASK [cyverse.ds.irods_cfg : Setup iRODS] **************************************
changed: [latest-ies.cyverse.at]
fatal: [latest-res02.cyverse.at]: FAILED! => {"changed": true, "cmd": "set -o errexit\npython3 /var/lib/irods/scripts/setup_irods.py --stdout --test --verbose \\\n  --json_configuration_file=/tmp/setup_configuration.json\nprintf '\\n' >> /var/lib/irods/.irods/irods_environment.json\nrm --force /var/lib/irods/log/test_mode_output.log /tmp/setup_configuration.json || true\n", "delta": "0:01:39.648800", "end": "2025-03-26 10:02:33.455180", "msg": "non-zero return code", "rc": 1, "start": "2025-03-26 10:00:53.806380", "stderr": "\u001b[1;31mError encountered running setup_irods:\nTraceback (most recent call last):\n  File \"/var/lib/irods/scripts/setup_irods.py\", line 523, in main\n    setup_server(irods_config,\n  File \"/var/lib/irods/scripts/setup_irods.py\", line 137, in setup_server\n    IrodsController(irods_config).start(test_mode=test_mode)\n  File \"/var/lib/irods/scripts/irods/controller.py\", line 172, in start\n    six.reraise(IrodsError, e, sys.exc_info()[2])\n  File \"/var/lib/irods/scripts/irods/six.py\", line 672, in reraise\n    raise value\n  File \"/var/lib/irods/scripts/irods/controller.py\", line 164, in start\n    raise IrodsError('iRODS server failed to start.')\nirods.exceptions.IrodsError: iRODS server failed to start.\u001b[0m", "stderr_lines": ["\u001b[1;31mError encountered running setup_irods:", "Traceback (most recent call last):", "  File \"/var/lib/irods/scripts/setup_irods.py\", line 523, in main", "    setup_server(irods_config,", "  File \"/var/lib/irods/scripts/setup_irods.py\", line 137, in setup_server", "    IrodsController(irods_config).start(test_mode=test_mode)", "  File \"/var/lib/irods/scripts/irods/controller.py\", line 172, in start", "    six.reraise(IrodsError, e, sys.exc_info()[2])", "  File \"/var/lib/irods/scripts/irods/six.py\", line 672, in reraise", "    raise value", "  File \"/var/lib/irods/scripts/irods/controller.py\", line 164, in start", "    raise IrodsError('iRODS server failed to start.')", "irods.exceptions.IrodsError: iRODS server failed to start.\u001b[0m"], "stdout": "Updating /var/lib/irods/version.json...\u001b[0m\n\n+--------------------------------+\n| Setting up the service account |\n+--------------------------------+\n\u001b[0m\nExisting Group Detected: irods\u001b[0m\nExisting Account Detected: irods\u001b[0m\nSetting owner of /var/lib/irods to irods:irods\u001b[0m\nSetting owner of /etc/irods to irods:irods\u001b[0m\nUpdating /etc/irods/server_config.json...\u001b[0m\nUpdating /var/lib/irods/.irods/irods_environment.json...\u001b[0m\n\n+-------------------+\n| Starting iRODS... |\n+-------------------+\n\u001b[0m\nValidating [/etc/irods/server_config.json]... Success\u001b[0m\nValidating [/var/lib/irods/version.json]... Success\u001b[0m\nValidating [/var/lib/irods/.irods/irods_environment.json]... Success\u001b[0m\nStarting iRODS server ...\u001b[0m\nFailure\u001b[0m\nExiting...\u001b[0m", "stdout_lines": ["Updating /var/lib/irods/version.json...\u001b[0m", "", "+--------------------------------+", "| Setting up the service account |", "+--------------------------------+", "\u001b[0m", "Existing Group Detected: irods\u001b[0m", "Existing Account Detected: irods\u001b[0m", "Setting owner of /var/lib/irods to irods:irods\u001b[0m", "Setting owner of /etc/irods to irods:irods\u001b[0m", "Updating /etc/irods/server_config.json...\u001b[0m", "Updating /var/lib/irods/.irods/irods_environment.json...\u001b[0m", "", "+-------------------+", "| Starting iRODS... |", "+-------------------+", "\u001b[0m", "Validating [/etc/irods/server_config.json]... Success\u001b[0m", "Validating [/var/lib/irods/version.json]... Success\u001b[0m", "Validating [/var/lib/irods/.irods/irods_environment.json]... Success\u001b[0m", "Starting iRODS server ...\u001b[0m", "Failure\u001b[0m", "Exiting...\u001b[0m"]}

```

## irods_resource_server.yml

```bash
TASK [Ensure clerver user is in group rodsadmin] *******************************
fatal: [latest-res02.cyverse.at -> localhost]: FAILED! => {"changed": false, "message": "", "msg": "Group must already exist", "users": []}
fatal: [latest-res01.cyverse.at -> localhost]: FAILED! => {"changed": false, "message": "", "msg": "Group must already exist", "users": []}

```
