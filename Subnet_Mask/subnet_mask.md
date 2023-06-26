# SUBNET MASK
* A subnet mask is a 32-bit value used in IP networking to divide an IP address into a network portion and a host portion. It helps determine which part of the IP address represents the network ID and which part represents the host ID.
* The subnet mask is often expressed in the same format as an IP address, with four sets of numbers separated by periods (e.g., 255.255.255.0).
* Each number in the subnet mask represents eight bits and the combination of these bits indicates which bits in the IP address are used for the network and host portions.

* 00000000 represented as 0      
* 11111111 represented as 255     => Total: 256 => 256-2 => 254 hosts
  
```
    1     1     1     1     1     1     1     1
    ↓     ↓     ↓     ↓     ↓     ↓     ↓     ↓
  128    64    32    16     8     4     2     1        => 255
```
* Making Network Bits as 1's & Host Bits as 0's

### CLASS A

* Network Id = 8bits
* Host Id    = 24bits

Conver 0's & 1's

```
   11111111.00000000.00000000.00000000
  |________|__________________________| 
      ↓                  ↓
    8bits             24bits
```

* 255.0.0.0 -> Subnet Mask

### CLASS B

* Network Id = 16bits
* Host Id    = 16bits

Conver 0's & 1's

```
   11111111.11111111.00000000.00000000
  |_________________|_________________| 
          ↓                  ↓
       16bits             16bits
```

* 255.255.0.0 -> Subnet Mask

### CLASS C

* Network Id = 24bits
* Host Id    = 8bits

Conver 0's & 1's

```
   11111111.11111111.11111111.00000000
  |__________________________|________| 
                ↓                ↓
             24bits            8bits
```

* 255.255.255.0 -> Subnet Mask

-----------------------------------------------------------------------------------------------------


 ## Example -1

 Given IP Address - 192.10.15.5

 * IP Address  : 192.10.15.5
 * Subnet Mask : 255.255.255.0


* 192.10.15.5
```
192
      128 64 32 16 8 4 2 1
       ↓   ↓  ↓  ↓ ↓ ↓ ↓ ↓
       1   1  0  0 0 0 0 0

10
      128 64 32 16 8 4 2 1
       ↓   ↓  ↓  ↓ ↓ ↓ ↓ ↓
       0   0  0  0 1 0 1 0

15
      128 64 32 16 8 4 2 1
       ↓   ↓  ↓  ↓ ↓ ↓ ↓ ↓
       0   0  0  0 1 1 1 1

5
      128 64 32 16 8 4 2 1
       ↓   ↓  ↓  ↓ ↓ ↓ ↓ ↓
       0   0  0  0 0 1 0 1

```
* Ip Address  : 192.10.15.5    -> 11000000.00001010.00001111.00000101
* Subnet Mask : 255.255.255.0  -> 11111111.11111111.11111111.00000000

* Lets Do `AND` Operation

```
  11000000.00001010.00001111.00000101
  11111111.11111111.11111111.00000000
  -----------------------------------
  11000000.00001010.00001111.00000000      => 192.10.15.0 
  -----------------------------------
```
* Broadcast => 192.10.15.255
* So, the Ip ranges from 192.10.15.0 - 192.10.15.255 => 254 Hosts

```
-> Network     : 192.10.15.0
-> Broadcast   : 192.10.15.255
-> Netmask     : 255.255.255.0
-> First Ip    : 192.10.15.1
-> Last Ip     : 192.10.15.254
-> Usable Ip's : 254 + 2 (Network, Broadcast)

```

# CIDR Table
* CIDR (Classless Inter-Domain Routing) table that provides the CIDR notation, corresponding subnet mask, and the number of IP addresses available in each CIDR block:

```
| CIDR Notation |   Subnet Mask   | Bits | IP Addresses |
|---------------|-----------------|------|--------------|
|       /32     | 255.255.255.255 |  32  |       1      |
|       /31     | 255.255.255.254 |  31  |       2      |
|       /30     | 255.255.255.252 |  30  |       4      |
|       /29     | 255.255.255.248 |  29  |       8      |
|       /28     | 255.255.255.240 |  28  |      16      |
|       /27     | 255.255.255.224 |  27  |      32      |
|       /26     | 255.255.255.192 |  26  |      64      |
|       /25     | 255.255.255.128 |  25  |     128      |
|       /24     | 255.255.255.0   |  24  |     256      |
|       /23     | 255.255.254.0   |  23  |     512      |
|       /22     | 255.255.252.0   |  22  |    1024      |
|       /21     | 255.255.248.0   |  21  |    2048      |
|       /20     | 255.255.240.0   |  20  |    4096      |
|       /19     | 255.255.224.0   |  19  |    8192      |
|       /18     | 255.255.192.0   |  18  |    16384     |
|       /17     | 255.255.128.0   |  17  |    32768     |
|       /16     | 255.255.0.0     |  16  |    65536     |
|       /15     | 255.254.0.0     |  15  |    131072    |
|       /14     | 255.252.0.0     |  14  |    262144    |
|       /13     | 255.248.0.0     |  13  |    524288    |
|       /12     | 255.240.0.0     |  12  |    1048576   |
|       /11     | 255.224.0.0     |  11  |    2097152   |
|       /10     | 255.192.0.0     |  10  |    4194304   | 
|       /9      | 255.128.0.0     |  9   |    8388608   |
|       /8      | 255.0.0.0       |  8   |    16777216  |
---------------------------------------------------------
```
