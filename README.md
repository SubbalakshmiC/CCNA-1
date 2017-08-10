# CCNA revision notes

Hello there, welcome to the CCNA revision notes repo, this page contains the notes from:

* Dan Easteal (me)
	* [Dan's notes](https://github.com/446163/CCNA/blob/master/ccnaDan.md)
* Simon Light
	* [Simon's notes](https://github.com/446163/CCNA/blob/master/CCNASimon.md)
* Sam Hastings
	* [Sam's notes](https://github.com/446163/CCNA/blob/master/CCNA_Sam.md)

To access the notes just click on the corresponding file above. 

* There are a couple of other files in this repository that you may find useful, these are:
	* [Simon's Mindmaps (WIP)](https://github.com/446163/CCNA/tree/master/Mind%20Maps)
	* [Sam's Cisco CLI Cheatsheet](https://github.com/446163/CCNA/blob/master/Cisco%20CLI%20Cheat%20Sheet.pdf)

Here are some useful tables that you may find good for quick reference 

###### OSI compared to TCP/IP 
<table>
	<tr>
	<th colspan="3"> OSI </th>
	<th colspan="3"> TCP/IP </th>
  </tr>
  <tr>
    <th>Layer Number</th>
    <th>PDU</th>
    <th>Layer Name</th>
    <th>Layer Name</th>
    <th>PDU</th>
    <th>Layer Number</th>
  </tr>
  <tr>
    <td>7</td>
    <td rowspan="3">Messages</td>
    <td>Application</td>
    <td rowspan="3">Application</td>
    <td rowspan="3">Data</td>
    <td rowspan="3">4</td>
  </tr>
  <tr>
    <td>6</td>
    <td>Presentation</td>
  </tr>
  <tr>
    <td>5</td>
  	<td>Session</td>
  </tr>
  <tr>
    <td>4</td>
    <td>Segment</td>
  	<td>Transport</td>
  	<td>Transport</td>
    <td>Segment</td>
    <td>3</td>
  </tr>
  <tr>
    <td>3</td>
    <td>Packet</t>
  	<td>Network</td>
  	<td>Internet</td>
    <td>Packet</t>
    <td>2</t>
  </tr>
  <tr>
    <td>2</td>
    <td>Frame</td>
  	<td>Data Link</td>
    <td rowspan="2">Link</td>
    <td rowspan="2">Frame</td>
    <td rowspan="2">1</td>
  </tr>
  <tr>
    <td>1</td>
    <td>Bit</td>
  	<td>Physical</td>
  </tr>
</table>

###### Encapsulation

<table>
<tr>
	<td >Application</td>		
	<td colspan="4" ></td>		
	<td>User data</td>		
	<td rowspan="3"> </td>
</tr>
<tr>
	<td> Transport </td>
	<td colspan="2"> </td>
	<td> L4 header </td>
	<td> Other Header</td>
	<td> User data </td>

</tr>
<tr>
	<td> Internet </td>
	<td></td>
	<td> L3 Header
	<td> L4 header </td>
	<td> Other Header</td>
	<td> User data </td>
</tr>
<tr>
	<td> Link </td>
	<td> L2 Header
	<td> L3 Header
	<td> L4 header </td>
	<td> Other Header</td>
	<td> User data </td>
	<td> Trailer </td>
</tr>
</table>

###### Classing table

|Class|binary range|decimal range|maximum number of hosts|Layout
|---|---|---|---|---|
|A|**0**0000001 - **0**1111110|1 - 126| 16,777,214|N.H.H.H|
|B|**10**000000 - **10**111111|128 - 191| 65,534|N.N.H.H|
|C|**110**00000 - **110**11111|192 - 223| 254|N.N.N.H|
|D|**1110**0000 - **1110**1111|224 - 239| Multicast |
|E|**1111**0000 - **1111**1111|240 - 255| Reserved |
| | **01111111** | 127 | used for diagnostics|


###### Subnetting table

|Step|128|64|32|16|8|4|2|1|
|---|---|---|---|---|---|---|---|---|
|Mask (.x)|***128***|***192***|***224***|***240***|***248***|***252***|***254***|***255***|
|A: /8 255.x.\*.\*|/9|/10|/11|/12|/13|/14|/15|/16|
|B: /16 255.255.x.\*|/17|/18|/19|/20|/21|/22|/23|/24|
|C: /24 255.255.255.x|/25|/26|/27|/28|/29|/30|/31|/32|



If you have any questions about the notes then just ask any of us. On the other hand you can just look at another set of notes as they may make more sense to you as they are all for you to use. 

> if in doubt, the answer is probably: "it depends"
