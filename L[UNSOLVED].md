## Problem Description:

You,Yagami Light posses paramount tool for the liberation of humanity from all evil-'The Death Note'.But the Japanese Police along with the proclaimed detective 'L' consider you a psycopath and would go to every extent to wash away your doings.For this ,they have even collaborated with the FBI to spy on people so that they can find the notorious killer 'Kira'.You know that being a suspect,you are also being spied on.To remove the FBI agent you need to write his name in the 'Death Note'.Luckily you know where all the information about the FBI Agents is stored.So can you the audacious 'Kira',the saviour of humanity hack thier Portal to fulfill your noble deeds?

https://skiddie.pythonanywhere.com/web5/

# Attempt:

We're given a login page.
The source code seems fairly innocent with no script tags anywhere. Tampering with the `admin_access` cookie also did not fetch any results. The session storage is empty.

On top of all this, the site disallows you to enter special signs like `=`  and `*` in their textfields so any form of injection of XSS attack isn't possible.
This problem is unsolved.