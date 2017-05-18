# day1

##sscanf 的使用
~~~
#include <iostream>
#include <string>
#include <stdio.h> // sscanf
using namespace std;
int main(void) {
	int num = 0;
	string str = "hujianjun 80";
	sscanf(str.c_str(), "hujianjun %d", &num);
	cout << num << end;
}
~~~

输出 80

#day2

##混用string对象和C风格字符串
~~~
string s("Hello World");

char *str = s;//error
const char *str = s.c_str(); // true
~~~

##使用数组初始化vector对象

	int int_arr[] = {0, 1, 2, 3, 4, 5, 6, 7};
	vector<int> ivec(begin(int_arrr), end(int_arr));
	
	vector<int> ivec1(int_arr, int_arr+8);

##int \*p[4]\(整型指针的数组) 与 int(\*ptr)[4]\(指向含有4个整数的数组)

	int *p[4];
	int a = 0, b = 0, c = 0, d = 0;
	p[0] = &a;p[1] = &b;p[2] = &c;p[3] = &d;
	
	int array[4] = {0, 1, 2, 3,};
	int (*ptr)[4] = &array;
	
	int array2[4][4] = {0, 1, 2, 3, 4, 5, 6};
	int (*ptr1)[4] = array2;

#day3
##for循环

	for(initializer; condition; expression)
	statement

	initializer // 只能有一条声明语句,因此所有变量的基础类型必须相同
	for(decltype(v.size()) i = 0, sz = v.size(); i != sz; ++i)
	v.push_back(v[i]);

#day4
##fun(string &str) 与 fun(const string &str)

	void fun1(string &str){
	}
	string str = "hello world";
	fun1(str);
	fun1("hello world");// error
	
	void fun2(const string &str){
	}
	string str = "hello world";
	fun2(str);
	fun2("hello world"); // true
	
##数值引用形参
	// 只能处理 int a[] = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9};
	// 不能处理 int b[] = {0, 1, 2, 3, 4, 5, 6, 7, 8};
	void print(int (&arr)[10])
	{
		for (auto elem : arr)
		cout << elem << end;
	}
	//使用 print(begin(a), end(a));
	void print(const int *beg, const int *end){
		while(beg != end){
		cout << *beg++ << end;
		}
	}
	// int j[] = {0, 1}
	//使用 print(j, end(j) - begin(j))
	void print(const int ia[], size_t size){
		for (size_t i = 0; i != size; ++i){
			cout << ia[i] << endl;
		}
	}

## int &arr[10] 与 int (&arr)[10]
- int &arr[10] 表示arr10个引用构成的数组   不成立 永远是错的
- int (&arr)[10]表示具有10个整数的整型数组的引用

## int *matrix[10] 与 int (*matrix)[10]
- int *matrix[10] 表示10个指针构成的数组
- int (*matrix)[10] 表示 指向含有10个整数的数组指针

	void print (int (*matrix)[10], int rowSize){}
	void print(int matrix[][10], int rowSize){}
	//以上两种形式等价
> 胡建军
>>　Owen

- apple
	- green apple
	- red apple
- banana
- orange


