# Network-Troubleshooting-for-Google-DNS-Resolution

# Network Troubleshooting for Google DNS Resolution

## Objective
- To ensure that Google services are reachable and working as expected.

## Steps Taken

### 1. DNS Resolution Check
Command: `dig google.com`
- **Reason**: To verify the DNS resolution of google.com.
- **Findings**: Multiple IPs are returned, confirming DNS is working fine.

### 2. Network Reachability Check
Command: `ping -c 4 google.com`
- **Reason**: To ensure that the network can reach Google's servers.
- **Findings**: Network latency is low, with an average response time of 12-15 ms.

### 3. Webserver Interaction Check
Command: `curl -I google.com`
- **Reason**: To check the status of the webserver hosting google.com.
- **Findings**: HTTP status 301 (Moved Permanently), redirecting to the www.google.com domain.

### 4. Logs/Service Check
Command: `systemctl status https://www.google.com/`
- **Reason**: To check the service status.
- **Findings**: As expected, Google is not a local system service, so this command is not applicable.

### 5. Hops Check (Traceroute)
Command: `traceroute google.com`
- **Reason**: To trace the route from the local machine to Google's servers.
- **Findings**: Path is routed through multiple hops with varied latencies, which is typical for large networks like Google's.

## Conclusion
Everything is working as expected except for the logs/service check (as expected for an external service).
