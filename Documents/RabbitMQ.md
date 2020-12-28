# RabbitMQ

Official Website: https://www.rabbitmq.com/
Latest release version: RabbitMQ 3.8.9 (28 Sep 2020)

## CLI Tool

Installaton location: C:\Program Files\RabbitMQ Server\rabbitmq_server-3.8.5\sbin

- rabbitmqctl: for service management and general operator tasks
- rabbitmq-diagnostics: for diagnostics and health checking
- rabbitmq-plugins: for plugin management
- rabbitmq-queues: for maintenance on queues, in particular quorum queues.
- rabbitmq-upgrade: for maintenance tasks related to upgrades

They can be found under the installation location, named like 'rabbitmqctl.bat'.

Additionally, 
- rabbitmqadmin: for operator tasks over HTTP API. Requires HTTP API port is open for outside connections.
- rabbitmq-collect-env: collects relevant cluster and environment information as well as server logs. (for Linux/Unix-like OS)


1. rabbitmqctl
   refer link: https://www.rabbitmq.com/rabbitmqctl.8.html


   | Action | Commands | Explanation |
   | - | - | - |
   | list | list_channels <br/> lìst_connectìons <br/> list_bindings <br/> list_exchanges <br/> list_queues <br/> |conditions: <br/> --vhost *host_name* : filter vhost <br/> |
   | add user | rabbitmqctl add_user --node *node_name* -- *user_name* *user_password*||
   | add vhost | rabbitmqctl add_vhost *vhost_name* | curl -u userename:pa$sw0rD -X PUT http://rabbitmq.local:15672/api/vhosts/vh1 |
   | delete vhost | rabbitmqctl delete_vhost *vhost_name* | curl -u userename:pa$sw0rD -X DELETE http://rabbitmq.local:15672/api/vhosts/vh1||
   | set limits | connection limits: rabbitmqctl set_vhost_limits -p *vhost_name* '{"max-connections": 256}'<br/>queue limits: rabbitmqctl set_vhost_limits -p *vhost_name* '{"max-queues": 1024}'| set to 0 means disable the collections<br/>set to -1 to lift the limit<br/>|

   



2. rabbitmqadmin
   This tool requires Python 2.79 or a more recent version. Download URL: http://localhost:15672/cli/rabbitmqadmin
   
   Execute commands as below:

   `C:\Program Files\RabbitMQ Server\rabbitmq_server-3.8.5> py rabbitmqadmin list queues`


3. rabbitmq bat files
   `rabbitmq-diagnostics environment`
   `rabbitmq-service stop/remove/install/start`: re-install rabbitmq services to make rabbitmq configuration changes (rabbitmq-env-conf.bat) to be applied.




## Configuration

RabbitMQ default configuration file location:<br/>
%APPDATA%\RabbitMQ\rabbitmq.config<br/>
C:\Users\matt\AppData\Roaming\RabbitMQ<br/>



# MassTransit RabbitMQ

rabbitmqctl list_channels [channelinfoitem ...] -> return current channel information
rabbìtmqctl lìst_connectìons [connectìonìnfoìtem ...]
rabbitmqctl list_bindings [-p vhost] [bindinginfoitem ...]
rabbitmqctl list_exchanges [-p vhost] [exchangeinfoitem ...]
rabbitmqctl list_queues [-p vhost] [queueinfoitem ...]