# 页面ui规范模板

注：vue框架使用element-ui，项目组件主要参考element-ui

​		地址： https://element.eleme.cn/#/ 

**全局：**

​	**组件与组件**

​		**左右边距：10px;**

​		**上下：10px;**



## 一、表格

**要求：**

​	**斑马线、完整边框、涉及到操作按钮，按参考按钮规范。**

**表格统一属性：**

​	固定表头:固定客户名称栏目，右固定操作栏目

​    表头：背景色#FAFAFA           

​	字体颜色：#333333 

 **表格内容：** 

​	列表的高度:宽度自适应，但根据字段的重要性显示，重要的字段优先完整显示，出宽度限	     以“...”代替，鼠标经过展示全部内容

​	空数据：表格某部分吴书记时，使用“-”来填充显示，对于数据为零的单元格，填上0

​	对齐：表格文字内容左对齐，数字内容右对齐

​	金额内容：千位符分隔。

​	表格中操作：文字按钮 ，字体大小与表格内容相同，按钮一行排列。

​							删除按钮#F07070

​							其他按钮#3FADFF**

​	**每列宽度：**

​			序号：60px;

​			修改人、姓名不超过五个字：100px;

​			模块名称、公司名称：自适应+提示窗；

​			操作按钮：最小宽度：70*n;

​			时间类：全部显示：200px; 年月日：150px;	

​			内容不确定性：自适应+提示窗；	

**视图：**

![image-20200113113827090](https://uf-share-file.oss-cn-shenzhen.aliyuncs.com/md-file/image-20200113113827090.png)

### 1.表格数据加载需要加载loading

![image-20200113112440898](https://uf-share-file.oss-cn-shenzhen.aliyuncs.com/md-file/image-20200113112440898.png)

### 2.特殊表格（待办列表）

**要求：设置不同行背景、完整边框、涉及到操作按钮，按参考按钮规范。**

![image-20200113114426815](https://uf-share-file.oss-cn-shenzhen.aliyuncs.com/md-file/image-20200113114426815.png) 

**代码：**

![image-20200113125135557](https://uf-share-file.oss-cn-shenzhen.aliyuncs.com/md-file/image-20200113125135557.png)







## 二、 查询输入框 

**要求：统一宽度（ el-col>5;width:20.8% ）高度（32px）**

**1.查询条件输入框：所有查询框高度、宽度统一** 

**![image-20200113125357294](https://uf-share-file.oss-cn-shenzhen.aliyuncs.com/md-file/image-20200113125357294.png)**

**2.查询单选框：所有查询框高度、宽度统一**

**![image-20200113125521942](https://uf-share-file.oss-cn-shenzhen.aliyuncs.com/md-file/image-20200113125521942.png)**

**3.日期选择器：所有查询框高度、宽度统一**

**![image-20200113125611157](https://uf-share-file.oss-cn-shenzhen.aliyuncs.com/md-file/image-20200113125611157.png)**

 **4.查询框排列：每行4个查询框，默认显示一行，其他折叠，点击 下拉图标 显示全部**



**代码：**

​	输入框：

​	![image-20200113133434324](https://uf-share-file.oss-cn-shenzhen.aliyuncs.com/md-file/image-20200113133434324.png)

​	时间选择器：

![image-20200113133525495](https://uf-share-file.oss-cn-shenzhen.aliyuncs.com/md-file/image-20200113133525495.png)

​	选择器：

​	![image-20200113133624032](https://uf-share-file.oss-cn-shenzhen.aliyuncs.com/md-file/image-20200113133624032.png)





## 三、按钮

**要求：** 

​	**1.按钮皆采用图标加文字方式，不同操作图标统一 ，宽度为：75px;高度:32px;文字大小16px;不超过4字，超过100px宽度，给定padding:8px 24px;**

​	**2.遇到横排多个按钮，最小间距为10px;**

​	**3.按钮的圆角为4px;特殊圆角50%；**

​	**4.在查询条件下方中间 查询：# 57A3F3** 

​	**5.下载导入模板、导入、导出、新增：# 409EFF** 

​	**6.批量删除：#F78989（class="redText"）** ；**删除操作必须二次确认**

​			

### 1.查询按钮：

![img](https://www.wulihub.com.cn/gc/Qo40NJ/images/%E6%8C%89%E9%92%AE/u36.png)

### 2.按钮响应时图标,位置于表格左上方横向排列 ：

![image-20200113134155364](https://uf-share-file.oss-cn-shenzhen.aliyuncs.com/md-file/image-20200113134155364.png)

### 3.操作按钮：

![img](https://www.wulihub.com.cn/gc/Qo40NJ/images/%E6%8C%89%E9%92%AE/u40.png)



 代码：

​	普通按钮：![image-20200113135625035](https://uf-share-file.oss-cn-shenzhen.aliyuncs.com/md-file/image-20200113135625035.png)

​	普通删除按钮：![image-20200113135907691](https://uf-share-file.oss-cn-shenzhen.aliyuncs.com/md-file/image-20200113135907691.png)

​	文字按钮：![image-20200113135735454](https://uf-share-file.oss-cn-shenzhen.aliyuncs.com/md-file/image-20200113135735454.png)

​	文字删除按钮：![image-20200113135808893](https://uf-share-file.oss-cn-shenzhen.aliyuncs.com/md-file/image-20200113135808893.png)





## 四、弹窗

要求：参考element-ui；

### 1.系统提示弹窗 

​	**成功**

![img](https://uf-share-file.oss-cn-shenzhen.aliyuncs.com/md-file/1581498765.jpg)

​	**报错**

![img](https://uf-share-file.oss-cn-shenzhen.aliyuncs.com/md-file/1581498832.jpg)

### **2.操作确认提示弹窗(所有删除操作**）

![img](https://uf-share-file.oss-cn-shenzhen.aliyuncs.com/md-file/1581498646.jpg)

 

### 3.新增表单弹窗

​	**表单验证**

​	**在防止用户犯错的前提下，尽可能让用户更早地发现并纠正错误**。

![image-20200113140701576](https://uf-share-file.oss-cn-shenzhen.aliyuncs.com/md-file/image-20200113140701576.png)





## 五、 文字标题 

### 1.文字色号 

![image-20200113140955260](https://uf-share-file.oss-cn-shenzhen.aliyuncs.com/md-file/image-20200113140955260.png)

### 2.文字字号 

![image-20200113141059531](https://uf-share-file.oss-cn-shenzhen.aliyuncs.com/md-file/image-20200113141059531.png)

### 3.文字字体 

![image-20200113141149453](https://uf-share-file.oss-cn-shenzhen.aliyuncs.com/md-file/image-20200113141149453.png)





## 六、分页

**要求： 总计、输入页码、跳转页码、上一页、下一页、每页条数选择**。 

![image-20200113160330744](https://uf-share-file.oss-cn-shenzhen.aliyuncs.com/md-file/image-20200113160330744.png)

**代码：**

​	![image-20200113160553530](https://uf-share-file.oss-cn-shenzhen.aliyuncs.com/md-file/image-20200113160553530.png)