# Exploring MQTT QoS Levels

Experiment with QoS 0, 1, and 2.
Observe how message delivery changes based on QoS settings.

## Publisher_qos.py output

```
[16:52:55] DEBUG | Sending CONNECT (u0, p0, wr0, wq0, wf0, c1, k60) client_id=b''
Enter message to publish: [16:52:55] DEBUG | Received CONNACK (0, 0)
dream
Enter QoS level (0, 1, 2): 2
[16:53:06] DEBUG | Sending PUBLISH (d0, q2, r0, m1), 'b'test/qos/6510301003/temperature'', ... (5 bytes)
[16:53:06] PUBLISH REQUESTED | QoS=2 | Message='dream' | msgid=1
Enter message to publish: [16:53:06] DEBUG | Received PUBREC (Mid: 1)
[16:53:06] DEBUG | Sending PUBREL (Mid: 1)
[16:53:06] DEBUG | Received PUBCOMP (Mid: 1)
[16:53:06] PUBLISHED | msgid=1
[16:53:56] DEBUG | Sending PINGREQ
[16:53:56] DEBUG | Received PINGRESP
```

## Subscriber_qos.py Output

```
[16:52:46] DEBUG | Sending CONNECT (u0, p0, wr0, wq0, wf0, c1, k60) client_id=b''
[16:52:46] DEBUG | Received CONNACK (0, 0)
[16:52:46] Connected with result code 0
[16:52:46] DEBUG | Sending SUBSCRIBE (d0, m1) [(b'test/qos/6510301003/#', 2)]
[16:52:46] DEBUG | Received SUBACK
[16:53:06] DEBUG | Received PUBLISH (d0, q2, r0, m1), 'test/qos/6510301003/temperature', ...  (5 bytes)
[16:53:06] DEBUG | Sending PUBREC (Mid: 1)
[16:53:06] DEBUG | Received PUBREL (Mid: 1)
[16:53:06] RECEIVED | QoS=2 | Topic=test/qos/6510301003/temperature | Message=dream | msgid=1
[16:53:06] DEBUG | Sending PUBCOMP (Mid: 1)
```