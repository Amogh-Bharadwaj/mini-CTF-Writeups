## Problem Description:

Aeeeee. Ben Dover just gotta watch dem dance, with me having dem cash.

https://aetherprior.github.io/CTF-stash/TechWeek2020/s

mirror (check file name and format, can be corrupted):

[https://skiddie.pythonanywhere.com/challenges/s](https://aetherprior.github.io/CTF-stash/TechWeek2020/s)

# Attempt:

We are given a shared-library file. 
Running the `strings` command on it, we get some info such as:

```C
Hello, World!
;*3$"
Sry it's not me
srnchUaWOR[aV
```

This looked a little promising so I tried feeding it into Ghidra's code analyser. 
The decompiler gave some (evidently incorrect) decompiled C code such as:

```C
void FUN_001006ca(void)

{
  int local_c;
  
  local_c = 0;
  while (local_c < 0xd) {
    s_srnchUaWOR[aV_00301028[local_c] = (char)local_c * '\x02' + s_srnchUaWOR[aV_00301028[local_c];
    local_c = local_c + 1;
  }
  puts(s_srnchUaWOR[aV_00301028);
  return;
}
```

Even after playing around with this, I was not fruitful. This problem is unsolved.