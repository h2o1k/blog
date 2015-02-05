
##Oracle over函数

###1. over用法
    rank() over ([partition_by_clause] order_by_clause)
###2. over用法实例(以scott/tiger为例)
**查询员工的sal"连续"求和**

	select sum(t.sal) over (order by t.ename) sum_sal, t.sal, t.* from emp t;
>先按照ename排序，然后连续求和

![查询结果][1]

	select sum(t.sal) over () sum_sal, t.sal, t.* from emp t;
>如果over()里面的内容是空的等同于sum(sal)

![查询结果][2]

	select sum(t.sal) over (partition by t.deptno) sum_sal, t.sal, t.* from emp t;
>按部门分组，每个部门的所有员工的sal求和

![查询结果][3]

	select sum(t.sal) over (partition by t.deptno order by t.ename) sum_sal, t.sal, t.* from emp t;
>按部门分组，每个部门的员工的sal连续求和

![查询结果][4]

###3. over作用
>
>可实现按指定的字段分组排序，对于相同分组字段的结棍集进行排序 
>其中partition_by为分组字段，order_by指定排序字段



[1]: 001.png
[2]: 002.png
[3]: 003.png
[4]: 004.png