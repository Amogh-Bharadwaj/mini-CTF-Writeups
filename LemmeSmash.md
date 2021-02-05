## Problem Description:

After some digging in, I found the source but the flag is censored ;-; . Can you help me? No?
There is a link to a C file and a binary which we need to work on : 

https://aetherprior.github.io/CTF-stash/mini-ctf-crux/Smash/Problem.tar.gz

# Disassembling Binaries

## The C File

On opening the tar file and extracting, we get a 'helloname.c' file and a 'helloname' binary file. 
Let's look at the C file:

```C
if(key == 0xcafebabe)
	{
		printf("<Censored>"); //flag to be censored in sources
    }
```

We're essentially being begged to look at the binary file to get this "censored" flag.

## The Binary

The first thing to do when you're given a binary to crack is to _disassemble_  it. There are a few ways of going about this(a worthy mention is the `objdump` command in Linux).

 I chose a handy and commonly used software named Ghidra which not only disassembles the binary but can also frame C code out of it in its code analyser.

From here on it's just about using the tool properly. 
When we look at the `main` function of the assembly, Ghidra's decompiler gives us what we need:

```C
undefined8 main(void)

{
  char local_16 [10];
  int local_c;
  
  local_c = 3;
  gets(local_16);
  printf("Hello, %s!\n",local_16);
  if (local_c == -0x35014542) {
    printf("%d%s%d\n",0xcf9,"metroid",0xc0);
  }
  return 0;
}
```

Running that `printf` statement at the end gives us our flag: `3321metroid192`.



