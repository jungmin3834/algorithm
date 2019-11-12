# algorithm
# 1108. Defanging an IP Address

##문제 링크
##https://leetcode.com/problems/defanging-an-ip-address/

![title](https://github.com/jungmin3834/algorithm/blob/master/image/Defanging-an-IP-Address.png)

```cpp
 string defangIPaddr(string address) {
	for (int i = address.size() - 1; i > -1; i--)
	{
		if (address[i] == '.')
		{
			address.insert(address.begin() + i + 1,']');
			address.insert(address.begin() + i,'[');
		}
	}
	return address;
}
```

```python

def defangIPaddr(self, address):
        return address.replace(".", "[.]")

```