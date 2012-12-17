---
layout: post
title: Javascript_DOM编程艺术—笔记
description: note
keywords: Javascript
category: IT
tags: javascript DOM css HTML
---



学习的过程总是枯燥的，这本书还不错，浅显易懂

>		一.语法：（语法的广义含义包括语句、单词、标点符号等各个方面，它的狭义含义则特指语句结构方面的各项规则.）
>		1.语句：用Javascript或任何一种其他程序设计语言编写出来的脚本都是由一系列指令构成的，这些指令称为语句（statement）;
>
>		2.js语法：只需简单把各条语句放在不同的行上就可以分隔它们。放在同一行用分号来分隔它们。如：first.statement;second statement;
>
>		3.变量：3.1 程序设计语言时，把那些会发生变化的东西称为变量（variable）;  
>		3.2 给变量做出声明是一种良好的编程习惯。如：var mood = "happy"; var age = 33;
>		3.3 js语言里，变量和其它语法元素的名字都是区分字母大小写的。如mood不等于Mood;
>		3.4 js语法里不允许变量的名字中包含空格或标点符号（$例外）例如：错误（var my mood = "happy";）正确（var my_mood = "happy"）;
>		3.5 js变量名允许包含字母、数字、美元符号和下划线字符。
>
>		4.数据类型：
>		4.1 字符串：由零个或多个字符构成。包括字母、数字、标点符号和空格。必须放在引号里面（单引号或者双引号）如：var mood = "happy";
>		在js语言中，对字符进行转义需要用到反斜杠字符 如 var mood = "don\`t ask";
>		4.2 数值：包含小数点，整数，负数，任意位数。如 var temperature = -20.333333;
>		4.3 布尔值（boolean）：只有两种可取值—true或false(布尔值不能用引号括起来) 如 var married = true;
>
>
>		二、数组(array)：由名字相同的多个值构成的一个集合，集合中的每个值都是这个数组的元素（element），字符串、数值和布尔值都属于离散值（scalar）;
>
>		2.在JS脚本中，数组要用关键字（Array）来声明。如 var beatles = Array();
>
>		3.向数组中添加元素的操作称为填充（populating）.在填充数组时，要给出新元素的值，跟指定位置（位置通过下标[index]给出。数组里的每个元素都有相应下标）如：array[index] = element;
>		实例：var beatles = Array(4);
>		beatles[0] = "john";(数组下标是从0开始计数的);
>		beatles[1] = "paul";
>		beatles[2] = "ceorge";
>		beatles[3] = "ringo";
>		或者可以在声明数组的同时对它进行填充
>		var beatles = Array("john","Paul","George","Ringo");——字符串。（数组每个元素自然会分配下标）;
>		var years = Array(1940,1941,1942,1943);——数值;
>		var lennon = Array("john",1940,false);—— 三种数据类型混合;
>
>		4.数组元素还可以变量：
>		var name = "john";
>		beatles[0] = name;(将beatles数组的第一个元素赋值为“John”.)
>		4.1、数组的元素的值还可以是另一个数组的元素。
>		var names = Array("Ringo","John","George","Paul");
>		beatles[1] = names[3];(把beatles数组的第二个元素赋值为"Paul";)
>
>		4.2、数组还可以包含其他的数组，数组中的任何一个元素都可以把一个数组作为它的值：
>		var lennon = Array("john",1940,false);
>		var beatles = Array();
>		beatles[0] = lennon;
>
>		4.3、关联数组(associative array)
>		var lennon = Array();
>		lennon["name"] = "john";
>		lennon["year"] = 1940;
>		lennon["living"] = false;
>
>		三、操作符:算术符操作：加（+）减（-）乘（*）除（/）等于（=）
>		1、变量可以包括操作：var total = (1+4) * 5;
>		2、对变量进行操作：
>		var temp_fahrenheit = 95;
>		var temp_celsius = (temp_fahrenheit-32)/1.8;
>		3、给数值变量加1 例：year = year+1;也可以 year++;
>		4、加号（+）是一个比较特殊的操作符既可以用于数值，也可以用于字符串
>		var message = "i an feeling" + "happy";(也叫拼接);
>
>		拼接也可以通过变量来完成
>		var mood = "happy";
>		var message = "i an feeling"+mood;
>
>		拼接数值和字符串
>		var year = 2005;
>		var message = "the year is"+year;
>
>		一次性完成拼接和赋值
>		var year = 2005;
>		var message = "the year is";
>		message += year;
>
>		四、条件语句（conditional statement）：
>		1、if语句基本语法：
>		if(condition){
>		statements;
>		}
>		2.条件的求值永远是一个布尔值，即只能是true或false.
>
>		if(1 > 2){
>		alert("the world has gone mad!")
>		}
>
>		3. if……else条件语句：
>		if(1 > 2){
>		alert("the world has gone mad!");
>		}
>		else{
>		alert("all is well with the world");
>		}
>
>
>		五、比较操作符号：大于(">") 小于("<") 大于或等于(">=") 小于或等于（"<="）;
>		1.如果想比较两个值是否相等，用（“==”）比较操作符，单个等号（“=”）是用于完成赋值操作。
>		var my_mood = "happy";
>		var your_mood = "sad";
>		if(my_mood == your_mood){
>		alert("we both feel the same");
>		}(返回的结果是false);
>
>		2.不等于比较操作符（！=）
>		if(my_mood != your_mood){
>		alert("we're feeling different moods.");
>		} 
>
>		六、逻辑操作符(“&&”【逻辑“与”操作符】)（“||【逻辑“或”】操作符”）（“！”【逻辑“非”操作符】）.逻辑操作符的操作对像是布尔值。
>
>		if(num >=5 && mun <= 10){
>		alert("the number is in the right range.");
>		}
>		if(num >=5 || mun <= 10){
>		alert("the number is not in the right range.");
>		}
>
>		if(!(1 > 2)){
>		alert("all is well with the world");
>		}
>
>		七、循环语句：
>		1.【while】循环与if语句非常相似，它们的语法几乎完全一样。
>		while(condition){
>		statements;
>		}
>
>		实例：
>		c
>
>		2.【do…while】那些被包含在循环语句内部的代码至少执行一次;
>		do{
>		statements;
>		}while(condition);
>		实例：
>		var count = 1;
>		do{
>		alert(count)
>		count++;
>		} while(count < 11);
>
>		实例二：
>		var count = 1;
>		do{
>		alert(count)
>		count++;
>		} while(count < 1);
>
>
>		3.【for】重复执行一些代码;使循环控制结构更加清晰。
>		实例：
>		for(var count = 1; count < 11; count++ ){
>		alert(count);
>		}
>
>		实例二：
>
>		var beatles = Array("John","Paul","George","Ringo")
>		for(var count = 0; count < beatles.length; count++){
>		alert(beatles[count]);
>		}
>
>
>		八、函数（function）：如果需要多次使用同一组语句，还可以把它们打包成为一个函数，函数就是一组允许人们在代码里随时调用的语句。从效果上看，每个函数都相当于一个短小的脚本。
>
>		实例：
>		function shout(){
>		var beatles = Array("John","Paul","George","Ringo");
>		for(var count = 0;count < beatles.length;count++){
>		alert(beatles[count]);
>		}
>		}
>
>		2.参数（argument）：把数据传递给函数;
>		实例：
>
>		function multiply(num1,num2){
>		var total = num1*num2;
>		alert(total);
>		}
>
>		multiply(10,2)【调用这个函数】