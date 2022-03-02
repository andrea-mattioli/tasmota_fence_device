# Tasmota fence device

[1] Connect a sonoff with tasmota firmware to the server's power supply.

[2] Test Fence
```
[root@node1 sbin]# fence_tasmota -a 192.168.1.186:80 -o on -l admin -p admin
Success: Already ON
[root@node1 sbin]# fence_tasmota -a 192.168.1.186:80 -o status -l admin -p admin
Status: ON
[root@node1 sbin]# fence_tasmota -a 192.168.1.186:80 -o off -l admin -p admin
Success: Already OFF
[root@node1 sbin]# fence_tasmota -a 192.168.1.186:80 -o status -l admin -p admin
Status: OFF
[root@node1 sbin]# fence_tasmota -a 192.168.1.186:80 -o reboot -l admin -p admin
Success: Rebooted
```

[3] Add custom fence to Ovirt/RHV
```
[root@rhv-m ~]# engine-config -s CustomVdsFenceType="tasmota"
Picked up JAVA_TOOL_OPTIONS: -Dcom.redhat.fips=false
[root@rhv-m ~]# engine-config -s CustomVdsFenceOptionMapping="tasmota:port=ipport"
Picked up JAVA_TOOL_OPTIONS: -Dcom.redhat.fips=false
[root@rhv-m ~]# systemctl restart ovirt-engine.service
```

[4] Configure

![image](https://user-images.githubusercontent.com/5707570/156444582-f3ba2141-a109-456b-8b93-6d3c5fb7065b.png)
