# Task 1. The NS IP address for Google, Facebook and Tesla are:
| Company Name | IP-Address     |
|--------------|----------------|
| Google	     | 216.58.223.206 |
| Facebook	   | 102.132.101.35 |
| Telsa	       | 199.66.11.0/24 |


# Task 2, Breakdown the following RFC 1918 IPv4 address range into exactly 4 subnets with no address left over.” 
* 10.10.10.0 
* 192.168.0.0 
*	172.168.1.0

# Solution
* (a). Original Network ID: 10.10.10.0 (Class A).
The Default Subnet Mask for this IP address is **255.0.0.0**
However, in order to create 4 Subnets we would need to borrow more bits from the host ID. 
Thus the new Subnet Mask would be **255.255.255.192**
###### Table 1: Subnetting Table.
| Subnet	     | 1	  | 2	 |   **4**  | 8   |	16	| 32	| 64	| 128	 | 256  |
|--------------|------|----|----------|-----|-----|-----|-----|------|------|
|   Host	     | 256	|128 | **64**   | 32	| 16	| 8	  | 4	  |  2	 |  1   |
| Subnet Mask  |	/24	| /25|	**/26** |/27	| /28	| /29	|/30	| /31	 | /32  |

From the subnetting table above, the needed column is column 3. **4 means 4 subnets**, **64 means each subnet** (i.e new subnet) will have 64 total host IDs including network ID and broadcast ID.
Finally, **/26** is the new subnet mask for these 4 subnets.
Now let list all these 4 subnets information in a table.

###### Table 2: The 4 New Subnet Information.
| Network ID   |	Subnet Mask	|   Host ID Range	          |Number of Usable Host	 |Broadcast ID   |
|--------------|--------------|---------------------------|----------------------- |---------------|
|10.10.10.0	   |   /26	      | 10.10.10.1-10.10.10.62    |	         62	           |  10.10.10.63  |
|10.10.10.64   |   /26	      | 10.10.10.65-10.10.10.126	|          62	           |  10.10.10.127 |
|10.10.10.128  |   /26	      |10.10.10.129-10.10.10.190	|          62	           |  10.10.10.191 |
10.10.10.192	 |   /26	      |10.10.10.193-10.10.10.254	|          62	           |  10.10.10.255 |

From table two above, the number of usable host is computed by excluding the Network ID and Broadcast ID from the 64 total Host IDs (64 -2 = 62).
###### (b). Original Network ID: 192.168.0.0 (Class C)
The Default subnet mask for this IP address is **255.255.255.0**
In creating 4 subnets the new subnet mask would be **255.255.192.192**
Note: To avoid repetitions, we would be making reference to table 1 above to solve this problem.

###### Table 3: The 4 New Subnet Information.
| Network ID	      |  Subnet Mask  |	       Host ID Range	            | Number of Usable Host	    | Broadcast ID     |
|-------------------|---------------|-----------------------------------|---------------------------|------------------|
| 192.168.0.0	      |   /26	        | 192.168.1.1-192.168.62.62	        |        62	                | 192.168.63.63    |
| 192.168.64.64	    |  /26	        | 192.168.65.65-192.168.126.126	    |        62	                | 192.168.127.127  |
| 192.168.128.128	  |  /26	        | 192.168.129.129-192.168.190.190	  |        62	                | 192.168.191.191  |
| 192.168.192.192	  |  /26	        | 192.168.193.193-192.168.254.254	  |        62	                | 192.168.255.255  |

###### (C) The Original Network ID: 172.168.1.0 (Class B)
The Default Subnet Mask for this IP address is: **255.255.0.0**
However, by creating 4 Subnets from this IP-address, the new Subnet Mask would be **255.255.255.192**
Note: To avoid repetitions, we would also be making reference to table 1 above.

###### Table 4: The 4 New Subnet Information
|  Network ID	     |   Subnet Mask	  |       Host ID Range	             |  Number of Usable Host	    | Broadcast ID    |
|------------------|------------------|----------------------------------|----------------------------|-----------------|
| 172.168.1.0	     |  /26	            | 172.168.1.1-172.168.1.62	       |    62	                    |  172.168.1.63   |
| 172.168.1.64	   |  /26	            | 172.168.1.65-172.168.1.126	     |    62	                    |  172.168.1.127  |
| 172.168.1.128	   |  /26	            | 172.168.1.129-172.168.1.190	     |    62	                    |  172.168.1.191  |
| 172.168.1.192	   |  /26	            | 172.168.1.193-172.168.1.254	     |    62	                    |  172.168.1.255  |

