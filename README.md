Role Name
=========

A sinple ansible role to install and configure apache kafka.

Requirements
------------

No special requirements.

Role Variables
--------------
* KAFKA_VERSION: The kafka version to install (default is 1.0.0)
* KAFKA_USER: The user used to run the kafka daemon. (default is kakfa)
* KAFKA_LOG_DIR: The directory used to store kafka logs (default is /tmp/kafka)
* KAFKA_ZOOKEEPER_URL: The url of zookeeper instance to use.
* KAFKA_TOPICS: This is an associative array with the following structure in each element:
    name: <Topic name> This is required and does not have a default value.
    replication_factor: The replication factor used for the topic (default is 1)
    partitions: The number of partitions for the topic (default is 1)

Dependencies
------------

* mohsenSy.java

Example Playbook
----------------

In this playbook we create a topic called test_topic with a replication factor of 3 and 3 partitions.

    - hosts: servers
      vars:
        - KAFKA_TOPICS:
          - name: test_topic
            replication_factor: 3
            partitions: 3
      roles:
         - mohsenSy.kafka

License
-------

BSD

Author Information
------------------

If you have any question please contact me on

[twitter](https://twitter.com/mouhsen_ibrahim)

[linkedin](https://linkedin.com/in/mohsen-ibrahim-670b13112/)

email mohsen47@hotmail.co.uk
