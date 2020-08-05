# IPMI

## install
```bash
 yum install ipmitool
```

## 查看所有sensor
```bash
ipmitool -l open sdr
# OR
ipmitool sdr elist
```
### 更詳細的
```bash
ipmitool sensor get <sensor name>
```
## 電源相關
```bash
ipmitool -I lanplus -H 192.168.1.83 -U admin -P password power status
ipmitool -I lanplus -H 192.168.1.83 -U admin -P password power on
ipmitool -I lanplus -H 192.168.1.83 -U admin -P password power soft #soft shotdown
ipmitool -I lanplus -H 192.168.1.83 -U admin -P password power reset
ipmitool -I lanplus -H 192.168.1.83 -U admin -P password chassis power cycle
#power cycle 會在關機後斷電1秒再開機
```
### 強制關機(小心)
```bash
ipmitool -I lanplus -H 192.168.1.83 -U admin -P password power off #force shotdown
```
## 其他
### 下次從哪邊開機
```bash
ipmitool chassis bootdev disk
ipmitool chassis bootdev safe
ipmitool chassis bootdev bios
```

### ID燈
```bash
ipmitool chassis identify <time | 0 | force> #default:15s
```

## reference
http://benjr.tw/11240

###### NEW
