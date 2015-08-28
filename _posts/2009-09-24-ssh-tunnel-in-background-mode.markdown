---
layout: post
title: SSH tunnel in background-mode
categories:
- quickFAQ
tags:
- Hacks
- ssh
- tunnel
- security
---
Hey guys!


Here the trick to use an invisible ssh-tunnel in background-mode:


<blockquote>#user should use a key...

</blockquote>
<blockquote>ssh -f -N -L &lt;local-port&gt;:&lt;remote-local-ip&gt;:&lt;remote-port&gt; &lt;user&gt;@&lt;dest&gt;

</blockquote>
-f =&gt; background


-N =&gt; don't exec a command (no prompt)


