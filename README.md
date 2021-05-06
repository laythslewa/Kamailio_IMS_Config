# Kamailio_IMS_Config
Fixed version of Kamailio IMS configuration files for basic calling

## Components
- Kamailio (5.3+focal)
- Fraunhofer OpenHSS (r1198) or PyHSS

## Testbed Setup

**For VoLTE setup, make sure to have gNB and (o5gc + IMS) in the same subnet**

### VoLTE test
<pre>
  +---------+        +-------+       +-------+
  |         | <-->   |  IMS  |  <--> |       |
  |  UE1    |        |   +   |       | UE2   |
  |         |        | o5gc  |       |       |
  |         |        |       |       |       |
  +---+-----+        +-------+       +-------+
</pre>

- Kamailio IMS + Open5gcore (O5gc) => Running in a OpenStack VM with internal IP 192.168.178.10 and Floating IP 172.24.15.30 (OpenStack is not mandatory, can run on a physical machine)
- UE1 => Huawei EVR-N29 UE with IMSI 001010000013348
- UE2 => Google Plus UE with IMSI 00101123456792

### VoIP test
<pre>
  +---------+        +-------+       +-------+
  |         | <-->   |  IMS  |  <--> |       |
  |  Alice  |        |       |       | Bob   |
  |         |        |       |       |       |
  |         |        |       |       |       |
  +---+-----+        +-------+       +-------+
</pre>

- Kamailio IMS => Running in a OpenStack VM with internal IP 192.168.178.10 and Floating IP 172.24.15.30 (OpenStack is not mandatory, can run on a physical machine)
- Alice => OnePlus UE SIP client IP (UE maybe behind NAT or otherwise, works in both cases)
- Bob => OnePlus UE SIP client IP (UE maybe behind NAT or otherwise, works in both cases)

## Tested
- Basic VoIP calling with WiFi and LTE
- VoLTE

## Not Tested
- VoWiFi

## Links related to VoIP
- [Learning VoIP, RTP and SIP](https://github.com/onmyway133/blog/issues/284)
