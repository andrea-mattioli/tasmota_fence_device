# tasmota_fence_device
fencing device based on tasmota

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
