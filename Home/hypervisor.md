#### Hypervisor:  ESXI 6.7

Installed onto a pair of 16GB SandDisk Cruzer USB's in RAID 1 (it works, and I don't care enough to modify it)


#### Why ESXI?

ESXI is a rather simple and easy to use hypervisor that is an industry standard and also looks good on a resume.  My alternative that I'd also look into were Xen and SmartOS. Xen was neat but really didn't offer many improvements besides the 8 logical CPU count on the ESXI free license.  SmartOS was an extremely powerful contender with a ton of great capabilities like native docker containers running on bare metal and stupid powerful templating abilities via yaml configuration files.  However, it's far too complex to be used as a home/hobby hypervisor IMO.  It wasn't worth the time to put into it.

#### Host specs:
Chassis: R710
CPU: 2x Xeon 5660 @ 2.8 GHz
Logical Core Count: 24
Total GHz available: 33.5 GHz
RAM: 144 GB
NICs:
  1x Native IPMI IDrac
  1x Native 1GB controller (4 port)
  1x PCIe 1GB Network Controller (2 port)
  1x PCIe QLogic 8GB Fiber Controller (2 port)
Storage:
  type: 8x 2.5" SCSI hot swap bays on backplane
  6x 1TB WD White HDDs (RAID 6)
  2x 120GB ADATA SP 550's (RAID 1)
  1x NFS Share: Lacustrine (The ever expanding money dumpster fire) TODO: add link once I make the page
