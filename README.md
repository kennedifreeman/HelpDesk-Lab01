# HelpDesk-Lab01
# Help Desk Ticket HD-002: Internal Website Unavailable

## 1. Incident Summary

**Status:** Resolved (simulated outcome)  
**Category:** Network / DNS  
**Priority:** Normal  
**Environment:** Simulated corporate environment

**User report:** The employee could connect to Wi-Fi and access public websites but could not access the company's internal website.

**Affected resource:** `intranet.company.local`

## 2. Initial Assessment

The issue appeared isolated to the internal website because public websites were accessible. Additional investigation was required to determine whether the cause involved DNS resolution, network configuration, or access to internal services.

## 3. Troubleshooting Performed

### Test 1: Public IP Connectivity

**Command:** `ping -c 4 8.8.8.8`

**Result:** Four replies received, with response times ranging from 6.846 ms to 11.517 ms.

**Finding:** The personal Mac used for practice could reach the tested public IP address.

### Test 2: Public DNS Resolution

**Command:** `nslookup example.com`

**Result:** Two IPv4 addresses were returned.

**Finding:** The configured DNS server successfully resolved the public hostname.

### Test 3: Internal Hostname Resolution

**Command:** `nslookup intranet.company.local`

**Result:** `NXDOMAIN`

**Finding:** The DNS server queried could not find the simulated internal hostname.

**Limitation:** This test was performed from a personal Mac outside the fictional company network. The result does not establish the cause of the simulated employee's issue.

### Test 4: DNS Configuration Review

**Command:** `scutil --dns | grep 'nameserver\[[0-9]*\]'`

**Result:** The Mac displayed IPv6 and IPv4 DNS server addresses.

**Finding:** DNS servers were configured on the personal Mac. This did not establish whether a corporate DNS server was available.

## 4. Root Cause Investigation

In the simulated scenario, comparison with a working coworker's computer revealed that the affected employee was using a different DNS server from the organization's approved internal DNS configuration.

**Simulated root cause:** Incorrect DNS configuration prevented the employee from resolving the internal website hostname.

## 5. Resolution

The technician restored the organization's approved DNS configuration according to company procedures.

## 6. Verification

In the simulated scenario:<br>

- The internal hostname resolved successfully.<br>
- The employee opened the intranet website.<br>
- The employee confirmed that access was restored.<br>

**Final status:** Resolved in the simulation.<br>

**Actual verification note:** The resolution was not performed on a real corporate computer. The diagnosis and successful outcome are simulated for training purposes.

<b>Skills Demonstrated</b>

1. DNS troubleshooting and hostname resolution<br>
2. Basic network connectivity testing<br>
3. macOS command-line utilities<br>
4. Evidence-based problem isolation<br>
5. Comparing working and affected configurations<br>
6. Incident documentation and resolution verification<br>

<b>Lessons Learned</b>

Public internet access does not guarantee access to internal company resources. Technicians should gather information, test the affected hostname, compare working and affected configurations, make only evidence-based changes, and verify the resolution before closing a ticket.
