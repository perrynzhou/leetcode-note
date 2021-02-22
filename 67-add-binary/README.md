55. 二进制求和
    给你两个二进制字符串，返回它们的和（用二进制表示）。

输入为 非空 字符串且只包含数字 1 和 0。

 

示例 1:

输入: a = "11", b = "1"
输出: "100"
示例 2:

输入: a = "1010", b = "1011"
输出: "10101"


提示：

每个字符串仅由字符 '0' 或 '1' 组成。
1 <= a.length, b.length <= 10^4
字符串如果不是 "0" ，就都不含前导零。



解题思路

1.判断a和b的长度，如果len(a)<len(b),则交换a,b=b,a

2.设置res :=make([]byte{},len(a)),为结果，同时设置tmp :=byte(0),设置j较短数组b的遍历下标，从0开始

3.设置主循环 

for i:=len(a)-1;i>=0;i--{ 

​		if j>=0 {

​		 tmp +=b[j]-'0'

​		 j--

​		}

​	tmp +=a[i]-'0'

​	// 需要tmp%2转为字符，方便后续转换字符串

​	res[i] = (temp%2)+'0'

​	temp/=2

}

if tmp>0 {

​	return "1"+string(res)

}

return string(res)