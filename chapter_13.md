第13章
## 多级继承
**问题描述:**
```
class A{}
class B:public A｛｝
class C:public A{}
class D: public B,public C{}
```
由D引用对象A有歧义.因为D中会包含两个A.
**解决方法:** 虚拟继承,即让D中只包含一个A.
**需要注意两点:**
- 构造函数，`D():A(),B(),C(){}`
- 如果B和C中有同名的成员函数，D中调用会产生歧义，需要重新封装.
