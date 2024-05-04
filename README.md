# Simple custom instructions based on tutorials

## Publisher/Subscriber

```bash
colcon build && source install/setup.bash
# [Listener]
ros2 run cpp_pubsub listener
# [Talker]
ros2 run cpp_pubsub talker
```

## Services

```bash
colcon build && source install/setup.bash
# [Server]
ros2 run cpp_srvcli server
# [Client]
ros2 run cpp_srvcli client 2 3 1
```
