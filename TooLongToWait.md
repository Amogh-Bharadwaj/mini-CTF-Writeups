## Problem Description

You, the Rick from dimension C-137 are suspicious that you will be banned from the citadel of Ricks for your growing anti-Rick activities in the next meeting of the Council of Ricks. Hence you concoct a plan to delete all your criminal records from the supercomputer in the citadel. But, the computer is so secure that it asks you to wait for 10000000 seconds before you can use it. You don't have so much time before your prosecution starts. So can you, 'The Rickest Rick' hack it to to fulfill your evil deeds?

https://skiddie.pythonanywhere.com/web4/

## Play Around With What You Have

We have a login page wherein even if we retrieve the username or password, we can't submit it due to that monstrous countdown.
As with any web challenge, we head straight to the sources. There we find a script which opens the gates for us:

```javascript
<script type="text/javascript">
	passwd = 'easyhuh!';
	function checkPass() {
		a = document.getElementById("erp").value;
		b = document.getElementById("td").value;
		if (a !== 'userxyvw' || b !== passwd) {
			alert("Invalid Credentials");
			return false;
		}
		return true;
	}
</script>
```

We now know the username and, seemingly, even the password. 

Let's try entering the credentials. We can now open the console and try our luck:

```C
>checkPass();
>false
```

We see that what we entered isn't valid. 
Maybe the password isn't correct. Let's check:

```C
> javascript: passwd;
> realpasswd!!
```

There we go. 
Now that we have this, we can just enter it and (this is an improvisation on my end) click the submit button immediately after removing its `disabled` attribute.
Our flag appears: `LaDiDa!`

