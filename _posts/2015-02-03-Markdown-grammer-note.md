
#一、标题
Setext形式的一级标题
======
Setext形式的二级标题
------
#Atx形式的一级标题
##Atx形式的二级标题

#二、区块引用
>区块引用
>
>换行需要一个空行

#三、斜体和加粗
*斜体*和**加粗**

_斜体_和__加粗__
#四、列表
无序列表可用 *,+,-

* 星号列表1
* 星号列表2
* 星号列表3

有序列表用 使用一般的数字接着一个英文句点和空格

1. 有序列表1
2. 有序列表2
3. 有序列表3

测试

* a

    dddddd

* b
* c
* d

#五、链接
这是一个行内链接[h2o1k.net](http://h2o1k.net/ "这是标题")


这是一个参考链接[Google][1] than [Yahoo][2] or [MSN][3].

[1]: http://google.com/ "Google"
[2]: http://search.yahoo.com/ "Yahoo Search"
[3]: http://search.msn.com/ "MSN Search"

#六、图片
图片：行内形式![头像](http://www.iteye.com/upload/logo/user/544790/a7508e1e-dd5c-367b-8b5b-0b88fdafb105.png?1314453413 "这是标题，标题是可选的")

图片：参考形式![头像][id]

[id]: http://www.iteye.com/upload/logo/user/544790/a7508e1e-dd5c-367b-8b5b-0b88fdafb105.png?1314453413 "这是标题，标题是可选的"

#七、代码

**标记一段代码，每行代码前留4个空格**



	public void testFindStudent() {
		List<Map<String, String>> stuList = stuMapper.findStudent();
		for (Map<String, String> stu : stuList) {
			String stuId = stu.get("STUDENTID");
			System.out.println(stuId);
			List<StuProcess> plist = mapper.findTrainProcess(stuId);
			if (plist != null) {
				for (StuProcess p : plist) {
					System.out.println(p);
				}
			}
		}
	}



**标记段内代码用反单引号**

I strongly recommend against using any `<blink>` tags.

I wish SmartyPants used named entities like `&mdash;`
instead of decimal-encoded entites like `&#8212;`.


If you want your page to validate under XHTML 1.0 Strict,
you've got to put paragraph tags in your blockquotes:


#八、分割线
 
一行中用3个或以上的星号、减号、底线来表示

***

---

___


#参考
1. [Markdown 语法说明 (简体中文版)](http://wowubuntu.com/markdown/)