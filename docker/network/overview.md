# Network driver
* bridge: The default driver
* host: For standalone containers, remove network isolation between the container and the Docker host, and use the host’s networking directly.
* overlay: Overlay networks connect multiple Docker daemons together. You can also use overlay networks to facilitate communication between a swarm service and a standalone container, or between two standalone containers on different Docker daemons.
* macvlan
* none