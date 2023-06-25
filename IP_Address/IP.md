# IP Address [IP - Internal Protocol Address]

### What is IP Address?
*  An IP address, which stands for Internet Protocol address, is a unique numerical label assigned to each device connected to a computer network. It serves as an identifier for that device and enables communication between devices within a network or across different networks using the Internet Protocol (IP).

* * Protocol - Refers to a set of rules and guidelines that govern the communication and interaction between devices. It establishes the standards and procedures for data exchange, ensuring that devices can understand and interpret the information they receive.

### IP Address Types
  1. IPv4 - Internet Protocol Version 4
  2. IPv6 - Internet Protocol Version 6


### IPv4 - Internet Protocol Version 4

* IPv4 or Internet Protocol version 4, is a widely used protocol for assigning unique IP addresses to devices connected to a network.
* It is the fourth version of the Internet Protocol and has been the dominant IP version for many years.
* IPv4 addresses are assigned to devices dynamically or statically by an Internet Service Provider (ISP) or a network administrator. 
* IPv4 addresses are 32-bit numbers written in dotted-decimal notation, consisting of four sets of numbers ranging from 0 to 255.
* For example an IPv4 address could be represented as "192.168.0.1".
  
```
    192    .    168    .    0    .    1
     ↓           ↓          ↓         ↓
  [0-255]     [0-255]    [0-255]   [0-255]
     ↓           ↓          ↓         ↓
  8 bits      8 bits     8 bits    8 bits      => 32 bits
 ```
* where 8 bits,

```
  00000000 represents 0
  11111111 represents 255
```

* Each set of numbers known as an octet represents 8 bits of the address.
* IPv4 allows for approximately 4.3 billion unique IP addresses. [2^32] ip will be generated


 
### IPv6 - Internet Protocol Version 6

* IPv6, or Internet Protocol version 6, is a network protocol that succeeds IPv4 and provides a significantly larger address space to accommodate the growing number of devices connected to the internet.
* IPv6 addresses are 128-bit numbers, written in hexadecimal notation, and are represented as eight groups of four hexadecimal digits separated by colons.
* For example an IPv6 address: 2001:0db8:85a3:0000:0000:8a2e:0370:7334.

```

    2001  :  0db8  :  85a3  :  0000  :  0000  :  8a2e  :  0370  :  7334
      ↓        ↓        ↓        ↓        ↓        ↓        ↓        ↓
   16bits   16bits   16bits   16bits   16bits   16bits   16bits   16bits    => 128 bits

```

* Each set of group represents 16 bits.
* Ipv6 allows approximately 3.4 x 10^38 unique addresses.

### IPv4 Address Classes

* Complete ip address is divided into 5 classes [A-E]
* IP Identified as 2 different parts.
    1. Network Id
    2. Host Id

```
CLASS A
  Network Id   Host Id
      ↓           ↓ 
    8 bits     24 bits  

CLASS B
  Network Id   Host Id
      ↓           ↓ 
   16 bits     16 bits  

CLASS C
  Network Id   Host Id
      ↓           ↓ 
    24 bits     8 bits  

CLASS D
  -> Multicasting Purpose

CLASS E
  -> Research and Experiment Purpose

```


* Range of IPv4 : 0.0.0.0 to 255.255.255.255

### CLASS A

* The first bit of a Class A address is always 0. 
* It allowed for a large number of networks with a large number of hosts per network.

```
    0        Network Id         Host Id
    ↓            ↓                 ↓ 
  1 bit        7 bits           24 bits


  00000000.00000000.00000000.00000000       => 0.0.0.0

                   to
  01111111.11111111.11111111.11111111       => 127.255.255.255

where,
  00000000 represented as 0
  11111111 represented as 1
  01111111 represented as 127 (don't add 0 values)
        0   1   1   1   1   1   1   1
        ↓   ↓   ↓   ↓   ↓   ↓   ↓   ↓
      128  64  32  16   8   4   2   1    [64+32+16+8+4+2+1 = 127] 
```
* The range of Class A addresses is from 0.0.0.0 to 127.255.255.255. 
* Number of Subnet -> 2^7
* Number of Hosts  -> 2^24


### CLASS B

* The first two bits of a Class B address are always 10. 
* Class B addresses were designed for moderate-sized networks.

```
    10        Network Id         Host Id
     ↓            ↓                 ↓ 
   2 bit        14 bits           16 bits


  10000000.00000000.00000000.00000000       => 128.0.0.0

                   to
  10111111.11111111.11111111.11111111       => 191.255.255.255

where,
  00000000 represented as 0
  11111111 represented as 1
  10000000 represented as 128 (don't add 0 values)
        1   0   0   0   0   0   0   0
        ↓   ↓   ↓   ↓   ↓   ↓   ↓   ↓
      128  64  32  16   8   4   2   1    [128] 
  10111111 represented as 191 (don't add 0 values)
        1   0   1   1   1   1   1   1
        ↓   ↓   ↓   ↓   ↓   ↓   ↓   ↓
      128  64  32  16   8   4   2   1    [128+0+32+16+8+4+2+1 = 191] 
```
* The range of Class B addresses is from 128.0.0.0 to 191.255.255.255.
* Number of Subnet -> 2^14
* Number of Hosts  -> 2^16

### CLASS C

* The first three bits of a Class C address are always 110. 
* Class C addresses were intended for small networks.

```
    110        Network Id         Host Id
     ↓            ↓                 ↓ 
   3 bit        21 bits            8 bits


  11000000.00000000.00000000.00000000       => 192.0.0.0

                   to
  11011111.11111111.11111111.11111111       => 223.255.255.255

where,
  00000000 represented as 0
  11111111 represented as 1
  11000000 represented as 192 (don't add 0 values)
        1   1   0   0   0   0   0   0
        ↓   ↓   ↓   ↓   ↓   ↓   ↓   ↓
      128  64  32  16   8   4   2   1    [128+64 = 192] 
  11011111 represented as 223 (don't add 0 values)
        1   1   0   1   1   1   1   1
        ↓   ↓   ↓   ↓   ↓   ↓   ↓   ↓
      128  64  32  16   8   4   2   1    [128+64+0+16+8+4+2+1 = 223] 
```
* The range of Class C addresses is from 192.0.0.0 to 223.255.255.255.
* Number of Subnet -> 2^21
* Number of Hosts  -> 2^8


### CLASS D

* The first four bits of a Class D address are always 1110.  
* Class D addresses are reserved for multicast group addresses and are not used for regular network addressing.

```
    1110        Network Id        
     ↓            ↓               
   4 bit        14 bits          

  11100000.00000000.00000000.00000000       => 224.0.0.0

                   to
  11101111.11111111.11111111.11111111       => 239.255.255.255

where,
  00000000 represented as 0
  11111111 represented as 1
  11100000 represented as 224 (don't add 0 values)
        1   1   1   0   0   0   0   0
        ↓   ↓   ↓   ↓   ↓   ↓   ↓   ↓
      128  64  32  16   8   4   2   1    [128+64+32 = 224] 
  11101111 represented as 239 (don't add 0 values)
        1   1   1   0   1   1   1   1
        ↓   ↓   ↓   ↓   ↓   ↓   ↓   ↓
      128  64  32  16   8   4   2   1    [128+64+32+0+8+4+2+1 = 223] 
```
* The range of Class D addresses is from 224.0.0.0 to 239.255.255.255.

### CLASS E

* The first four bits of a Class E address are always 1111.   
* Class E addresses are reserved for experimental purposes and are not used for regular network addressing. 

```
              1111              
               ↓                           
             4 bit                  

  11110000.00000000.00000000.00000000       => 240.0.0.0

                   to
  11111111.11111111.11111111.11111111       => 255.255.255.255

where,
  00000000 represented as 0
  11111111 represented as 1 [255]
  11110000 represented as 224 (don't add 0 values)
        1   1   1   1   0   0   0   0
        ↓   ↓   ↓   ↓   ↓   ↓   ↓   ↓
      128  64  32  16   8   4   2   1    [128+64+32+16 = 240] 

```
* The range of Class E addresses is from 240.0.0.0 to 255.255.255.255.


### Table View
```
-----------------------------------------------------------------
|    Classes  |    Leading Bits    |     Range of IP Address    |
-----------------------------------------------------------------
|      A      |        0           |          0 - 127           |
|      B      |       1 0          |        128 - 191           |
|      C      |      1 1 0         |        192 - 223           |
|      D      |     1 1 1 0        |        224 - 239           |
|      E      |     1 1 1 1        |        240 - 255           |
----------------------------------------------------------------- 
```

## Private IP Address Range

```
---------------------------------------------------------------
|    Classes  |            Range of IP Address                |
---------------------------------------------------------------
|      A      |         10.0.0.0 - 10.255.255.255             |
|      B      |       172.16.0.0 - 172.31.255.255             |
|      C      |      192.168.0.0 - 192.168.255.255            |
--------------------------------------------------------------- 
```

## Public IP Address Range

```
---------------------------------------------------------------
|    Classes  |            Range of IP Address                |
---------------------------------------------------------------
|             |          1.0.0.0 - 9.255.255.255              |                         |
|      A      |         11.0.0.0 - 126.255.255.255            |
---------------------------------------------------------------                        
|             |        128.0.0.0 - 172.15.255.255             |
|      B      |       172.32.0.0 - 191.255.255.255            |
---------------------------------------------------------------
|             |        192.0.0.0 - 192.167.255.255            |
|      C      |      192.169.0.0 - 223.255.255.255            |
---------------------------------------------------------------
|      D      |        224.0.0.0 - 239.255.255.255            |
---------------------------------------------------------------
|      E      |        240.0.0.0 - 254.255.255.255            |
---------------------------------------------------------------
| Local Host  |        127.0.0.0 - 127.255.255.255            |
---------------------------------------------------------------


```
