# Disaster Recovery Procedure — Quarterly Test

**Objective:** Restore critical VM from LTO tape to production in <15min.

**Steps:**
1. Simulate failure: Power off `sliit-pve` 
2. Insert LTO tape into library
3. PBS: Restore latest backup of `vm-100-opnsense` to `pbs-backup`
4. Migrate VM to `sliit-pve` and start
5. Verify: Ping, DNS, WireGuard tunnel up
6. Record time: Start to service restored

**Last result: 12min on 2026-01-15**

This proves 7/4/3 backup strategy + air-gapped LTO meets <15min RTO SLA.
