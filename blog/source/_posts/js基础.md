---
title: js基础
date: 2015-04-25 17:23:16
tags: 
	- 数组
---
#### 数组

   		1.数组的作用，用于保存多个数据
   		2.数组中的数组我们成为数组的元素
   		3.数组中可以同时保存多个类型的元素，但是不推荐

#### 数组的声明方式

		1.方法一
	   *var arr=new Array(1,2,3,4,5) 直接添加元素
	   *var arr=new Array(6) 创建一个具有默认长度的数组，几乎没有用
		2.方法二:常用
		*数组字面量形式：var arr=[1,2,3,4];
#### 数组的长度

		数组的length属性表示数组中元素的个数

#### 数组的索引

		数组中的元素是按照索引排列，索引从0开始
		我们可以根据索引获取和修改数组中的某个元素

#### 数组的长度和索引的关系

		数组中最后一项的索引为arr.length-1
		数组中新项的索引，为arr.length

#### 数组的基本操作方式
#### 1.正向遍历
		````JavaScript
		var arr=[1,2,3,4,5];
		for(var i=0;i<arr.length;i++){
			console.log(arr[i]);
		}
		````
#### 2.反向遍历
		````JavaScript
		var arr=[1,2,3,4,5];
		for(var i=arr.length-1;i>0;i--){
			console.log(arr[i]);
		}
		````
#### 3.将0-99的所有数放到数组中
	````JavaScript
		var arr=[];
		for(var i=0;i<100;i++){
		arr[i]=i;
		}
		````
	
#### 4.将1-100中所有奇数放到数组中
		````JavaScript
		var arr=[];
		for(var i=1;i<=100;i++){
	if(i%2!=0){
	arr[arr.length]=i;
 	 }
		}
		````

#### 5.将1-100之间能被3整除的数字，存到数组中
	````JavaScript
	var arr=[];
	for(var i=1;i<=100;i++){
	if(i/3==0){
	arr[arr.length]=i;
 	}
	}
	````

#### 6.求一组数中的所有的数的和 和平均值
	````JavaScript
 	var arr=[12,34,56,67,78,90];
	var sum=0,v;
	for(var i=0;i<arr.length;i++){
	sum+=arr[i];
	}
	v=sum/arr.length;
	````

#### 7.求一组数中的最大值
		````JavaScript
		var arr=[12,34,56,67,78,90];
		var max=0;
		for(var i=0;i<arr.length;i++){
			if(arr[i]>max){
				max=arr[i];
		  }
		}
		````

#### 8.求一组数中的最小值及其索引值
		````JavaScript
		var arr=[12,34,56,67,78,90];
		var min=0,v;
		for(var i=0;i<arr.length;i++){
			if(arr[i]<min){
				min=arr[i];
				v=i;
		  }
		} 
		````
#### 9.将字符串数组用|或其他符号分割
		````JavaScript
		var arr =["a","b","c"];
		var str=arr[0];
		var fenGeFu='-';
		for(var i=1;i<arr.length;i++){
			str+=fenGefu+arr[i];
		}
		````
#### 10.翻转数组
		````JavaScript
		var arr=[1,2,3,4,5];
		var resultArr=[];
		for(var i=arr.length-1;i>0;i--){
			resultArr[resultArr.length]=arr[i];
		}
		````
#### 11.要求将数组中的0项去掉，将不为0的值存入一个新的数组，生成新的数组
		````JavaScript
		var arrNew=[];
		var arr=[1,0,3,4,50,5,0,9,0,0];
		for(var i in arr){
			if(arr[i]!==0){
			  arrNew.push(arr[i]);
		  }
		}
		````
#### 12.冒泡排序，从小到大
		````JavaScript
		var count=0;//设置一个变量去记录当前比较过得轮数
		//1.外层循环控制比较的轮数
		for(var i=0;i<arr.length-1;i++){
			count++;
			//在每一轮开始的时候，假设当前这一轮已经比较完毕了
			var flag=true;
			//2.内层循环 控制每一轮比较的次数
			for(var j=0;j<arr.length-1-i;j++){
			//3.如果当前项大于了后一个项
			if(arr[j]>arr[j+1]){
				//4.交换两个位置的值
				var temp=arr[j];
				arr[j]=arr[j+1];
				arr[j+1]=temp;
				//如果发生了任意一次交换。说明比较没有完毕，我们阻止跳出
				flag=false；
		       }
			}
			//验证假设条件是否成立
			if(flag){
		       break;
		     }

		}
		````