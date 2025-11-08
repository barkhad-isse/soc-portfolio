# Week 4 — Command History

## Ensure the Wazuh agent is running and communicating with the manager.

sudo systemctl status wazuh-agent


## Make a dedicated directory for generating FIM events and change into it.

sudo mkdir -p /home/kali/fim-test
cd /home/kali/fim-test

## Generate File Events

Create, modify and delete a file to trigger FIM alerts.

## Create a file with initial content
echo "Initial test content" | sudo tee testfile.txt

##  Append additional content
echo "Modified content" | sudo tee -a testfile.txt

## Delete the file
sudo rm testfile.txt

## Check Syscheck (FIM) Logs

Review the agent’s log to ensure that syscheck is monitoring the directory.

sudo cat /var/ossec/logs/ossec.log | grep syscheck

## configuration changes were applied, restart the agent to load the new rules.

sudo systemctl restart wazuh-agent

## Use ausearch to display recent successful audit events (useful for troubleshooting).

sudo ausearch --start recent --success yes | tail -n 20
