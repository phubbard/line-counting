This is an Awk script that I wrote to compute C code metrics. It looks at code and comments via regular expressions and computes

  * Lines of code (non-blank)
  * Number of comments (multiline and single-line accounted for)
  * Raw lines of text
  * Total code
  * Total comments
  * Comment percentage

The last is the most interesting. I'm a comment-zealot so mine tend to run about 24%.

It's old code, but works great and is really quite fast.

Run it like so:
```
 awk -f lc.awk *.c
```

I use a shell script called lc:
```
#!/bin/sh
# Script to call awk line-counting script
# pfh 3/19/02
awk -f ${HOME}/bin/lc.awk $*%      
```

Here's an example, the Linux kernel 2.2.16:
```
----------File---Code---Comments---Raw Lines------------------------------------
         sys.c    716        193        1025
       panic.c     59         21          90
      itimer.c    133         21         173
      printk.c    365        101         487
       ksyms.c    343         49         426
       sched.c   1262        581        2081
        kmod.c    101         56         187
 exec_domain.c     92         20         128
    resource.c    130         42         189
  capability.c    142         40         216
        fork.c    547        126         763
         dma.c     66         39         128
      module.c    767        118        1020
        info.c     22          6          38
     softirq.c     36         26          70
      signal.c    776        177        1099
        acct.c    201        133         363
        time.c    238        166         423
      sysctl.c    997        115        1190
        exit.c    394         95         540
--------------------------------------------------------------------------------
 Total code: 7387
 Total comments: 2125
 Total raw lines: 10636
Comment percentage: 22.340202
```

I had this project self-hosted at http://www.phfactor.net/code/line-counting/ but this is the new home.