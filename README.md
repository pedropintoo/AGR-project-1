# 3ano/1semestre/AGR/AGR-project-1

# Nota: 20

Pedro Pinto (115304)

Guilherme Santos (113893)

# AGR-project-1

# Network Addressing

## Overview - Public IPv4

This section describes the IPv4 addressing scheme used for the public network and the rationale behind the allocation and subnetting of the address space. The original public IPv4 block assigned for this network is **191.1.1.0/25**. The addressing has been divided to meet the specific requirements of different network segments, while allowing some room for future growth.

### Summary of Subnets

| Subnet             | CIDR Notation    | Range                | Total IPs |
|--------------------|------------------|----------------------|-----------|
| **SITE B**         | 191.1.1.0/27     | 191.1.1.0 - 191.1.1.31 | 32         |
| **ENG**            | 191.1.1.32/28    | 191.1.1.32 - 191.1.1.47 | 16        |
| **DC**             | 191.1.1.48/28    | 191.1.1.48 - 191.1.1.63 | 16        | 
| **DMZ**            | 191.1.1.64/28    | 191.1.1.64 - 191.1.1.79 | 16        |
| **NAT**            | 191.1.1.80/28    | 191.1.1.80 - 191.1.1.95 | 16        |

## Rationale for Subnetting

### 1. **SITE B (191.1.1.0/27)**
   - **Required IPs**: 18
   - **Allocated Subnet**: 191.1.1.0/27 (32 IPs)

### 2. **ENG (191.1.1.32/28)**
   - **Required IPs**: 12
   - **Allocated Subnet**: 191.1.1.32/28 (16 IPs)

### 3. **DC (Data Center) (191.1.1.48/28)**
   - **Required IPs**: 9
   - **Allocated Subnet**: 191.1.1.48/28 (16 IPs)

### 4. **DMZ (Demilitarized Zone) (191.1.1.64/28)**
   - **Required IPs**: 6
   - **Allocated Subnet**: 191.1.1.64/28 (16 IPs)
   - **Rationale**: The DMZ required 6 IP addresses, and although a /29 (8 IPs) would have sufficed, a /28 was chosen to provide more flexibility for future needs. The DMZ hosts public-facing services such as web servers.

### 5. **NAT (Network Address Translation) (191.1.1.80/28)**
   - **Required IPs**: 6
   - **Allocated Subnet**: 191.1.1.80/28 (16 IPs)
   - **Rationale**: The NAT segment required 6 IP addresses, and similar to the DMZ, a /28 subnet was selected to offer flexibility. This segment handles network address translation for internal traffic routing through the public interface.

