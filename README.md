Apache ActiveMQ
=========
This ansible role install and configure Apache ActiveMQ.

Requirements
------------
[ansiblebit.oracle-java](https://github.com/ansiblebit/oracle-java) (will be autoinstalled)

Role Variables
--------------

```
amq_user: activemq

# Download link. For version higher 5.8.0 http://apache-mirror.rbc.ru/pub/apache/activemq/
amq_download_url: 'http://archive.apache.org/dist/activemq/apache-activemq/5.8.0/apache-activemq-5.8.0-bin.tar.gz'

# name of service for instances. also usage for service control, example:
# 'service [amq_broker_name] start|stop|restart`
amq_broker_name: activemq

# installation directory
amq_install_dir: '/opt/activemq'

# activemq enviroment variables
amq_opts_memory: '-Xms1G -Xmx1G'
amq_conf_dir: '{{ amq_install_dir }}/conf'
amq_data_dir: '{{ amq_install_dir }}/data'
amq_tmp_dir: '{{ amq_install_dir }}/tmp'

# activemq broker config
amq_stomp_transport_connector_uri: 'stomp://0.0.0.0:61612?transport.closeAsync=false'
amq_stomp_and_nio_transport_connector_uri: 'stomp+nio://0.0.0.0:61613?transport.closeAsync=false'

# Use custom broker xml config
amq_custom_xml_config: False
amq_custom_xml_config_path: ''

# jetty settings
amq_webconsole_port: 8161
```

Dependencies
------------
None

Example Playbook
----------------
```
- hosts: all
  roles:
     - role: activemq
```

Author Information
------------------
Разработано и протестировано для Ubuntu 14.04 (trusty)
