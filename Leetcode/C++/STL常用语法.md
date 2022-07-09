# STL常用语法

Let's learn C++ STL by concrete examples!

*Source code @ Leetcode*

[TOC]

## Vector

### Initialization

```c++
int main(){
	vector<int> vecl;	// Empty
    vector<float> vec2(3);	//	[0,0,0]
    vector<char> vec3(3,'a');  //	['a', 'a', 'a']
    vector<char> vec4(vec3);  //	['a', 'a', 'a'], copy from vec3, same elements.
}
```



### resize()

```c++
vector<vector<int>> sums;
sums.resize(m, vector<int>(n + 1));	

/* Example:
输入：
m = 3
n = 2
输出
sums = 
[[0,0,0],
 [0,0,0],
 [0,0,0]]
 
```



### Comparison

当vector里的元素是基本数据类型时，可以直接使用 "=="， "!="， ">="，"<=" 来对两个vector进行比较。



## String

### length() / size()

C++标准库中的string中两者的源代码如下：

     _NODISCARD size_type length() const noexcept { // return length of sequence
            return _Get_data()._Mysize;
        }
    
    _NODISCARD size_type size() const noexcept { // return length of sequence
        return _Get_data()._Mysize;
    }     

由此可以看出，length()与size()没有区别，都是返回string对象中元素数量，即返回std::distance(begin(),end()) 。length是因为沿用C语言的习惯而保留下来的，string类最初只有length，引入STL之后，为了兼容又加入了size，它是作为STL容器的属性存在的，便于符合STL的接口规则，以便用于STL的算法。

具体可参考：https://en.cppreference.com/w/cpp/string/basic_string/size
