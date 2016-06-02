---
layout: page
title: Just a few short notes about some technical stuff
---

# open a SSH port-tunnel in background

```bash
# -f => in background
# -N => don't exec a command (no prompt)
ssh -f -N -L $local_port:$remote_local_ip:$remote_port $user@$dest
```

# Debug 3rd party binaries

```bash
# dumps, which shared libs are used by the executed programm
LD_DEBUG=files ls
```
