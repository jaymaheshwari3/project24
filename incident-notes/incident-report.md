
# Project 24: Manual Chaos Test

## 1. Incident Summary
A controlled failure was simulated by manually stopping the Nginx web server on Ubuntu Linux.

## 2. Environment
- Operating System: Ubuntu Linux
- Service: Nginx
- Testing Tool: systemctl
- Verification Tool: curl

## 3. Initial Healthy State
- Nginx status: active (running)
- HTTP response: 200 OK
- Local website was accessible.

## 4. Failure Simulation
Command:
`sudo systemctl stop nginx`

Observations:
- Service status changed to inactive.
- HTTP request failed.
- Connection to localhost port 80 was refused.

## 5. Recovery Procedure
Command:
`sudo systemctl start nginx`

Observations:
- Nginx started successfully.
- Service status returned to active (running).
- HTTP response returned to 200 OK.

## 6. Log Verification
Command:
`sudo journalctl -u nginx -n 15 --no-pager`

The logs recorded the stopping and subsequent starting of the Nginx service.

## 7. Final Result
The Nginx service recovered successfully after the simulated failure.

## 8. Conclusion
This exercise demonstrated manual service failure simulation, troubleshooting, recovery, and verification using Linux system administration commands.
