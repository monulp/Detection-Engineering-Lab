# Troubleshooting Notes (Phase 2)

## 1) Host-only adapter caused VM abort
**Symptom:** VM session aborted with VERR_INTNET_FLT_IF_NOT_FOUND  
**Cause:** VirtualBox host-only interface missing/broken on Windows host  
**Fix:** Repaired VirtualBox networking / recreated host-only adapter in Host Network Manager

## 2) No internet when using host-only only
**Symptom:** DNS resolution fails / cannot download packages  
**Cause:** Host-only has no outbound route by default  
**Fix:** Added a second NIC using NAT for egress

## 3) Splunk permission errors + port already bound
**Symptom:** local.meta Permission denied, splunkd.pid unreadable, port 8000 already bound  
**Cause:** Incorrect ownership under `/opt/splunk` and stuck splunkd process  
**Fix:** Stopped/killed splunkd as needed, `chown -R splunk:splunk /opt/splunk`, started Splunk as user `splunk`

## 4) Searches blocked due to minimum free disk space
**Symptom:** Splunk refuses searches: minimum free disk threshold reached  
**Cause:** Root filesystem too small (19G)  
**Fix:** Expanded VirtualBox disk to 80G and extended LVM volume + filesystem

## 5) Host-only NIC not persistent after reboot
**Symptom:** Secondary NIC down after reboot  
**Cause:** cloud-init overwriting network config  
**Fix:** Disabled cloud-init networking and managed NICs via netplan
