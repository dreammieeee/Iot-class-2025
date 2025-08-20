# Exploring MQTT QoS Levels

Experiment with QoS 0, 1, and 2.
Observe how message delivery changes based on QoS settings.

## Publisher_qos.py output

```
[16:04:29] DEBUG | Sending CONNECT (u0, p0, wr0, wq0, wf0, c1, k60) client_id=b''
Enter message to publish: [16:04:29] DEBUG | Received CONNACK (0, 0)
dream
Enter QoS level (0, 1, 2): 2
[16:04:44] DEBUG | Sending PUBLISH (d0, q2, r0, m1), 'b'test/qos/6510301003/temperature'', ... (5 bytes)
[16:04:44] PUBLISH REQUESTED | QoS=2 | Message='dream' | msgid=1
Enter message to publish: [16:04:44] DEBUG | Received PUBREC (Mid: 1)
[16:04:44] DEBUG | Sending PUBREL (Mid: 1)
[16:04:44] DEBUG | Received PUBCOMP (Mid: 1)
[16:04:44] PUBLISHED | msgid=1
```

## Subscriber_qos.py Output

```
[15:45:22] DEBUG | Sending CONNECT (u0, p0, wr0, wq0, wf0, c1, k60) client_id=b''
Enter message to publish: [15:45:22] DEBUG | Received CONNACK (0, 0)
dream
Enter QoS level (0, 1, 2): 2
[15:45:34] DEBUG | Sending PUBLISH (d0, q2, r0, m1), 'b'test/qos/6510301003/temperature'', ... (5 bytes)
[15:45:34] PUBLISH REQUESTED | QoS=2 | Message='dream' | msgid=1
Enter message to publish: [15:45:34] DEBUG | Received PUBREC (Mid: 1)
[15:45:34] DEBUG | Sending PUBREL (Mid: 1)
[15:45:34] DEBUG | Received PUBCOMP (Mid: 1)
[15:45:34] PUBLISHED | msgid=1
```