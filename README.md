# smbdoor
### :green_circle: Fixed crash/shellcode not executing. see `callbacks.c` for more info.

---

#### "old"  below

# :radioactive: finally Win11 soon done
### `Windows 11 now works; but will need to do further testing`


- idk a bit un-sure ⚠️ note this(pull request) is failing for some reason (??) 
- https://github.com/fengjixuchui/smbdoor/pull/1/files




![ExtraPulsar](extrapulsar.png)

The proof-of-concept smbdoor.sys driver is a silent remote backdoor that does not bind new sockets or perform function modification hooking. Instead it abuses undocumented APIs in srvnet.sys to register itself as a valid SMB handler. It then listens on the already-bound ports 139/445 for special packets in which to execute secondary shellcode. In several ways, it has similarities with DoublePulsar and DarkPulsar, as well as ToxicSerpent.

Of course, it comes with practical limitations that make it mostly an academic exploration, but I thought it might be interesting to share, and is possibly something EDR products should monitor.

### Detection: 
- https://twitter.com/zerosum0x0/status/1117701672237535233
- https://twitter.com/msuiche/status/1117716796658864128
