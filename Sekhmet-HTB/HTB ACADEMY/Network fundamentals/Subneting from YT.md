
**IP**
 `192.168.1.x`
  `192.168.1` = network address part
 `x`= host part


**Mask**
`255.255.255.0`
`255` = cannot be changed by any ways
`0` = can be changed (mostly the host part)


![[Pasted image 20240726032723.png]]

Depending of the mask, you can generate more network address like class C
you mask will look like `255.255.255.0` 
But you have less host (the `0`)

If you have `255.0.0.0`
You only have `255` network adress
but a lot of host adress

-----------------------------------

**Calculating mask and creating subnet**

https://www.youtube.com/watch?v=mJ_5qeqGOaI&list=PLIhvC56v63IKrRHh3gvZZBAGvsvOhwrRF&index=6


In an IP like `192.168.1.0/24`
`24` = number of 1 in the mask
mask = `255.255.255.0`
binary-mask = `11111111.11111111.11111111.00000000`

You can create sub-networks by "stealing" bits from host.
To do this, you first need to figure out the number of sub-network you need like 4.

`128.64.32.16.8.4.2.1`
`256.128.64.32.16.8.4.2`

You see that to get 4 subnet you need to take at least 2 bits so your mask gonna look like this : `255.255.255.192` / `11111111.11111111.11111111.11000000`
Where `192 = 11000000` (`128+64`)

So here we have a new IP `192.168.1.0`

To have the range and the number of host of this sub-network you need to find the increment which you can do by this way :

The increment is equal to the last 1 of your binary subnet mask
`11111111.11111111.11111111.11000000`
For this example the increment is equal to 64 because we take the last 1 which correspond to 64

So for this network the number of host is 64 in the range `192.168.1.0 - 192.168.1.63`
Here we have 63 because `192.168.1.0` is almost an address (same principle as python indexation)

To get all range of all of our 4 subnet we just continue by adding 64 etc (don't forget to considere the first one as an address)
![[Pasted image 20240726063902.png]]


10.200.20.0/29
`11111111.11111111.11111111.11111000`
255.255.255.224