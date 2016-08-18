This is a fork of:
https://github.com/joxeankoret/multiav


I'm going to be refractoring this project away from an API and back to a commandline tool. For my uses the Web/API is more bloat than functionality.







MultiAV Scanner Wrapper
=======================

MultiAV Python API. It can scan a file or directory with multiple AV
engines simultaneously. It uses, with the only exception of ClamAV, the
command line AV scanners and extracts the malware names from the output
of the command line tools (for ClamAV it uses the https://code.google.com/p/pyclamd/ extension).

It supports a total of 18 AV engines. The list of currently supported
engines is the following:

   * ClamAV (Ultra-fast, using the daemon)
   * F-Prot (Ultra-fast)
   * Comodo (Fast)
   * BitDefender (Medium)
   * ESET (Slow)
   * Avira (Slow)
   * Sophos (Medium)
   * Avast (Ultra-fast, using the daemon)
   * AVG (Ultra-fast, using the daemon)
   * DrWeb (Slow)
   * McAfee (Very slow, only enabled when running all the engines)
   * Ikarus (Medium, using Wine in Linux/Unix)
   * F-Secure (Fast)
   * Kaspersky (Fast, tested under MacOSX & Linux)
   * Zoner Antivirus (Ultra-fast)
   * MicroWorld-eScan (Fast)
   * Cyren (Ultra-fast)
   * QuickHeal (Fast)

This tool have been tested only under Linux. However, it should work equally
in other Unix based operating systems as well as in Windows as long as the
output from the AV command line utilities maintains the same format.

## Example usages


```python
import pprint
from multiav.core import CMultiAV, AV_SPEED_MEDIUM

multi_av = CMultiAV()
ret = multi_av.scan(path, AV_SPEED_MEDIUM)
pprint.pprint(multi_av)
```




## Moving Forward

The original documentation hasn't been updated in a while, I'll spend some time to rewrite that as well for those looking to use the legacy MultiAV

This project will likey be renamed to avoid confusion with the other project

There will likely be a c# wrapper