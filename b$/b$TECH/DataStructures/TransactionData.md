# DataStructure of a Bitcon Transaction 

## Example
This Block contains the first transaction where Satoshi Nakamoto paid Hal Finney 10 BTC. This was the first time one person paid another person in Bitcoin.

This early transaction type is known as `Pay to Public Key (P2PK)`. It is the simplest type. 
<span style="color:red; font-weight:bold">Attention</span>: 

> Popular types used nowadays are more complicated!

Since the **data is in binary**, we must use a printable representation of it to make it viewable in this web-page. I choose hexadecimal:

<pre>
0100000001c997a5e56e104102fa209c6a852dd90660a20b2d9c352423edce25
857fcd3704000000004847304402204e45e16932b8af514961a1d3a1a25fdf3f
4f7732e9d624c6c61548ab5fb8cd410220181522ec8eca07de4860a4acdd1290
9d831cc56cbbac4622082221a8768d1d0901ffffffff0200ca9a3b0000000043
4104ae1a62fe09c5f51b13905f07f06b99a2f7159b2225f374cd378d71302fa2
8414e7aab37397f554a7df5f142c21c1b7303b8a0626f1baded5c72a704f7e6c
d84cac00286bee0000000043410411db93e1dcdb8a016b49840f8c53bc1eb68a
382e97b1482ecad7b148a6909a5cb2e0eaddfb84ccf9744464f82e160bfa9b8b
64f9d4c03f999b8643f656b412a3ac00000000
</pre>

Here I have tried to work out by hand what that meant (how far I got before losing interest):

<table>
<tr>
<th>Hex Data</th>	<th>Meaning</th>
</tr>
<tr>
<td>01000000</td>	<td>Version 1 (little endian uint32)</td>
</tr>
<tr>
<td>01</td>	<td>Number of transaction inputs (compact-int)</td>
</tr>
<tr>
<td colspan="2"><b>First input</b></td>	
</tr>
<tr>
<td>c997a5e56e104102&nbsp; fa209c6a852dd906&nbsp; 60a20b2d9c352423&nbsp; edce25857fcd3704</td>	<td>Hash of referenced transaction (32 octets)</td>
</tr>
<tr>
<td>00000000</td><td>index of output in referenced transaction (uint32)</td>
</tr>

<tr>
<td>48</td> <td>length of unlocking script (compact-int). 48 hex is 72 decimal.</td>
</tr>

<tr>
<td>47304402204e45e1 6932b8af514961a1 d3a1a25fdf3f4f77 32e9d624c6c61548 ab5fb8cd41022018 1522ec8eca07de48 60a4acdd12909d83 1cc56cbbac462208 2221a8768d1d0901</td>	<td>unlocking script (72 octets)</td>
</tr>

<tr>
<td>ffffffff</td><td>sequence</td>
</tr>
<tr>
<td>02</td><td>	Number of outputs</td>
</tr>
<tr>
<td><b>First output</b></td>
</tr>	
<tr>
<td>00ca9a3b00000000</td><td>	amount 1000000000 satoshi i.e. 10 BTC (int64)</td>
</tr>
<tr>
<td>43</td><td>	length of locking script</td>
</tr>
<tr>
<td>4104ae1a62fe09c5 f51b13905f07f06b 99a2f7159b2225f3 74cd378d71302fa2 8414e7aab37397f5 54a7df5f142c21c1 b7303b8a0626f1ba ded5c72a704f7e6c d84cac</td><td>locking script</td>
</tr>
<tr>
<td><b>Second output</b></td>
</tr>	
<tr>
<td>00286bee00000000</td><td>	amount 40 BTC. This is change.</td>
</tr>
<tr>
<td>43</td><td>	length of locking script</td>
</tr>
<tr>
<td>410411db93e1dcdb 8a016b49840f8c53 bc1eb68a382e97b1 482ecad7b148a690 9a5cb2e0eaddfb84 ccf9744464f82e16 0bfa9b8b64f9d4c0 3f999b8643f656b4 12a3ac</td><td>	locking script</td>
</tr>
<tr>
<td>00000000</td><td>	lock time = unlocked (4 octets)
</table>

I should probably decode the locking scripts on the outputs. 

The first `41` is `OP_PUSHDATA` for 4116 bytes. Then we have the 4116 bytes of data to be pushed onto the stack and finally `ac` at the end is `OP_CHECKSIG`, which expects a signature and public key on the stack which it takes off the stack and checks. This script only really gets executed when the money is spent.

For historical reasons `locking-scripts` were called `pubkey scripts`, and `unlocking scripts` were called `signature scripts`. But those older names are misleading for newer transaction types.

The compact form of integers used by Bitcoin is sometimes called `varint` (variable-length integer) but this is a potential source of confusion as there are other things named varint IIRC.

You can check the little endian numbers by reversing them byte-wise (two hex digits at a time) into a big endian representation and feeding that into Windows Calculator in programmer mode - here's that second output amount (00286bee00000000LE -> 00000000ee6b2800BE):

That's how we know 00286bee00000000 means 40000000000 Satoshi. Which is 40 BTC.

You can, of course, rather easily get a JSON representation of this transaction using most **blockchain explorers**. I find that a bit unsatisfactory as they often introduce some artificial elements (e.g. both 'hex' and 'asm' representations of the script) so you're never certain how exactly the JSON items correspond to parts of the underlying data. Hence the above decoding attempt. 

