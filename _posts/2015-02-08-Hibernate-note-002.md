

# Hibernate关联关系总结

>都是基于Annotation的配置

## 1对1

>Husband--->Wife

>一夫一妻制

### 1对1 单向 基于主键

	Husband实体类中
	@OneToOne
	@PrimaryKeyJoinColumn
	getWife()

### 1对1 单向 基于外键

	Husband实体类中
	@OneToOne
	@JoinColumn(name="my_wife_id")
	getWife()

### 1对1 单向 基于中间表
	
	未实验

### 1对1 双向 基于主键

	Husband实体类中
	@OneToOne
	@PrimaryKeyJoinColumn
	getWife()
	Wife实体类中
	@OneToOne
	@PrimaryKeyJoinColumn	
	getHusband()

### 1对1 双向 基于外键

	Husband实体类中
	@OneToOne
	@JoinColumn(name="my_wife_id")
	getWife()
	Wife实体类中
	@OneToOne
	@OneToOne(mappedBy="wife") // 告诉hibernate对方那里是主导
	getHusband()

### 1对1 双向 基于中间表

	未实验

## n对1

>User--->Group

>一个小组包含多个用户，但是每个用户只能属于一个小组

### n对1 单向 基于外键

	User实体类中
	@ManyToOne
	@JoinColumn(name="my_group_id")
	getGroup()

### n对1 单向 基于中间表

	未实验

### n对1 双向 基于外键

	User实体类中
	@ManyToOne
	@JoinColumn(name="my_group_id")
	getGroup()
	Group实体类中
	@OneToMany(mappedBy="group")	
	getUsers()

### n对1 双向 基于中间表

	未实验

## 1对n

>People--->Car

>一个人拥有很多车辆，每辆车只能属于一个人

### 1对n 单向 基于外键

	People实体类中
	@OneToMany
	@JoinColumn(name="people_id")
	getCars()

### 1对n 双向 基于外键

	同n对1 双向 基于外键

## n对n

>Teacher--->Student

>老师教学生，老师知道要教哪些学生，学生不知道/知道被哪些老师教

### n对n 单向 基于中间表

	Teacher实体类中
	@ManyToMany
	@JoinTable(
		name = "hibernate_a0201_teacher_student", 
		joinColumns = { @JoinColumn(name = "teacher_id"), }, 
		inverseJoinColumns = { @JoinColumn(name = "student_id") })
	getStudents()

### n对n 双向 基于中间表
	
	Teacher实体类中
	@ManyToMany
	@JoinTable(
		name = "hibernate_A0201_teacher_student", 
		joinColumns = { @JoinColumn(name = "teacher_id"), }, 
		inverseJoinColumns = { @JoinColumn(name = "student_id") })
	getStudents()
	Student实体类中
	@ManyToMany(mappedBy="students")
	getTeachers()