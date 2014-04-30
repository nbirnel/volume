<html>
<head>
<meta name="generator" content="groff -Thtml, see www.gnu.org">
<meta http-equiv="Content-Type" content="text/html; charset=US-ASCII">
<meta name="Content-Style" content="text/css">
<title>volume</title>

</head>
<body>

<h1 align="center">volume</h1>

<a href="#NAME">NAME</a><br>
<a href="#SYNOPSIS">SYNOPSIS</a><br>
<a href="#DESCRIPTION">DESCRIPTION</a><br>
<a href="#OPTIONS">OPTIONS</a><br>
<a href="#COMMANDS">COMMANDS</a><br>
<a href="#EXAMPLES">EXAMPLES</a><br>
<a href="#CONFIGURATION">CONFIGURATION</a><br>
<a href="#EXIT STATUS">EXIT STATUS</a><br>
<a href="#AUTHOR">AUTHOR</a><br>
<a href="#BUGS">BUGS</a><br>
<a href="#SEE ALSO">SEE ALSO</a><br>
<a href="#LICENSE">LICENSE</a><br>

<hr>


<h2>NAME
<a name="NAME"></a>
</h2>


<p style="margin-left:11%; margin-top: 1em">volume &minus;
a simple wrapper around amixer for changing audio
volumes</p>

<h2>SYNOPSIS
<a name="SYNOPSIS"></a>
</h2>


<p style="margin-left:11%; margin-top: 1em"><b>volume [-v]
[CONTROL] [DIRECTION] [AMOUNT]</b></p>

<p style="margin-left:11%; margin-top: 1em"><b>volume [-v]
[CONTROL] on</b></p>

<p style="margin-left:11%; margin-top: 1em"><b>volume [-v]
a[lternate]</b></p>

<h2>DESCRIPTION
<a name="DESCRIPTION"></a>
</h2>


<p style="margin-left:11%; margin-top: 1em"><b>volume</b>
changes the volume of the given control.</p>

<p style="margin-left:11%; margin-top: 1em">In the first
form, <b>CONTROL</b> is changed in <b>DIRECTION</b> by
<b>AMOUNT.</b></p>

<p style="margin-left:11%; margin-top: 1em">In the second
form, <b>CONTROL</b> is turned on, and other <b>CONTROLs</b>
are turned off. (Master is always turned on.)</p>

<p style="margin-left:11%; margin-top: 1em">In the third
form, headphone and speaker are swapped, defaulting to
headphone on if both are on, and to speaker on if both are
off. (Master is always turned on.)</p>

<h2>OPTIONS
<a name="OPTIONS"></a>
</h2>


<table width="100%" border="0" rules="none" frame="void"
       cellspacing="0" cellpadding="0">
<tr valign="top" align="left">
<td width="11%"></td>
<td width="3%">


<p style="margin-top: 1em"><b>-v</b></p></td>
<td width="4%"></td>
<td width="82%">


<p style="margin-top: 1em">Print what is being done to
standard out. Useful for scripting with GUI notifiers.</p></td></tr>
</table>

<h2>COMMANDS
<a name="COMMANDS"></a>
</h2>


<p style="margin-left:11%; margin-top: 1em"><b>CONTROLS
<br>
m[aster]</b></p>

<p style="margin-left:18%;">This is the default.</p>

<p style="margin-left:11%;"><b>h[eadphones] <br>
s[peaker]</b></p>


<p style="margin-left:11%; margin-top: 1em"><b>DIRECTION</b></p>

<table width="100%" border="0" rules="none" frame="void"
       cellspacing="0" cellpadding="0">
<tr valign="top" align="left">
<td width="11%"></td>
<td width="1%">


<p><b>+</b></p></td>
<td width="6%"></td>
<td width="31%">


<p>This is the default.</p></td>
<td width="51%">
</td></tr>
<tr valign="top" align="left">
<td width="11%"></td>
<td width="1%">


<p><b>-</b></p></td>
<td width="6%"></td>
<td width="31%"></td>
<td width="51%">
</td></tr>
</table>

<p style="margin-left:11%;"><b>t[oggle]</b></p>

<p style="margin-left:18%;">Toggle on or off.</p>

<p style="margin-left:11%; margin-top: 1em"><b>AMOUNT</b>
<br>
Defaults to 5 decibels. This option is irrelevant to
toggling.</p>

<h2>EXAMPLES
<a name="EXAMPLES"></a>
</h2>


<p style="margin-left:11%; margin-top: 1em"><b>volume</b>
increase master volume by 5 db.</p>

<p style="margin-left:11%; margin-top: 1em"><b>volume h
-</b> decrease headphone volume by 5 db.</p>

<p style="margin-left:11%; margin-top: 1em"><b>volume a</b>
swap between headphones and speakers.</p>

<h2>CONFIGURATION
<a name="CONFIGURATION"></a>
</h2>


<p style="margin-left:11%; margin-top: 1em">To use your
multimedia keys using <b>xbindkeys(1)</b> and get
notifications using <b>dzen(1)</b> you might want to add
something like:</p>

<p style="margin-left:22%; margin-top: 1em">&quot;volume -v
alternate | dzen2 -l 2 -p 1 -e
&rsquo;onstart=uncollapse&rsquo; -ta l&quot;</p>


<p style="margin-left:22%; margin-top: 1em">XF86AudioMute</p>

<p style="margin-left:22%; margin-top: 1em">&quot;volume -v
- | dzen2 -p 1 -ta l&quot;</p>


<p style="margin-left:22%; margin-top: 1em">XF86AudioLowerVolume</p>

<p style="margin-left:22%; margin-top: 1em">&quot;volume -v
+ | dzen2 -p 1 -ta l&quot;</p>


<p style="margin-left:22%; margin-top: 1em">XF86AudioRaiseVolume</p>

<p style="margin-left:11%; margin-top: 1em">to your
<b>$HOME/.xbindkeys</b> and add</p>

<p style="margin-left:22%; margin-top: 1em">xbindkeys</p>

<p style="margin-left:11%; margin-top: 1em">to your
<b>$HOME/.xinitrc</b></p>

<h2>EXIT STATUS
<a name="EXIT STATUS"></a>
</h2>


<p style="margin-left:11%; margin-top: 1em">exits non-zero
on error.</p>

<h2>AUTHOR
<a name="AUTHOR"></a>
</h2>


<p style="margin-left:11%; margin-top: 1em">Noah Birnel</p>

<h2>BUGS
<a name="BUGS"></a>
</h2>


<p style="margin-left:11%; margin-top: 1em">I doubt the
hardcoded values work for all audio cards. Probably
others.</p>

<h2>SEE ALSO
<a name="SEE ALSO"></a>
</h2>


<p style="margin-left:11%; margin-top: 1em"><b>amixer(1)
<br>
alsamixer(1) <br>
dzen(1) <br>
xbindkeys(1)</b></p>

<h2>LICENSE
<a name="LICENSE"></a>
</h2>


<p style="margin-left:11%; margin-top: 1em">Copyright 2014
Noah Birnel</p>

<p style="margin-left:11%; margin-top: 1em">Do whatever you
want with this software.</p>
<hr>
</body>
</html>
