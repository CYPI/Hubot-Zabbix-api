# Hubot Zabbix script that let's you:
 - create maintenance period for an host or group of hosts
- acknowledge events

 works with Zabbix 2.4

#configuration

in zabbix.py, add your zabbix server's fqdn:

  api = "https://<<zabbixserver_fqdn>>/api_jsonrpc.php"
  
in secrets.json, add a username and password with api permissions:

{
    "jsonrpc": "2.0",
    "method": "user.login",
    "params": {
        "user": "<username>",
        "password": "<password>"
    },
    "id": 1,
    "auth": null
}


#Commands:

hubot pause me group pao - create a maintenance period of 1 hour for host group PAO

hubot pause me host paoad1 for 6 hours -  create a maintenance period of 6 hours for paoad1 host

hubot unpause me group pao - delete maintenance for group pao

hubot unpause me host paoad1 - delete maintenance for host paoad1

hubot zaback 9376146 pb resolved - Acknowledge eventid 9376146 and add comment: "pb resolved"

