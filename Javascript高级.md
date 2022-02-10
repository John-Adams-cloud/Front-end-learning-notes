<a name="NJqlL"></a>
# this指向问题
<a name="ujiyP"></a>
## this的作用
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641626710715-c021e6fa-bb0e-44e8-8bf7-890d51c377fb.png#clientId=u4c4be185-8406-4&from=paste&height=423&id=u7bbda83b&margin=%5Bobject%20Object%5D&name=image.png&originHeight=845&originWidth=1574&originalType=binary&ratio=1&size=508569&status=done&style=none&taskId=u85cc7976-8d00-4c70-83ec-ba4540e0905&width=787)<br />this可以使写代码更加方便，高效
<a name="b9bJ8"></a>
## 全局作用域
一般很少再全局使用，一般this再函数中使用<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641626861608-ff2e5344-589e-431c-89e8-256da4cc7a88.png#clientId=u4c4be185-8406-4&from=paste&height=394&id=u6c382224&margin=%5Bobject%20Object%5D&name=image.png&originHeight=787&originWidth=1340&originalType=binary&ratio=1&size=236388&status=done&style=none&taskId=u2d6b3b41-f1b2-4fd3-bfd3-13875ae1fa0&width=670)<br />浏览器：全局作用域下this指向window（globalObject）<br />Node环境下：全局作用域下this指向空对象{}<br />以下是node执行文件的过程，将文件当成一个模块<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641627100108-48a58d41-7cec-47c8-ba2c-6dee8ec2a629.png#clientId=u4c4be185-8406-4&from=paste&height=51&id=ueaa71caa&margin=%5Bobject%20Object%5D&name=image.png&originHeight=102&originWidth=587&originalType=binary&ratio=1&size=49856&status=done&style=none&taskId=ue4f58667-cf1d-4e72-9df1-ea2ac699bf8&width=293.5)<br />最后通过apply绑定一个空对象，因此this指向空对象
<a name="ZSJ9T"></a>
## 四大规则
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641627639046-fd4c963a-fdaa-4ea5-9c7c-698e70b31687.png#clientId=u796dd4a7-f6fa-4&from=paste&id=u9e6f1b96&margin=%5Bobject%20Object%5D&name=image.png&originHeight=658&originWidth=1160&originalType=binary&ratio=1&size=252209&status=done&style=none&taskId=u8f80001a-bf95-40a9-8c46-1601f7f806c)
<a name="ViZfk"></a>
#### 规则一：默认绑定（自执行函数）
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641627668533-5660d5a5-261f-45d1-b9a3-e250369539cd.png#clientId=u796dd4a7-f6fa-4&from=paste&id=u0d3eec8e&margin=%5Bobject%20Object%5D&name=image.png&originHeight=651&originWidth=1154&originalType=binary&ratio=1&size=254264&status=done&style=none&taskId=u558d09b9-823a-4a80-95b1-f40aad886ca)
<a name="Ct1TA"></a>
#### 规则二：隐式绑定
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641628228286-3219779d-8f1e-4f82-9061-4de9315a29cd.png#clientId=u796dd4a7-f6fa-4&from=paste&id=ua5049485&margin=%5Bobject%20Object%5D&name=image.png&originHeight=663&originWidth=1157&originalType=binary&ratio=1&size=288406&status=done&style=none&taskId=ua5ab6ca6-a214-444d-b731-296ad6de00b)<br />用对象主题进行调用的时候该对象会被js引擎绑定到该函数执行上下文中的this里面
<a name="DSUS6"></a>
#### 规则三：显示绑定
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641629621061-f4fdfeae-f797-4232-8eb9-7b92208bee6b.png#clientId=u796dd4a7-f6fa-4&from=paste&id=u891131a1&margin=%5Bobject%20Object%5D&name=image.png&originHeight=655&originWidth=1166&originalType=binary&ratio=1&size=206161&status=done&style=none&taskId=uc5ac0770-268c-40c1-ba8c-683df0557e7)<br />call和apply传参区别：<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641630081488-3d020c3e-4176-4182-9878-0640fe2c420b.png#clientId=u796dd4a7-f6fa-4&from=paste&height=34&id=u7476705f&margin=%5Bobject%20Object%5D&name=image.png&originHeight=68&originWidth=326&originalType=binary&ratio=1&size=26618&status=done&style=none&taskId=ue146cfd7-0872-495c-983d-36901bda322&width=163)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641630294175-09fb70df-7175-41e5-b01c-bc87e82d2b38.png#clientId=u796dd4a7-f6fa-4&from=paste&height=325&id=ua4770c43&margin=%5Bobject%20Object%5D&name=image.png&originHeight=650&originWidth=976&originalType=binary&ratio=1&size=158371&status=done&style=none&taskId=ubeb7da54-52f5-4e91-bc5e-ad8bce9ee4e&width=488)<br />用bind绑定再独立调用新函数相当于是**默认绑定和显式绑定冲突**，显式的优先级更高，因此this指向的是bind传入的对象
<a name="eKnfe"></a>
#### 规则四：new绑定
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641630753781-dbe780bd-a7e1-408b-8350-d7918e6f27c6.png#clientId=u796dd4a7-f6fa-4&from=paste&height=328&id=u0e30da48&margin=%5Bobject%20Object%5D&name=image.png&originHeight=655&originWidth=994&originalType=binary&ratio=1&size=185756&status=done&style=none&taskId=u08aa06e1-10b6-4100-bb38-3fdbd4423f6&width=497)
<a name="uiXQh"></a>
## 规则优先级
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641643288990-9859cd6b-cd9c-4cb1-a51a-e6f03c3cebea.png#clientId=u941bd60e-02a1-4&from=paste&height=331&id=u0c0304ce&margin=%5Bobject%20Object%5D&name=image.png&originHeight=662&originWidth=1167&originalType=binary&ratio=1&size=162304&status=done&style=none&taskId=ua44b9571-b7b5-4cb4-a7ad-bf163ddcb4a&width=583.5)
<a name="LcqTu"></a>
#### 显式高于隐式
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641643768267-ba712c68-e4de-490e-97d9-73870f0d81d7.png#clientId=u941bd60e-02a1-4&from=paste&height=43&id=u3f7820a6&margin=%5Bobject%20Object%5D&name=image.png&originHeight=86&originWidth=359&originalType=binary&ratio=1&size=33596&status=done&style=none&taskId=u745bc530-29d9-4872-aea1-abf6e2a0b9c&width=179.5)<br />以下不能体现，因为是在函数执行之前绑定的，而this的调用是在函数的执行时决定的，即使最终结果为绑定到cba，也不能说明bind的优先级高于隐式（obj）<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641643781338-f31f0589-1e8a-43c3-b514-27b0bf5d8b34.png#clientId=u941bd60e-02a1-4&from=paste&height=45&id=u0c7d057b&margin=%5Bobject%20Object%5D&name=image.png&originHeight=89&originWidth=302&originalType=binary&ratio=1&size=23218&status=done&style=none&taskId=uabeb4063-6241-4ff5-8d5c-d87f317c18e&width=151)<br />能证明bind优先级比隐式高如下<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641644000530-d8b9a848-8dbe-42dd-bf65-22dab28dd55a.png#clientId=u941bd60e-02a1-4&from=paste&height=140&id=u7c466452&margin=%5Bobject%20Object%5D&name=image.png&originHeight=280&originWidth=263&originalType=binary&ratio=1&size=49090&status=done&style=none&taskId=u8c86fefa-e27b-4f35-b66a-9345c71df23&width=131.5)
<a name="bP5dG"></a>
## 内置/第三方库函数的绑定
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641642740810-344edf96-8cb6-49bc-a697-10e1b76f173f.png#clientId=u941bd60e-02a1-4&from=paste&height=332&id=u901760af&margin=%5Bobject%20Object%5D&name=image.png&originHeight=664&originWidth=1177&originalType=binary&ratio=1&size=362518&status=done&style=none&taskId=ucf95635a-ad70-4fa4-8724-bd98f2d21c4&width=588.5)
<a name="aQKA6"></a>
## 特殊规则
<a name="FiIOl"></a>
### 忽略显示绑定
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641644663099-ea527f11-0648-4d23-a587-2becf725c501.png#clientId=u37aeeb32-bc70-4&from=paste&height=315&id=u6c4394f0&margin=%5Bobject%20Object%5D&name=image.png&originHeight=630&originWidth=1183&originalType=binary&ratio=1&size=179303&status=done&style=none&taskId=u24cdf7c7-1b2d-454c-b25f-09e23f0685c&width=591.5)
<a name="tWAzc"></a>
### 间接函数引用
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641644962600-ab2b2cb8-53e1-46d6-8cf6-14e6b16db411.png#clientId=u37aeeb32-bc70-4&from=paste&height=321&id=uec934e82&margin=%5Bobject%20Object%5D&name=image.png&originHeight=642&originWidth=911&originalType=binary&ratio=1&size=150046&status=done&style=none&taskId=u5b97bb81-014d-489c-b907-efb6dc5fff6&width=455.5)<br />间接函数引用必须是小括号里面有赋值表达式<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641710714619-fd7ddbc4-9974-41c6-9659-f66a847bc887.png#clientId=u5d094b0d-00a7-4&from=paste&height=25&id=u2ae7b7fb&margin=%5Bobject%20Object%5D&name=image.png&originHeight=50&originWidth=550&originalType=binary&ratio=1&size=35907&status=done&style=none&taskId=u2724adea-b233-4122-8b4c-33aa842059f&width=275)<br />区别于只有小括号，没有赋值表达式
<a name="nGNHO"></a>
### 箭头函数
<a name="yBDKm"></a>
#### 基本
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641646477448-a4cd7e5c-0519-484e-8f92-39ccb943a281.png#clientId=udfa02d16-2aeb-4&from=paste&height=282&id=u6f74d2e1&margin=%5Bobject%20Object%5D&name=image.png&originHeight=563&originWidth=887&originalType=binary&ratio=1&size=178406&status=done&style=none&taskId=u5fc26b5d-2538-4521-9914-329341fe469&width=443.5)
<a name="HAYmq"></a>
#### 简写注意
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641646542293-44c8a3ea-6371-47da-8c14-472d5fa50258.png#clientId=udfa02d16-2aeb-4&from=paste&height=318&id=u0f9da228&margin=%5Bobject%20Object%5D&name=image.png&originHeight=636&originWidth=923&originalType=binary&ratio=1&size=252439&status=done&style=none&taskId=u8ea83def-bad3-4a48-aa81-81233cf1442&width=461.5)
<a name="HimQP"></a>
#### this
<a name="kMmDw"></a>
##### ![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641645140429-4b08b2ac-74a4-4b65-b0a0-c2b2a9585016.png#clientId=u37aeeb32-bc70-4&from=paste&height=333&id=u042528ac&margin=%5Bobject%20Object%5D&name=image.png&originHeight=666&originWidth=1168&originalType=binary&ratio=1&size=188781&status=done&style=none&taskId=uf2d09c10-799e-4447-8772-88a4c05042a&width=584)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641647136887-094dd11a-14f9-4c10-bd5c-b2eca5d49951.png#clientId=udfa02d16-2aeb-4&from=paste&height=327&id=uaf5fb7e8&margin=%5Bobject%20Object%5D&name=image.png&originHeight=654&originWidth=1161&originalType=binary&ratio=1&size=263319&status=done&style=none&taskId=ubc636381-4da1-4147-b673-ecc123259ff&width=580.5)
<a name="Td5Iv"></a>
# call apply bind的实现
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641714986335-150c7ecc-6492-4d7b-a5de-bf48dc283452.png#clientId=ub4018114-c052-4&from=paste&height=402&id=u17bc2a66&margin=%5Bobject%20Object%5D&name=image.png&originHeight=804&originWidth=1485&originalType=binary&ratio=1&size=507857&status=done&style=none&taskId=ub52ae996-1df7-42ad-af3d-41526873c4d&width=742.5)
<a name="b0eHD"></a>
## 原理
**call apply bind的核心思想是利用隐式绑定的特性**<br />apply函数需要另外加条件判断，因为不传参数的话默认是undefined，不可以对undefined进行展开运算符<br />bind函数的实现需要返回一个代理函数（实质作用是运行原来要执行的函数），此外，还需要对参数进行拼接
<a name="zI3Ky"></a>
# arguments
<a name="hoqTU"></a>
## 基本
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641716049227-c4ccbba7-df0a-4714-b0bc-62ab3d9a438b.png#clientId=ub4018114-c052-4&from=paste&height=400&id=u71ef7d93&margin=%5Bobject%20Object%5D&name=image.png&originHeight=799&originWidth=1462&originalType=binary&ratio=1&size=359464&status=done&style=none&taskId=u94162b78-83f2-46a9-897c-c12f3f25345&width=731)<br />arguments类数组对象是保存到函数ao对象中的<br />callee获取当前arguments所在的函数<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641716408769-dbc964fa-ac84-4d59-b084-0eb9db649ba6.png#clientId=ub4018114-c052-4&from=paste&height=29&id=u987695f9&margin=%5Bobject%20Object%5D&name=image.png&originHeight=57&originWidth=388&originalType=binary&ratio=1&size=23436&status=done&style=none&taskId=u7e476cde-2711-4ab3-baef-5417b931983&width=194)
<a name="MfoNo"></a>
## arguments转数组的三种方法
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641716466889-e761cf56-8070-488d-ae12-941eedd1e67a.png#clientId=ub4018114-c052-4&from=paste&height=405&id=ud6dc7dc0&margin=%5Bobject%20Object%5D&name=image.png&originHeight=809&originWidth=1285&originalType=binary&ratio=1&size=393870&status=done&style=none&taskId=u2791aac7-408b-4425-b36a-cfc25f15343&width=642.5)<br />方法一：手动遍历<br />方法二：利用slice方法（本质上slice内部对传入的this也会进行遍历）如下<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641717309407-e0b79315-f508-4821-bf19-65ee5fdb7038.png#clientId=ub4018114-c052-4&from=paste&id=uc3feea50&margin=%5Bobject%20Object%5D&name=image.png&originHeight=355&originWidth=715&originalType=binary&ratio=1&size=141957&status=done&style=none&taskId=uc6287e2b-c31d-4df0-9f27-be2512dcb42)<br />利用空数组进行显式绑定也是可以的<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641717539734-54ee0141-1268-4f88-a3eb-be6644b8123a.png#clientId=uf97c8e1e-f566-4&from=paste&height=31&id=u7d1b194e&margin=%5Bobject%20Object%5D&name=image.png&originHeight=61&originWidth=384&originalType=binary&ratio=1&size=26982&status=done&style=none&taskId=uc2e0de1a-8dac-4be5-bece-0fb3e2aa0c6&width=192)<br />方法三：ES6的from
<a name="upEzg"></a>
## 箭头函数不绑定arguments
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641717810068-797f240d-393f-4348-9c9d-527311f33597.png#clientId=uf97c8e1e-f566-4&from=paste&height=388&id=u377a4e97&margin=%5Bobject%20Object%5D&name=image.png&originHeight=776&originWidth=1323&originalType=binary&ratio=1&size=268164&status=done&style=none&taskId=u6e25ef31-38eb-4dcc-b048-03b9001c175&width=661.5)<br />浏览器全局作用域没有arguments<br />Node环境下有arguments，因为js文件当成模块解析后，通过call绑定对象后，还会将一系列的参数放到全局的arguments中去<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641717911954-8fbe9d30-77bb-4832-b34f-602926c18e2f.png#clientId=uf97c8e1e-f566-4&from=paste&height=32&id=ZxOUl&margin=%5Bobject%20Object%5D&name=image.png&originHeight=63&originWidth=318&originalType=binary&ratio=1&size=23646&status=done&style=none&taskId=ud130c70a-fdc0-400d-8a6a-3170007d6d3&width=159)<br />

<a name="rx1v0"></a>
# 函数式编程
<a name="wlXoG"></a>
## 纯函数
<a name="HWxIV"></a>
### 基本
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641718144616-8e37cdb5-0b16-4ae1-b0c6-7ec1771aa141.png#clientId=uf97c8e1e-f566-4&from=paste&height=382&id=u7b159afe&margin=%5Bobject%20Object%5D&name=image.png&originHeight=763&originWidth=1401&originalType=binary&ratio=1&size=275212&status=done&style=none&taskId=ufe7c08a7-d68d-45b4-8cc1-9214045b6ce&width=700.5)
<a name="StwvX"></a>
### 案例
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641724474227-f99ffed7-4096-4a7f-a30d-8238123524e0.png#clientId=uf97c8e1e-f566-4&from=paste&id=xDFdk&margin=%5Bobject%20Object%5D&name=image.png&originHeight=757&originWidth=1195&originalType=binary&ratio=1&size=321989&status=done&style=none&taskId=uddf72753-9eda-49dd-8be7-3d78c0e9931)
<a name="EOND8"></a>
### 优势
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641724806334-2891e9f8-734f-4447-a11f-93e5321c6aeb.png#clientId=ubb6342de-a47c-4&from=paste&height=344&id=I9PIk&margin=%5Bobject%20Object%5D&name=image.png&originHeight=688&originWidth=1376&originalType=binary&ratio=1&size=237403&status=done&style=none&taskId=u5dad02cf-c880-497b-8f60-c41751f6c9b&width=688)
<a name="vYsZX"></a>
### 副作用
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641719379720-40c1e85b-6883-4193-85f1-8b878ba6c953.png#clientId=uf97c8e1e-f566-4&from=paste&height=295&id=u22825ea8&margin=%5Bobject%20Object%5D&name=image.png&originHeight=590&originWidth=1379&originalType=binary&ratio=1&size=157150&status=done&style=none&taskId=u0dad3039-f22c-4418-855b-81bf675b670&width=689.5)<br />
<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641724342227-2e7598d3-894d-45fd-a9e2-2f7ee1958ee4.png#clientId=uf97c8e1e-f566-4&from=paste&height=81&id=ue47a1b49&margin=%5Bobject%20Object%5D&name=image.png&originHeight=161&originWidth=341&originalType=binary&ratio=1&size=34005&status=done&style=none&taskId=ue07c79f5-8668-4e1d-aed3-a1cb523f375&width=170.5)<br />以上也是纯函数，因为确定输入产生确定输出，而且展开运算符相当于一个拷贝操作，并没有产生副作用
<a name="Pmb16"></a>
## 柯里化
<a name="Do9JJ"></a>
### 基本
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641725181490-d7fac223-de39-4b9e-a5a5-1d9d7c7c3f06.png#clientId=ubb6342de-a47c-4&from=paste&height=370&id=u69153df7&margin=%5Bobject%20Object%5D&name=image.png&originHeight=740&originWidth=1325&originalType=binary&ratio=1&size=192106&status=done&style=none&taskId=u9b7e7ebb-46ec-4189-8a64-cf861caa445&width=662.5)
<a name="VszSe"></a>
### 结构
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641725492743-c9f2ce57-5f0e-49e5-aecc-9756351a0b63.png#clientId=ubb6342de-a47c-4&from=paste&height=387&id=u797f4924&margin=%5Bobject%20Object%5D&name=image.png&originHeight=774&originWidth=1395&originalType=binary&ratio=1&size=309557&status=done&style=none&taskId=u0a05b6a7-9b0c-4e97-b57f-ae1de694f83&width=697.5)
<a name="d2mmg"></a>
### 作用
<a name="HBxvr"></a>
#### 单一职责
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641725515384-9a5c6883-1467-4a1a-81a3-86162a5c873e.png#clientId=ubb6342de-a47c-4&from=paste&height=377&id=ufde94917&margin=%5Bobject%20Object%5D&name=image.png&originHeight=754&originWidth=1387&originalType=binary&ratio=1&size=240573&status=done&style=none&taskId=u0c4dd5bc-bc49-4102-9fde-341adc57eaa&width=693.5)
<a name="ePl79"></a>
#### 复用
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641725905271-0e88d944-ffc9-4d4b-ade4-db72c716ba60.png#clientId=ubb6342de-a47c-4&from=paste&height=377&id=ubab5ee06&margin=%5Bobject%20Object%5D&name=image.png&originHeight=753&originWidth=1364&originalType=binary&ratio=1&size=284484&status=done&style=none&taskId=uf2c95d39-5025-4a02-ba9f-b59f79afded&width=682)
<a name="WsTZO"></a>
##### 案例
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641726253050-a69f1897-6ef8-4f76-87d8-82ddaeffc440.png#clientId=ubb6342de-a47c-4&from=paste&height=375&id=ua31f2bac&margin=%5Bobject%20Object%5D&name=image.png&originHeight=750&originWidth=1152&originalType=binary&ratio=1&size=327031&status=done&style=none&taskId=ud5602261-377b-414a-b3c7-f9faf0e0db0&width=576)
<a name="FU3Mv"></a>
### 自动柯里化函数（难点）
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641728882182-a7380b98-9896-4f16-99a6-cd48bb8ed6d6.png#clientId=ubb6342de-a47c-4&from=paste&height=347&id=u07207933&margin=%5Bobject%20Object%5D&name=image.png&originHeight=694&originWidth=1008&originalType=binary&ratio=1&size=291093&status=done&style=none&taskId=u3907f7d9-60ce-4900-873a-7750e1ea6ca&width=504)
<a name="biM9k"></a>
## 组合函数
<a name="gEjEI"></a>
### 基本
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641729761914-9bc40dee-8eea-4fdd-9bff-7173eb9c4a64.png#clientId=ubb6342de-a47c-4&from=paste&height=389&id=u86b897e7&margin=%5Bobject%20Object%5D&name=image.png&originHeight=777&originWidth=1369&originalType=binary&ratio=1&size=350726&status=done&style=none&taskId=u4eccd7f9-fa42-4cb5-a2f4-99e4caf3976&width=684.5)<br />

<a name="FkrTq"></a>
### 较复杂的组合函数的实现
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641734535768-c2864f7b-b456-40a4-b4c9-10d903242aac.png#clientId=u220a0edf-8590-4&from=paste&height=407&id=u0f3374cf&margin=%5Bobject%20Object%5D&name=image.png&originHeight=814&originWidth=1401&originalType=binary&ratio=1&size=312329&status=done&style=none&taskId=u6beafbfe-905b-42ed-af8d-dee1e9f42f4&width=700.5)
<a name="hGm88"></a>
# with
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641797158009-01cbc807-5a9b-4e4b-a0ce-6bb449ad237a.png#clientId=ud4856636-c809-4&from=paste&height=358&id=u3eff398e&margin=%5Bobject%20Object%5D&name=image.png&originHeight=715&originWidth=1075&originalType=binary&ratio=1&size=198245&status=done&style=none&taskId=u1d01f588-70d2-4dd7-9ceb-9ccf8f8ad8a&width=537.5)
<a name="xA5C9"></a>
# eval函数
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641797210039-b58f0471-5af0-4535-afa4-26a0794b7f87.png#clientId=ud4856636-c809-4&from=paste&height=357&id=u4b0ae001&margin=%5Bobject%20Object%5D&name=image.png&originHeight=714&originWidth=1371&originalType=binary&ratio=1&size=261911&status=done&style=none&taskId=u1472e07b-159e-4e56-b9db-dda6de154d9&width=685.5)
<a name="dFydq"></a>
# 严格模式
<a name="UMMDO"></a>
## 基本
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641797556264-d278b0e4-ff1d-418b-b7f3-54da40e61c3c.png#clientId=ud4856636-c809-4&from=paste&id=u6e419c50&margin=%5Bobject%20Object%5D&name=image.png&originHeight=611&originWidth=1562&originalType=binary&ratio=1&size=224472&status=done&style=none&taskId=u2a4cee27-7b19-4c8a-a564-a16dc9521fc)<br />静默错误：错误的代码但是没有造成很严重的影响
<a name="NxqGx"></a>
## 开启
很多打包工具如webpack都会在打包后默认给文件加上严格模式，各个文件不需要手动加上<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641798004131-db074814-1a81-467f-8fb9-a66e7fc43dea.png#clientId=u88b9a424-b00f-4&from=paste&height=402&id=u36112ff4&margin=%5Bobject%20Object%5D&name=image.png&originHeight=804&originWidth=1203&originalType=binary&ratio=1&size=323666&status=done&style=none&taskId=ub786b65c-800d-436c-ac9b-811fe7c2cf7&width=601.5)
<a name="FuhFo"></a>
## 限制
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641798058866-da5a0138-7546-4b9d-b1ee-7f27ae204a0a.png#clientId=u88b9a424-b00f-4&from=paste&height=405&id=u4001449c&margin=%5Bobject%20Object%5D&name=image.png&originHeight=809&originWidth=1396&originalType=binary&ratio=1&size=236433&status=done&style=none&taskId=u933f5d9e-07ed-4e1f-8b99-7eb2d7abefa&width=698)
<a name="dOrcH"></a>
###  无法意外的创建全局变量  
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641798224066-20e1f93e-731c-45d4-a728-097d907ec842.png#clientId=u88b9a424-b00f-4&from=paste&height=14&id=u6477b4c4&margin=%5Bobject%20Object%5D&name=image.png&originHeight=27&originWidth=110&originalType=binary&ratio=1&size=4631&status=done&style=none&taskId=u3edddf76-90ba-4add-88b9-06397e2f120&width=55)<br />直接赋值
<a name="dNwRa"></a>
###  式不允许函数参数有相同的名称  
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641798265617-17bd4fd0-1453-4c33-a21b-123aa35bc039.png#clientId=u88b9a424-b00f-4&from=paste&height=68&id=ueb264629&margin=%5Bobject%20Object%5D&name=image.png&originHeight=135&originWidth=280&originalType=binary&ratio=1&size=28166&status=done&style=none&taskId=u879a94ef-08b9-4780-9656-cafda6eab6e&width=140)
<a name="vKhvy"></a>
###  不允许0的八进制语法  
不允许0开头 0o可以 0x可以<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641798471719-306a0722-6d76-4961-9010-1faf3886c2a8.png#clientId=u88b9a424-b00f-4&from=paste&height=40&id=ud196c435&margin=%5Bobject%20Object%5D&name=image.png&originHeight=79&originWidth=367&originalType=binary&ratio=1&size=28953&status=done&style=none&taskId=u8551ef44-40f8-428f-abaa-41b65684a0f&width=183.5)
<a name="spYkI"></a>
###  eval不再为上层引用变量
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641798709414-2bf3b125-e102-479e-9858-bb0927e10725.png#clientId=u88b9a424-b00f-4&from=paste&height=50&id=u207640ce&margin=%5Bobject%20Object%5D&name=image.png&originHeight=99&originWidth=794&originalType=binary&ratio=1&size=48850&status=done&style=none&taskId=ub438961c-4177-4a67-9b20-80f4c95354c&width=397)<br />意思是不会给全局添加变量 因此只能打印一次
<a name="p1jAo"></a>
###  严格模式下，this绑定不会默认转成对象
自执行函数（默认绑定）不会指向window，而是指向undefined<br />对原来代码不会有太大影响，因为我们一般不会直接通过this去调用window<br />注意：settimeout里面的普通函数，在严格模式/非严格模式下它的指向都是window（而不会变成undefined）
<a name="QeSQp"></a>
# 面向对象
<a name="XLRKJ"></a>
## 基本
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641799863285-f3cd92cf-3c66-442e-998c-e81561d2fcbd.png#clientId=u88b9a424-b00f-4&from=paste&height=287&id=u0736ffcd&margin=%5Bobject%20Object%5D&name=image.png&originHeight=574&originWidth=1449&originalType=binary&ratio=1&size=186408&status=done&style=none&taskId=ue8252fa2-216f-40a1-bd84-08f81e6b0ce&width=724.5)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641800471754-0a45eb96-8267-4235-bbc3-239e4ef97f91.png#clientId=u88b9a424-b00f-4&from=paste&height=385&id=ue8a9359e&margin=%5Bobject%20Object%5D&name=image.png&originHeight=770&originWidth=1500&originalType=binary&ratio=1&size=272940&status=done&style=none&taskId=ua9610c17-cd1c-41f7-89d8-2b0a69573eb&width=750)<br />

<a name="rIl4F"></a>
## 创建对象
<a name="uaoHv"></a>
### 基本
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641800494644-3e168ebf-d4de-4c5f-910f-c25f0e880667.png#clientId=u88b9a424-b00f-4&from=paste&height=326&id=uc3012bbe&margin=%5Bobject%20Object%5D&name=image.png&originHeight=651&originWidth=1326&originalType=binary&ratio=1&size=382099&status=done&style=none&taskId=u5d49fdc4-9511-45a2-8107-0c92ab929fb&width=663)
<a name="jrA7L"></a>
## 创建多个对象的方案
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641812743307-ed85d6f1-22c2-4256-9cab-781453f97a39.png#clientId=u88b9a424-b00f-4&from=paste&height=357&id=u912e93b5&margin=%5Bobject%20Object%5D&name=image.png&originHeight=713&originWidth=1014&originalType=binary&ratio=1&size=291694&status=done&style=none&taskId=u17de0dc5-d066-4bd9-b7bb-a4f10c9403b&width=507)
<a name="k2L4I"></a>
### 工厂模式
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641812883533-e6e6f573-f8e1-454e-ac70-722009100149.png#clientId=u88b9a424-b00f-4&from=paste&height=363&id=ud7f7adbb&margin=%5Bobject%20Object%5D&name=image.png&originHeight=726&originWidth=1229&originalType=binary&ratio=1&size=365879&status=done&style=none&taskId=u99d38b8a-a8aa-4b5d-8081-5e55923333d&width=614.5)
<a name="EaflZ"></a>
### 构造函数
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641812983731-4f65b2b7-2e28-4d13-9d2d-6e962b63da8e.png#clientId=u88b9a424-b00f-4&from=paste&height=357&id=ud67bf634&margin=%5Bobject%20Object%5D&name=image.png&originHeight=714&originWidth=1200&originalType=binary&ratio=1&size=239311&status=done&style=none&taskId=u476734b8-eecb-4f6a-bafa-fbb049aa5a8&width=600)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641813001545-834aebe3-a721-4e03-a1fa-88c188c2e95d.png#clientId=u88b9a424-b00f-4&from=paste&height=371&id=u31c7cfca&margin=%5Bobject%20Object%5D&name=image.png&originHeight=741&originWidth=1300&originalType=binary&ratio=1&size=223930&status=done&style=none&taskId=u6c4bc410-4aeb-4427-9264-bc5474720f5&width=650)<br />new一个函数后产生对象的隐式原型指向构造函数的显式原型<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641813096864-08b27307-fe3d-4794-999b-6d557d109a1c.png#clientId=u88b9a424-b00f-4&from=paste&height=358&id=u5c826270&margin=%5Bobject%20Object%5D&name=image.png&originHeight=715&originWidth=1280&originalType=binary&ratio=1&size=286813&status=done&style=none&taskId=u6dd082a4-b780-4038-8fc4-a5ff44f347f&width=640)<br />约定的一般规范：构造函数的函数名一般为大写
<a name="nksW0"></a>
### 构造函数和原型结合
<a name="pRByc"></a>
#### 对象原型（隐式原型）
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641815778848-10411f8b-7c6c-4b4a-ba25-acb6c32b5d59.png#clientId=u88b9a424-b00f-4&from=paste&height=351&id=u859763e0&margin=%5Bobject%20Object%5D&name=image.png&originHeight=701&originWidth=1286&originalType=binary&ratio=1&size=236272&status=done&style=none&taskId=u0da1b77b-b77f-4b7a-94ed-bb1444b4c77&width=643)
<a name="yJVUK"></a>
#### 显式原型
因为函数本身也是一个对象，因此函数有隐式原型，但是因为函数是一个函数，因此还有显式原型<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641815866350-aae65086-906f-473f-989e-e6546116f991.png#clientId=u88b9a424-b00f-4&from=paste&height=367&id=udd3a3a09&margin=%5Bobject%20Object%5D&name=image.png&originHeight=733&originWidth=1042&originalType=binary&ratio=1&size=255294&status=done&style=none&taskId=u78232f87-2794-43e6-81fa-657d95c5d1d&width=521)<br />全局声明一个函数产生一个函数ao对象，被go（全局对象）引用，ao对象里面有prototype（显式原型），parentscope（父级作用域），函数执行体等等<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641820488906-ae9ae79f-fc14-4c9c-9af1-e18d923bbe0e.png#clientId=u88b9a424-b00f-4&from=paste&height=47&id=uf4b187a0&margin=%5Bobject%20Object%5D&name=image.png&originHeight=93&originWidth=197&originalType=binary&ratio=1&size=15057&status=done&style=none&taskId=u30f05b87-746b-4f52-80d3-705241777a3&width=98.5)
<a name="LVwEX"></a>
#### new操作符
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641817303810-9b7f958b-3b7b-4060-84a6-de695b4c6bba.png#clientId=u88b9a424-b00f-4&from=paste&height=346&id=ud102ad08&margin=%5Bobject%20Object%5D&name=image.png&originHeight=692&originWidth=1288&originalType=binary&ratio=1&size=349216&status=done&style=none&taskId=u19124138-d4e4-463f-9137-8ab0a2e8945&width=644)<br />new一个函数后产生对象的隐式原型指向构造函数的显式原型
<a name="USIRV"></a>
#### constructor
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641818756836-4d7432eb-82d7-4d18-b73b-ae9212e52367.png#clientId=u88b9a424-b00f-4&from=paste&height=269&id=u4b7e6e02&margin=%5Bobject%20Object%5D&name=image.png&originHeight=538&originWidth=1217&originalType=binary&ratio=1&size=207287&status=done&style=none&taskId=u577fa095-77a1-4037-baf7-82ed094f4f5&width=608.5)<br />

<a name="Oa71h"></a>
#### 重写原型对象
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641818339371-a7f0d9bc-f382-4f7f-9529-f25b0baf76a9.png#clientId=u88b9a424-b00f-4&from=paste&height=343&id=u5301d3e8&margin=%5Bobject%20Object%5D&name=image.png&originHeight=685&originWidth=1293&originalType=binary&ratio=1&size=248533&status=done&style=none&taskId=u2c8d0cf1-3cbf-4d48-95f0-5783af278ff&width=646.5)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641818789964-80e1c2bd-4099-4a9b-9b25-37194bdce392.png#clientId=u88b9a424-b00f-4&from=paste&height=341&id=u041403c0&margin=%5Bobject%20Object%5D&name=image.png&originHeight=682&originWidth=1288&originalType=binary&ratio=1&size=290156&status=done&style=none&taskId=uda7dd3e7-3e48-43bd-9d72-0e3042ec02b&width=644)
<a name="PoNXy"></a>
#### 构造函数和原型结合的最终方案
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641818829885-26a43373-40ae-483d-88b2-adfa151091c3.png#clientId=u88b9a424-b00f-4&from=paste&height=361&id=uba8088c7&margin=%5Bobject%20Object%5D&name=image.png&originHeight=722&originWidth=1298&originalType=binary&ratio=1&size=243061&status=done&style=none&taskId=ufffe954b-980b-47f0-87c5-378cbe4974a&width=649)
<a name="tLXia"></a>
##  对属性操作的控制  
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641800572274-3178887f-7b18-4aed-bf02-ba5be2122aa3.png#clientId=u88b9a424-b00f-4&from=paste&height=388&id=uac1192da&margin=%5Bobject%20Object%5D&name=image.png&originHeight=775&originWidth=1449&originalType=binary&ratio=1&size=279356&status=done&style=none&taskId=u8b75a7ae-96ec-4d7d-88c3-bb3d7b5e982&width=724.5)
<a name="ucmet"></a>
###  Object.defineProperty  
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641800863154-078f59ac-48a7-4e00-97de-874790171be3.png#clientId=u88b9a424-b00f-4&from=paste&height=383&id=ubdb9dbdd&margin=%5Bobject%20Object%5D&name=image.png&originHeight=766&originWidth=1473&originalType=binary&ratio=1&size=158881&status=done&style=none&taskId=u7e0b3cab-5b0c-424e-b728-90d9a9c31f3&width=736.5)<br />此方法会对传入的对象进行修改，因此不是纯函数
<a name="ulIjw"></a>
### 属性描述符
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641801071014-5370c073-ace8-4546-a67e-ea0a8509b116.png#clientId=u88b9a424-b00f-4&from=paste&height=306&id=ue703e61c&margin=%5Bobject%20Object%5D&name=image.png&originHeight=612&originWidth=1097&originalType=binary&ratio=1&size=145780&status=done&style=none&taskId=udef87942-6c76-421e-a14a-e606f09d2cd&width=548.5)
<a name="QP1wL"></a>
#### 数据属性描述符
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641801148464-4a350ed7-38bd-40cd-b0ea-375ca8719956.png#clientId=u88b9a424-b00f-4&from=paste&height=332&id=ubfbdd972&margin=%5Bobject%20Object%5D&name=image.png&originHeight=663&originWidth=1186&originalType=binary&ratio=1&size=328726&status=done&style=none&taskId=ueea5a19e-e60e-4ffb-b4d0-074c5dfbf6b&width=593)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641803332512-bab25576-f66a-414d-9829-59434b364177.png#clientId=u88b9a424-b00f-4&from=paste&height=351&id=u548b48f4&margin=%5Bobject%20Object%5D&name=image.png&originHeight=701&originWidth=1250&originalType=binary&ratio=1&size=375015&status=done&style=none&taskId=u1be362ea-33f9-4d2e-afe2-5f3c1cfc19c&width=625)
<a name="moIln"></a>
####  存取属性描述符  
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641803319300-c22a7d79-70c0-416e-9643-8b0291e9105d.png#clientId=u88b9a424-b00f-4&from=paste&height=338&id=u809dccaa&margin=%5Bobject%20Object%5D&name=image.png&originHeight=676&originWidth=1291&originalType=binary&ratio=1&size=217440&status=done&style=none&taskId=u197023a5-dd24-4a52-b720-bc3cd9f1218&width=645.5)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641803311557-89f81b43-d313-48e9-ba87-a374388c0352.png#clientId=u88b9a424-b00f-4&from=paste&height=358&id=u49649f83&margin=%5Bobject%20Object%5D&name=image.png&originHeight=715&originWidth=700&originalType=binary&ratio=1&size=204860&status=done&style=none&taskId=uf30e7466-c2e9-487a-aa07-be7c123c9f7&width=350)<br />使用场景<br />1.隐藏某个私有属性（例子中的-address)，不希望直接被外界赋值和使用<br />注：js中没有严格定义的私有属性，但社区中逐渐产生一个规范：私有属性的命名前有下划线<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641803668597-d711fcd4-9eb0-4bda-8aff-ab4c2eac7dc0.png#clientId=u88b9a424-b00f-4&from=paste&height=220&id=uf5152fc3&margin=%5Bobject%20Object%5D&name=image.png&originHeight=439&originWidth=441&originalType=binary&ratio=1&size=116198&status=done&style=none&taskId=uac0a150f-9eb7-4d0c-91ae-a218a708f31&width=220.5)<br />2.希望截获一个属性访问和设置的过程，也会使用存储属性描述符(例子：vue2的响应式原理，将遍历所有数据并通过存储属性描述符截获get和set，并收集依赖，在更新时利用get将所有依赖执行一遍）
<a name="Oz44W"></a>
### Object.defineProperties
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641811241768-ad2ea940-d87a-4e5b-bf59-f001ee8fb5e5.png#clientId=u88b9a424-b00f-4&from=paste&height=344&id=u0ac4f12e&margin=%5Bobject%20Object%5D&name=image.png&originHeight=688&originWidth=1247&originalType=binary&ratio=1&size=184364&status=done&style=none&taskId=u6e0ac278-ffa2-4b9d-95c1-147b9687a95&width=623.5)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641811231249-56fd828c-3237-413c-a854-f8785061cdf0.png#clientId=u88b9a424-b00f-4&from=paste&height=140&id=uefe1f64b&margin=%5Bobject%20Object%5D&name=image.png&originHeight=280&originWidth=401&originalType=binary&ratio=1&size=75186&status=done&style=none&taskId=u0d53825f-3343-45a7-b2b8-ea71ce5e52e&width=200.5)![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641811299801-b56f7bb8-09b5-40d6-a16e-64c47427dc69.png#clientId=u88b9a424-b00f-4&from=paste&height=124&id=uba3bd950&margin=%5Bobject%20Object%5D&name=image.png&originHeight=247&originWidth=274&originalType=binary&ratio=1&size=62891&status=done&style=none&taskId=uc4b30803-392a-4779-aeb5-5c4b3130ae1&width=137)<br />以上两种写法都等价<br />获取特定属性的
<a name="HkAk1"></a>
### 其他方法
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641811522416-1872e491-7ee2-40c5-acd9-0f96528cc450.png#clientId=u88b9a424-b00f-4&from=paste&height=355&id=u0219d3c2&margin=%5Bobject%20Object%5D&name=image.png&originHeight=710&originWidth=887&originalType=binary&ratio=1&size=142070&status=done&style=none&taskId=u3182e78e-ab0a-4341-a0d3-5242e406e6a&width=443.5)
<a name="iVKSI"></a>
## 类
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641885007177-0f005a0d-a078-41d8-b76c-ae9a33c504f1.png#clientId=u646c98c3-b256-4&from=paste&height=373&id=uc4a442ce&margin=%5Bobject%20Object%5D&name=image.png&originHeight=746&originWidth=1550&originalType=binary&ratio=1&size=232401&status=done&style=none&taskId=u4a2974e4-28ac-479b-98b1-4c1228f42ad&width=775)
<a name="TEzXy"></a>
## 继承
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641885194925-62544235-2b9b-42e9-8b35-34c26a8903ff.png#clientId=u646c98c3-b256-4&from=paste&height=408&id=u483133c0&margin=%5Bobject%20Object%5D&name=image.png&originHeight=815&originWidth=1550&originalType=binary&ratio=1&size=228862&status=done&style=none&taskId=ud7df3249-07be-42f7-bc70-5a14b06bb3d&width=775)
<a name="MjOtQ"></a>
### 原型链
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641885461264-fcdfa672-cd95-4cd0-9b6e-27c2cca2aad9.png#clientId=u646c98c3-b256-4&from=paste&height=392&id=u9e404723&margin=%5Bobject%20Object%5D&name=image.png&originHeight=783&originWidth=1368&originalType=binary&ratio=1&size=371133&status=done&style=none&taskId=u5aab94bf-fe00-4658-9e75-f6a9e7ce45d&width=684)
<a name="OenBK"></a>
### Object的原型
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641885919502-10976777-e082-4b2c-bd23-7935fb3cadb0.png#clientId=u646c98c3-b256-4&from=paste&id=u8183f673&margin=%5Bobject%20Object%5D&name=image.png&originHeight=715&originWidth=1328&originalType=binary&ratio=1&size=242318&status=done&style=none&taskId=ufcd628d4-8453-428e-95b3-55214d6f710)
<a name="NUznm"></a>
### ![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641888458339-fa86532b-9494-43ef-a8ff-d6b99f2978d7.png#clientId=uce5ac03b-0fe4-4&from=paste&height=349&id=ufa723f1c&margin=%5Bobject%20Object%5D&name=image.png&originHeight=698&originWidth=1489&originalType=binary&ratio=1&size=431043&status=done&style=none&taskId=u7225aad9-2f99-4e4c-849e-57dbc7f0d6a&width=744.5)继承的实现
<a name="OlD9d"></a>
#### 通过原型链实现继承
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641898823563-21d45e2d-88ef-41f8-850d-a582ff5b519d.png#clientId=uce5ac03b-0fe4-4&from=paste&height=398&id=u74d0cd2e&margin=%5Bobject%20Object%5D&name=image.png&originHeight=796&originWidth=1359&originalType=binary&ratio=1&size=463726&status=done&style=none&taskId=u6f6c6141-89f4-4c60-8bf1-32d3ff69fa1&width=679.5)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641898923011-fb419709-96ea-4197-8211-8e99235f610e.png#clientId=uce5ac03b-0fe4-4&from=paste&height=208&id=ufe40ada3&margin=%5Bobject%20Object%5D&name=image.png&originHeight=415&originWidth=1228&originalType=binary&ratio=1&size=119241&status=done&style=none&taskId=ua1509afa-c350-478f-9a4d-0bd25bdf6ed&width=614)<br />第一：因为直接访问属性只能打印当前对象可以枚举的属性，不可以打印出通过原型链继承的属性<br />第二：通过push等方法改变找到继承的原型（会触发getter），并在原型修改属性（引用类型），因此其他对象通过继承这个原型的属性都会发生改变，简单类型的数据一般都是直接赋值，赋值后是直接添加属性在实例中，一般不会影响其他实例<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641899090290-6c48c232-b50d-46ac-88d6-762c53b7ab53.png#clientId=uce5ac03b-0fe4-4&from=paste&height=63&id=u85ba5486&margin=%5Bobject%20Object%5D&name=image.png&originHeight=126&originWidth=273&originalType=binary&ratio=1&size=39084&status=done&style=none&taskId=ub5e85cef-d186-46e8-b3f5-cfa0b655a80&width=136.5)<br />以下方法是直接给现有对象添加了一个新的name属性，不是添加到原型上的，因此其他对象不会受影响<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641899210536-9fb4bc9e-c422-484f-8d48-1b1ea31c734e.png#clientId=uce5ac03b-0fe4-4&from=paste&height=42&id=u38e4f6bc&margin=%5Bobject%20Object%5D&name=image.png&originHeight=84&originWidth=454&originalType=binary&ratio=1&size=33455&status=done&style=none&taskId=u58fbf0ec-3250-43f9-aabb-4145abf13ad&width=227)<br />第三：不能传参数，如果将参数处理逻辑写在子类就违反了继承的目的（逻辑相互分离）
<a name="wzL1R"></a>
#### 组合借用构造函数继承
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641899507849-af5edd00-3c1b-42bc-9f54-34fff790d632.png#clientId=uce5ac03b-0fe4-4&from=paste&height=391&id=u3a7846bf&margin=%5Bobject%20Object%5D&name=image.png&originHeight=781&originWidth=1472&originalType=binary&ratio=1&size=327679&status=done&style=none&taskId=uea4b8b55-4e92-4102-abe4-91bfbf8f586&width=736)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641991094747-de999435-8420-4798-b1bb-c646330df30d.png#clientId=uab34d97d-47be-4&from=paste&height=94&id=ufd3a4344&margin=%5Bobject%20Object%5D&name=image.png&originHeight=187&originWidth=1299&originalType=binary&ratio=1&size=71677&status=done&style=none&taskId=ud0d76e70-c66b-4df5-8d10-504d7c7937a&width=649.5)<br />以上是错误的，因为后续再要为子类加方法，就会给父类添加方法，会直接影响父类<br />以下是借用构造函数继承相对正确的方法<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641990802835-92a773ba-cadf-4c3e-b93f-94884d7678c8.png#clientId=uab34d97d-47be-4&from=paste&height=126&id=ucb10d722&margin=%5Bobject%20Object%5D&name=image.png&originHeight=252&originWidth=522&originalType=binary&ratio=1&size=78321&status=done&style=none&taskId=ua80b69a7-5463-4227-8450-024b49ea667&width=261)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641900049889-642cf8d0-9c1c-4154-8edf-79857a39a79f.png#clientId=uce5ac03b-0fe4-4&from=paste&height=398&id=ua1deb0d7&margin=%5Bobject%20Object%5D&name=image.png&originHeight=795&originWidth=1396&originalType=binary&ratio=1&size=266706&status=done&style=none&taskId=u1d84f943-a800-4388-87e0-eebb3ff38db&width=698)
<a name="rWeqI"></a>
#### 原型式继承
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641991886089-7fd901fe-8ef3-4472-a670-401621333b28.png#clientId=uab34d97d-47be-4&from=paste&height=345&id=uceff4825&margin=%5Bobject%20Object%5D&name=image.png&originHeight=690&originWidth=1394&originalType=binary&ratio=1&size=425911&status=done&style=none&taskId=ue6bda802-e1ea-47f0-9f37-f09f91e8f40&width=697)<br />创建一个子类和父类的中间对象，使该对象指向父类的prototype，而添加属性就添加到这个中间对象本身
<a name="tjAOJ"></a>
#### 寄生式继承函数
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641992786577-4a4fc8cf-8210-4188-8084-97c9e0091aae.png#clientId=uab34d97d-47be-4&from=paste&height=358&id=uddad7740&margin=%5Bobject%20Object%5D&name=image.png&originHeight=716&originWidth=1379&originalType=binary&ratio=1&size=387426&status=done&style=none&taskId=u50d6567f-83b5-4330-bb1d-939fc5c4b70&width=689.5)
<a name="E39mM"></a>
#### 寄生组合式继承函数
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641992968556-ff45823d-515d-49bb-bdd8-286c16472e66.png#clientId=uab34d97d-47be-4&from=paste&height=377&id=uc4aa7823&margin=%5Bobject%20Object%5D&name=image.png&originHeight=753&originWidth=1393&originalType=binary&ratio=1&size=283181&status=done&style=none&taskId=ud58b90d9-fbcc-4731-8fd8-7feca84e048&width=696.5)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641993076503-db213e24-b311-457e-9c09-b1b1ed46f09e.png#clientId=uab34d97d-47be-4&from=paste&height=185&id=ue198ad5f&margin=%5Bobject%20Object%5D&name=image.png&originHeight=369&originWidth=609&originalType=binary&ratio=1&size=150711&status=done&style=none&taskId=u72399cc2-ac48-4b33-acf0-da71613bdb1&width=304.5)
<a name="eTlBx"></a>
## 对象方法的补充
create方法<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641993875163-854bb883-34e9-4e74-a86c-f872feda63b4.png#clientId=uab34d97d-47be-4&from=paste&height=180&id=ue28ab03d&margin=%5Bobject%20Object%5D&name=image.png&originHeight=360&originWidth=375&originalType=binary&ratio=1&size=83136&status=done&style=none&taskId=ueb7c1a10-a10a-4772-a2f8-527a1541616&width=187.5)<br />后面的属性描述符添加到是新对象中，而不是加入到原型中<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641993783343-115233c0-7071-40ed-99fe-b90ccd75671d.png#clientId=uab34d97d-47be-4&from=paste&height=405&id=u53d98d56&margin=%5Bobject%20Object%5D&name=image.png&originHeight=809&originWidth=1175&originalType=binary&ratio=1&size=205187&status=done&style=none&taskId=u09258483-258f-4d7f-a5d1-22f5645f191&width=587.5)
<a name="v9D0u"></a>
## 原型继承关系
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1641994691948-1f66c0ce-9f28-4f96-922e-cb14ad619565.png#clientId=uab34d97d-47be-4&from=paste&height=406&id=uf4fea5c9&margin=%5Bobject%20Object%5D&name=image.png&originHeight=812&originWidth=1464&originalType=binary&ratio=1&size=560312&status=done&style=none&taskId=u6ee85781-69ac-4a09-9b9a-efda9547569&width=732)
<a name="AGsz2"></a>
## ES6的继承
<a name="bGbEm"></a>
### 用class定义类
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642057654148-426dfd80-d83c-4d68-b95d-f5d1a505f585.png#clientId=ua6712525-b4e3-4&from=paste&height=401&id=ua9843c02&margin=%5Bobject%20Object%5D&name=image.png&originHeight=802&originWidth=1538&originalType=binary&ratio=1&size=248863&status=done&style=none&taskId=u198005c9-8c18-4d1c-9832-bfeaea82533&width=769)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642057778778-deb8e378-c665-4eb1-8ef3-ec8f77bfff60.png#clientId=ua6712525-b4e3-4&from=paste&height=367&id=uecf35f7f&margin=%5Bobject%20Object%5D&name=image.png&originHeight=734&originWidth=1028&originalType=binary&ratio=1&size=306700&status=done&style=none&taskId=uda466e44-6856-44b1-ac6e-00e9f676483&width=514)
<a name="EB36S"></a>
### 构造函数
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642057905266-a8c12465-fb62-491a-9add-54e5d2493d45.png#clientId=ua6712525-b4e3-4&from=paste&height=396&id=u589bd1bf&margin=%5Bobject%20Object%5D&name=image.png&originHeight=791&originWidth=1308&originalType=binary&ratio=1&size=267543&status=done&style=none&taskId=uc2d9ee66-19ae-4b03-b955-5220d5d993a&width=654)
<a name="Yjf60"></a>
### 实例方法
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642059154964-f46d64ae-bd4c-4f50-b912-2bb13c2ce1fa.png#clientId=ua6712525-b4e3-4&from=paste&height=408&id=u47a2503a&margin=%5Bobject%20Object%5D&name=image.png&originHeight=816&originWidth=1429&originalType=binary&ratio=1&size=293140&status=done&style=none&taskId=ub43dc915-c2e9-4e72-885c-240abc59fb6&width=714.5)
<a name="MeJrq"></a>
### 访问器方法
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642059176794-27b8a064-ac51-4f9c-878f-8ae8590fb05a.png#clientId=ua6712525-b4e3-4&from=paste&height=406&id=u86eeca2b&margin=%5Bobject%20Object%5D&name=image.png&originHeight=812&originWidth=1390&originalType=binary&ratio=1&size=332872&status=done&style=none&taskId=u05df6675-43d3-4c91-9313-a75276c27cd&width=695)
<a name="Yqyhc"></a>
### 静态方法（类方法）
静态方法子类也是可以直接调用的<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642061000332-807e36f3-d332-4565-bff7-f9d6b7e668a8.png#clientId=ua6712525-b4e3-4&from=paste&height=26&id=u48beb609&margin=%5Bobject%20Object%5D&name=image.png&originHeight=51&originWidth=305&originalType=binary&ratio=1&size=16556&status=done&style=none&taskId=u06d2c7ff-6738-4e29-8bbf-bd9775f4186&width=152.5)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642059250609-13227507-dae2-4f21-9c49-f76b8c44a881.png#clientId=ua6712525-b4e3-4&from=paste&height=300&id=ub89ef1d0&margin=%5Bobject%20Object%5D&name=image.png&originHeight=600&originWidth=1370&originalType=binary&ratio=1&size=217301&status=done&style=none&taskId=u8a2f9ecc-0cbc-4d26-8ccb-7ac9f3f607e&width=685)<br />实现继承extends<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642059263905-47a13d1b-8d81-404f-87c2-4683608d1e52.png#clientId=ua6712525-b4e3-4&from=paste&height=321&id=udd3f15e4&margin=%5Bobject%20Object%5D&name=image.png&originHeight=642&originWidth=1450&originalType=binary&ratio=1&size=173294&status=done&style=none&taskId=u5174c0a5-47a3-4891-9464-a6d5113f713&width=725)
<a name="IP0XR"></a>
### Super关键字
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642060341131-31e147b4-8255-4001-af33-f3f1e69f287b.png#clientId=ua6712525-b4e3-4&from=paste&height=287&id=u57f30711&margin=%5Bobject%20Object%5D&name=image.png&originHeight=573&originWidth=1459&originalType=binary&ratio=1&size=242002&status=done&style=none&taskId=ud8f9e57d-43b2-4f71-80c1-010e860434b&width=729.5)
<a name="wHvC0"></a>
### 子类对父类重写方法
可以重写普通实例方法，也可以重写静态方法<br />如果除了自己重写的代码外，还需使用父类原有方法的逻辑，使用super调用即可<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642060801020-f90aa3a4-5f8d-4155-9d52-f2013472c6be.png#clientId=ua6712525-b4e3-4&from=paste&height=67&id=ua6fb82e6&margin=%5Bobject%20Object%5D&name=image.png&originHeight=133&originWidth=496&originalType=binary&ratio=1&size=35789&status=done&style=none&taskId=u5c32c23d-8bc2-4ebc-94fe-e1117fc4711&width=248)
<a name="PM5g6"></a>
### 继承内置类并做一定扩展
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642072262094-981fefd4-15e1-4d60-8514-9d624993844e.png#clientId=u72526633-d771-4&from=paste&height=269&id=u8b0c1c28&margin=%5Bobject%20Object%5D&name=image.png&originHeight=537&originWidth=750&originalType=binary&ratio=1&size=181405&status=done&style=none&taskId=ufba0038c-041d-4b06-a738-43d2b7565cf&width=375)
<a name="P6PG0"></a>
### 类的混入
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642072524241-b9200f4e-76a0-4121-a768-32c52c61c775.png#clientId=u72526633-d771-4&from=paste&height=404&id=u171703e4&margin=%5Bobject%20Object%5D&name=image.png&originHeight=808&originWidth=1442&originalType=binary&ratio=1&size=426830&status=done&style=none&taskId=u9678a776-0938-4db8-baf3-6eedd0ca8ad&width=721)
<a name="hnvTW"></a>
## 多态
<a name="BZQGN"></a>
## ![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642073235978-e31dd47f-049a-482d-ac1a-f48aba3bb366.png#clientId=u72526633-d771-4&from=paste&height=405&id=u3128be08&margin=%5Bobject%20Object%5D&name=image.png&originHeight=809&originWidth=1476&originalType=binary&ratio=1&size=260846&status=done&style=none&taskId=u97cbae37-a4cd-43ea-b4e4-47eb0c1cc44&width=738)
<a name="e7umL"></a>
## 
<a name="O7n7B"></a>
# 阅读源码
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642063475365-f6f3af4d-3b12-476e-a25f-d09fb71fa714.png#clientId=ua6712525-b4e3-4&from=paste&height=328&id=u4df10368&margin=%5Bobject%20Object%5D&name=image.png&originHeight=655&originWidth=966&originalType=binary&ratio=1&size=96472&status=done&style=none&taskId=u9ebd93ca-b209-452f-a94f-6ab5a504fd2&width=483)
<a name="lCEpB"></a>
# Es6（Es2015）
<a name="UzNRk"></a>
## Es6对象字面量的增强写法
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642075809768-882feaf8-4319-430f-8c91-a6d5dab25619.png#clientId=u72526633-d771-4&from=paste&height=230&id=qi0IG&margin=%5Bobject%20Object%5D&name=image.png&originHeight=460&originWidth=1195&originalType=binary&ratio=1&size=92477&status=done&style=none&taskId=uc8b52087-d0f5-4cd1-bce1-aa60f5ca7cd&width=597.5)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642075785306-5ca605ea-7d57-4430-a988-adeac7c7a681.png#clientId=u72526633-d771-4&from=paste&height=155&id=VjEAu&margin=%5Bobject%20Object%5D&name=image.png&originHeight=309&originWidth=497&originalType=binary&ratio=1&size=73471&status=done&style=none&taskId=u4ccdd20d-43e8-4297-8c7f-b22e3adf922&width=248.5)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642075803209-b06eb79f-1b5b-435e-ba4f-00b67f9f8eb8.png#clientId=u72526633-d771-4&from=paste&height=44&id=cnzXf&margin=%5Bobject%20Object%5D&name=image.png&originHeight=87&originWidth=376&originalType=binary&ratio=1&size=32278&status=done&style=none&taskId=u1918e0a5-2030-4897-ab43-5509dd8b1da&width=188)
<a name="tiwGp"></a>
## 解构
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642083430104-5db56856-375d-438f-9e7e-991e6487fa8a.png#clientId=u193b8331-14ac-4&from=paste&height=385&id=rogLG&margin=%5Bobject%20Object%5D&name=image.png&originHeight=769&originWidth=1198&originalType=binary&ratio=1&size=117828&status=done&style=none&taskId=ub70fb1c4-c4d5-448a-97fc-30c0f15f670&width=599)
<a name="pDdG4"></a>
### 数组的解构
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642083416144-44c4dc73-1e41-4d3f-8461-fe00ef08dc8e.png#clientId=u193b8331-14ac-4&from=paste&height=368&id=xxNhK&margin=%5Bobject%20Object%5D&name=image.png&originHeight=736&originWidth=816&originalType=binary&ratio=1&size=100135&status=done&style=none&taskId=ub3a08978-ad1c-478c-bf6f-ab4d81a0088&width=408)
<a name="kbu6R"></a>
### 对象的解构
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642083784132-a9bfe86d-fc21-4967-a027-50ebb498bee0.png#clientId=u193b8331-14ac-4&from=paste&height=448&id=znCu7&margin=%5Bobject%20Object%5D&name=image.png&originHeight=896&originWidth=563&originalType=binary&ratio=1&size=88445&status=done&style=none&taskId=u25ef73de-73d5-47f4-b2b5-909a29b51b3&width=281.5)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642083813755-d8d6f28b-6bdf-490e-9a68-2590300d115c.png#clientId=u193b8331-14ac-4&from=paste&height=378&id=yClOg&margin=%5Bobject%20Object%5D&name=image.png&originHeight=755&originWidth=1258&originalType=binary&ratio=1&size=545445&status=done&style=none&taskId=u75dbc816-cbf8-48c3-825b-fd8bcce7150&width=629)
<a name="FEeMo"></a>
## let const
<a name="S73Vd"></a>
### 基本
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642084052045-3be42827-ae85-452e-beb9-d8539dde341a.png#clientId=u193b8331-14ac-4&from=paste&height=421&id=u4f64ac04&margin=%5Bobject%20Object%5D&name=image.png&originHeight=841&originWidth=1487&originalType=binary&ratio=1&size=225283&status=done&style=none&taskId=ua427c6e8-942e-4718-b9fd-32a40a1b6cc&width=743.5)<br />

<a name="VJ8J5"></a>
### 作用域提升
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642084603057-d9fbd8ab-b887-4031-b8ab-032b2d867b86.png#clientId=u193b8331-14ac-4&from=paste&height=409&id=u74dc2e29&margin=%5Bobject%20Object%5D&name=image.png&originHeight=817&originWidth=1411&originalType=binary&ratio=1&size=415045&status=done&style=none&taskId=uf1638a0f-74b3-48d2-aeb2-9854e08609f&width=705.5)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642147727752-42ea06ee-b583-4932-82a4-409d55bfc24a.png#clientId=u88e1f65d-d475-4&from=paste&height=290&id=u5c9b2cc6&margin=%5Bobject%20Object%5D&name=image.png&originHeight=580&originWidth=1482&originalType=binary&ratio=1&size=212297&status=done&style=none&taskId=u0a53ddde-f4d5-4b6c-8557-3bf82d8c58a&width=741)
<a name="KjHXt"></a>
### window对象中的属性
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642148050148-c528c46a-e82d-44bc-9f22-0b02f65f609c.png#clientId=u88e1f65d-d475-4&from=paste&height=397&id=u8e29db42&margin=%5Bobject%20Object%5D&name=image.png&originHeight=794&originWidth=1437&originalType=binary&ratio=1&size=329448&status=done&style=none&taskId=u3fa17826-4450-4817-90fc-b793271cedc&width=718.5)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642148059317-fd2387f8-6c61-4456-9950-c4e47053c5fd.png#clientId=u88e1f65d-d475-4&from=paste&height=231&id=u04945d5d&margin=%5Bobject%20Object%5D&name=image.png&originHeight=461&originWidth=1475&originalType=binary&ratio=1&size=168685&status=done&style=none&taskId=u57f8fadb-821f-4466-841c-44ddf00ea86&width=737.5)
<a name="JCv12"></a>
### 块级作用域
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642148218844-7d191296-69cc-46d4-9922-3a7fc168dff6.png#clientId=u88e1f65d-d475-4&from=paste&height=355&id=u81a9f3aa&margin=%5Bobject%20Object%5D&name=image.png&originHeight=710&originWidth=1298&originalType=binary&ratio=1&size=207790&status=done&style=none&taskId=u75d344a1-039b-4bc3-b25b-0b39ce13a5d&width=649)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642148233471-0286618f-5571-454a-8820-855f31b8149f.png#clientId=u88e1f65d-d475-4&from=paste&height=363&id=ud8e6550f&margin=%5Bobject%20Object%5D&name=image.png&originHeight=725&originWidth=1432&originalType=binary&ratio=1&size=263741&status=done&style=none&taskId=uf7dd556e-e86a-40be-9039-ae718828ae7&width=716)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642148277026-66e93329-f1f3-4e05-b94e-eb6f87e1a2c9.png#clientId=u88e1f65d-d475-4&from=paste&height=344&id=ufb8f05f3&margin=%5Bobject%20Object%5D&name=image.png&originHeight=688&originWidth=795&originalType=binary&ratio=1&size=304481&status=done&style=none&taskId=ua4a719d4-d13f-4e91-86e8-2f97274a07c&width=397.5)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642148297083-5bd02afc-b249-4308-ab0f-722b2d39a7ae.png#clientId=u88e1f65d-d475-4&from=paste&height=382&id=ufea9e172&margin=%5Bobject%20Object%5D&name=image.png&originHeight=764&originWidth=1461&originalType=binary&ratio=1&size=276983&status=done&style=none&taskId=u0ba10580-8583-4a7e-9c9b-39971824cc5&width=730.5)
<a name="noxnZ"></a>
## 模板字符串
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642143009121-961b599e-5b8f-4191-94b5-3502a35d752b.png#clientId=u88e1f65d-d475-4&from=paste&height=386&id=u2678c132&margin=%5Bobject%20Object%5D&name=image.png&originHeight=772&originWidth=1420&originalType=binary&ratio=1&size=386618&status=done&style=none&taskId=ud8aca06b-3908-483d-a8c7-c17c5e3cea3&width=710)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642143554239-14867e75-b50e-4b10-bf9b-aeb4eddd8463.png#clientId=u88e1f65d-d475-4&from=paste&height=406&id=u726fced6&margin=%5Bobject%20Object%5D&name=image.png&originHeight=812&originWidth=1292&originalType=binary&ratio=1&size=267835&status=done&style=none&taskId=u9e1bcf06-7b51-4932-9900-4b1370a96d9&width=646)
<a name="jNPsj"></a>
## 函数的默认参数
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642148340548-9ffe15c9-9220-4ce0-93f1-90b647aa7820.png#clientId=u88e1f65d-d475-4&from=paste&height=409&id=ud41af3ad&margin=%5Bobject%20Object%5D&name=image.png&originHeight=818&originWidth=1457&originalType=binary&ratio=1&size=374850&status=done&style=none&taskId=u741a0be0-d0ad-4693-bbfb-61003ecfcdb&width=728.5)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642143767629-9af58178-b1f8-4582-84cb-997baadbfdf7.png#clientId=u88e1f65d-d475-4&from=paste&height=48&id=u4710e870&margin=%5Bobject%20Object%5D&name=image.png&originHeight=96&originWidth=253&originalType=binary&ratio=1&size=16783&status=done&style=none&taskId=ucbf5ab12-8dd2-44be-bf21-f2714b32057&width=126.5)<br />以上是es5的写法，有bug，因为传入null，undefined也会使用默认值
<a name="FZ1fi"></a>
### 结合解构
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642143933063-5d7e817b-32ca-44ad-8c3e-8908b8ab9698.png#clientId=u88e1f65d-d475-4&from=paste&height=383&id=u6bb91dbb&margin=%5Bobject%20Object%5D&name=image.png&originHeight=765&originWidth=1382&originalType=binary&ratio=1&size=296197&status=done&style=none&taskId=uf75326ca-2612-4fed-b9e8-5aeb6e8630b&width=691)
<a name="kWG9H"></a>
## 剩余参数
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642144404434-fd3fc480-e3e5-485e-af5b-bd3d276024f3.png#clientId=u88e1f65d-d475-4&from=paste&height=404&id=u9d43c145&margin=%5Bobject%20Object%5D&name=image.png&originHeight=808&originWidth=1535&originalType=binary&ratio=1&size=348887&status=done&style=none&taskId=uc54ab972-653a-4cf2-aac1-b7d65f819c0&width=767.5)
<a name="VsunK"></a>
## 箭头函数
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642144388630-b133bf81-cada-40ce-93b7-968bf8ea198d.png#clientId=u88e1f65d-d475-4&from=paste&height=315&id=u8f3f4a31&margin=%5Bobject%20Object%5D&name=image.png&originHeight=629&originWidth=1163&originalType=binary&ratio=1&size=204463&status=done&style=none&taskId=ubfdf1435-b0b8-499e-9f06-c11946574cf&width=581.5)
<a name="kLz21"></a>
## 展开语法
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642144826952-497889bb-4d58-4859-9230-cc07a449eba0.png#clientId=u88e1f65d-d475-4&from=paste&height=380&id=u9737b87e&margin=%5Bobject%20Object%5D&name=image.png&originHeight=759&originWidth=1430&originalType=binary&ratio=1&size=166928&status=done&style=none&taskId=ub401e843-07ad-46c0-8e77-e71285b2da3&width=715)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642144866359-85571686-b22f-47a0-b0eb-0be38cc423e2.png#clientId=u88e1f65d-d475-4&from=paste&height=244&id=u66a81f2f&margin=%5Bobject%20Object%5D&name=image.png&originHeight=488&originWidth=554&originalType=binary&ratio=1&size=160555&status=done&style=none&taskId=u862ec212-e004-4d08-a0e5-155da570a45&width=277)<br />在构造字面量对象的时候，将数组展开放入对象是按照索引号作为key的<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642145188930-43a6ca1d-56f1-4eb7-8810-3d6bf36970e7.png#clientId=u88e1f65d-d475-4&from=paste&height=130&id=u1184ace9&margin=%5Bobject%20Object%5D&name=image.png&originHeight=259&originWidth=454&originalType=binary&ratio=1&size=81958&status=done&style=none&taskId=ucc0e239e-fac8-422a-9924-35f798c937f&width=227)<br />展开运算符也是浅拷贝
<a name="aRha4"></a>
## 数值的表示（进制）
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642145409468-aa6a2ff4-3f08-4f19-b853-8d6bf216c359.png#clientId=u88e1f65d-d475-4&from=paste&height=397&id=u68f9964f&margin=%5Bobject%20Object%5D&name=image.png&originHeight=793&originWidth=1131&originalType=binary&ratio=1&size=272751&status=done&style=none&taskId=ud73c5c0e-a335-42b9-a031-d9ae69a6f63&width=565.5)
<a name="Tgsrr"></a>
## symbol
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642146528433-870733cc-bc6f-4ae5-8038-d3e754d7fd45.png#clientId=u88e1f65d-d475-4&from=paste&height=409&id=uc6d795a2&margin=%5Bobject%20Object%5D&name=image.png&originHeight=818&originWidth=1526&originalType=binary&ratio=1&size=349141&status=done&style=none&taskId=u1a861331-3344-4851-9fee-68e5b1ac262&width=763)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642146588880-019d7d19-a6a7-46b8-bb76-af87e46ce951.png#clientId=u88e1f65d-d475-4&from=paste&height=428&id=ud473f780&margin=%5Bobject%20Object%5D&name=image.png&originHeight=855&originWidth=1417&originalType=binary&ratio=1&size=435085&status=done&style=none&taskId=ucb222db6-476d-4fe5-a235-c9220b7aaf3&width=708.5)<br />symbol作为属性名不可以使用obj.的语法去获取，因为.语法是针对字符串属性名的一定要使用[]去访问<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642146905866-f9ef192d-015f-44d9-8cec-05df9e38506e.png#clientId=u88e1f65d-d475-4&from=paste&height=365&id=uf3f242f5&margin=%5Bobject%20Object%5D&name=image.png&originHeight=729&originWidth=1539&originalType=binary&ratio=1&size=356653&status=done&style=none&taskId=u80086297-9203-4242-9a4f-7ebb2c34179&width=769.5)
<a name="JGxq2"></a>
## Set
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642250525507-9e0a9b59-ea9a-4d24-a5a8-978c104bfc17.png#clientId=u20ff212d-d242-4&from=paste&height=408&id=u7beeb053&margin=%5Bobject%20Object%5D&name=image.png&originHeight=815&originWidth=1521&originalType=binary&ratio=1&size=547580&status=done&style=none&taskId=u8d689502-debc-48c4-b0d5-237d3a66194&width=760.5)<br />add加入分别加入两个空对象，加入的是不同的内存地址，因此set是会多出两个对象（不会重复），但如果是一个对象的引用，就只会多出一个<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642251651800-b192fac4-c1e5-4b7c-b5a1-dc2542aaa81e.png#clientId=u6c16c6a1-cf04-4&from=paste&height=143&id=ua3ba66b6&margin=%5Bobject%20Object%5D&name=image.png&originHeight=286&originWidth=535&originalType=binary&ratio=1&size=27877&status=done&style=none&taskId=u14b5b0ee-dfbe-4a4f-981c-d27fb55994b&width=267.5)<br />一般的数组去重<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642251593872-0ea4802d-8b86-4263-8a9f-709005dcb7d8.png#clientId=u6c16c6a1-cf04-4&from=paste&height=366&id=u85652428&margin=%5Bobject%20Object%5D&name=image.png&originHeight=732&originWidth=1121&originalType=binary&ratio=1&size=157060&status=done&style=none&taskId=ubcdec43f-eab8-4568-8a5b-262d07213bd&width=560.5)
<a name="a0btV"></a>
## Weakset
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642251807272-4d68ca4f-1f71-4bf5-8d22-c9b708f2e5b6.png#clientId=u6c16c6a1-cf04-4&from=paste&height=424&id=u237f9270&margin=%5Bobject%20Object%5D&name=image.png&originHeight=847&originWidth=1475&originalType=binary&ratio=1&size=291441&status=done&style=none&taskId=ufe15dc22-b9d8-4e96-8f0c-c3904bf1a94&width=737.5)<br />gc垃圾回收系统只会监测强引用，弱引用不会对gc造成印象<br />weakset是不能遍历的，不能用forEach等
<a name="kYZ9a"></a>
### 应用
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642255223215-8931102c-ee78-4c1f-a6d5-dc7c313e4d47.png#clientId=u6c16c6a1-cf04-4&from=paste&height=399&id=ua81254d8&margin=%5Bobject%20Object%5D&name=image.png&originHeight=797&originWidth=1466&originalType=binary&ratio=1&size=368602&status=done&style=none&taskId=u48970070-1242-411a-b301-56bacd48795&width=733)​<br />weakset保存的是弱引用，这样要销毁创建出来的新对象就直接=null，如果就set，还需要销毁set对新对象的强引用
<a name="fcIVq"></a>
## Map
<a name="Z1ITp"></a>
### 基本
js的对象的key只能是字符串/symbol<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642255578143-fce824cd-d163-42f5-87de-cf31a74a2c6a.png#clientId=u6c16c6a1-cf04-4&from=paste&height=130&id=u70ac98a4&margin=%5Bobject%20Object%5D&name=image.png&originHeight=259&originWidth=357&originalType=binary&ratio=1&size=70469&status=done&style=none&taskId=u3821f1b3-a52d-419c-a685-fba7ef12d60&width=178.5)<br />以上操作直接将obj转化为![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642255635222-73774811-45e7-4b08-964c-6dff019882a2.png#clientId=u6c16c6a1-cf04-4&from=paste&height=20&id=u14ed4c93&margin=%5Bobject%20Object%5D&name=image.png&originHeight=39&originWidth=277&originalType=binary&ratio=1&size=21395&status=done&style=none&taskId=u7e28e176-4f7e-426a-9304-2c9443c7e4f&width=138.5)，因此不能成功将对象作为key<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642255686764-ecfd4af5-6850-4084-96d0-e3e0fb3ffc2c.png#clientId=u6c16c6a1-cf04-4&from=paste&height=393&id=u4b311384&margin=%5Bobject%20Object%5D&name=image.png&originHeight=786&originWidth=1452&originalType=binary&ratio=1&size=480213&status=done&style=none&taskId=ud60da964-ac84-4f6c-900b-f1d92a45f94&width=726)
<a name="YmwYa"></a>
### 常用方法
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642256054514-74d507f4-60da-49fa-84fb-4a70e5ed829e.png#clientId=u6c16c6a1-cf04-4&from=paste&height=373&id=u90c970b3&margin=%5Bobject%20Object%5D&name=image.png&originHeight=746&originWidth=1178&originalType=binary&ratio=1&size=163586&status=done&style=none&taskId=u954fddb0-45f1-44be-88aa-a3bd027b6f3&width=589)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642256076244-a3dc0a14-1c91-4128-ba10-c625809e922e.png#clientId=u6c16c6a1-cf04-4&from=paste&height=165&id=ued85d434&margin=%5Bobject%20Object%5D&name=image.png&originHeight=329&originWidth=379&originalType=binary&ratio=1&size=81696&status=done&style=none&taskId=ub22f957d-7001-4bd2-a599-5cca7456bc2&width=189.5)<br />遍历（可结合解构）
<a name="E73Z4"></a>
## waekmap
<a name="MIBcE"></a>
### 基本
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642256160490-25b44127-4c24-4583-8a14-3bb3ba2025ab.png#clientId=u6c16c6a1-cf04-4&from=paste&height=412&id=u4e010244&margin=%5Bobject%20Object%5D&name=image.png&originHeight=823&originWidth=1417&originalType=binary&ratio=1&size=336827&status=done&style=none&taskId=u92291cde-e4f7-4624-b602-4332d5e2d30&width=708.5)
<a name="jAyFk"></a>
### 应用（响应式的原理）
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642256311121-a4b8d98b-25c2-4ae8-abb4-c477bca0fe32.png#clientId=u6c16c6a1-cf04-4&from=paste&height=422&id=u33bf14a8&margin=%5Bobject%20Object%5D&name=image.png&originHeight=844&originWidth=1214&originalType=binary&ratio=1&size=287807&status=done&style=none&taskId=u352ceb8d-7d1b-4534-9a74-27920a6ffb8&width=607)udi<br />利用weakmap将obj对象的属性和函数建立映射关系，创建weakmap对象<br />利用map将obj对象和weakmap对象建立映射关系1<br />从而将收集数据结构<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642257698891-0bc60ea7-28ac-4bab-88da-7883d5f97b50.png#clientId=u6c16c6a1-cf04-4&from=paste&height=375&id=u759ae786&margin=%5Bobject%20Object%5D&name=image.png&originHeight=750&originWidth=649&originalType=binary&ratio=1&size=75176&status=done&style=none&taskId=u20c90eb7-301b-4213-bbdd-048530efa6e&width=324.5)<br />​

![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642257679701-094ae937-212a-4223-a9c2-25942f5e6ae7.png#clientId=u6c16c6a1-cf04-4&from=paste&height=371&id=u4b53a1c8&margin=%5Bobject%20Object%5D&name=image.png&originHeight=742&originWidth=746&originalType=binary&ratio=1&size=118216&status=done&style=none&taskId=ue1fa8c2a-2cd9-4094-a22a-49a1f5306e9&width=373)
<a name="ZCOGv"></a>
# Es7（Es2016）
<a name="dicQk"></a>
## Arry Includes
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642258491073-f474323b-3a3b-4d35-8ac9-841ff9f28567.png#clientId=uf763c8a0-5c4a-4&from=paste&height=418&id=u9560be4f&margin=%5Bobject%20Object%5D&name=image.png&originHeight=836&originWidth=1575&originalType=binary&ratio=1&size=365035&status=done&style=none&taskId=uf9c688f9-0dd3-49a8-ae35-49831e23786&width=787.5)<br />第二个参数是索引号，表示从第几个元素开始检测<br />includes也可以判断NaN 但是indexOf不可以判断
<a name="aRdKl"></a>
##  指数(乘方) 运算符  
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642258638692-a2e7c5d0-5e47-4a64-9ff8-267843cf6870.png#clientId=uf763c8a0-5c4a-4&from=paste&height=250&id=u12c4f355&margin=%5Bobject%20Object%5D&name=image.png&originHeight=500&originWidth=1314&originalType=binary&ratio=1&size=204278&status=done&style=none&taskId=uac593ae7-c5c6-4494-bdde-e4ad0cbdb9f&width=657)
<a name="h4aP1"></a>
# Es8（Es2017）
<a name="l1Qvt"></a>
##  Object values  
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642258851703-d7e50e7e-d731-417f-a69d-c8ee43e02355.png#clientId=uf763c8a0-5c4a-4&from=paste&height=310&id=u7469dc38&margin=%5Bobject%20Object%5D&name=image.png&originHeight=620&originWidth=1566&originalType=binary&ratio=1&size=230230&status=done&style=none&taskId=u2c71e6af-1ce3-4106-9054-aaa4e3022b3&width=783)<br />也可以传入数组，返回的也是数组本身<br />也可以传入字符串，会进行分割，然后放到一个数组
<a name="Byivq"></a>
##  Object entries  
<a name="v4ws0"></a>
## ![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642258958969-98d79715-ba33-4d45-b5c6-1e8f1081f865.png#clientId=uf763c8a0-5c4a-4&from=paste&height=337&id=ua6196233&margin=%5Bobject%20Object%5D&name=image.png&originHeight=673&originWidth=1375&originalType=binary&ratio=1&size=341782&status=done&style=none&taskId=u88585930-c260-471f-9438-6b332a5ccae&width=687.5)String Paddin
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642259227522-d4030997-af43-4958-9ed3-93fd8324b2b7.png#clientId=uf763c8a0-5c4a-4&from=paste&height=382&id=u7b3ec2ec&margin=%5Bobject%20Object%5D&name=image.png&originHeight=764&originWidth=1546&originalType=binary&ratio=1&size=527351&status=done&style=none&taskId=u35b8b128-3af1-43d3-9fed-da210e5177a&width=773)
<a name="mecv6"></a>
##  Trailing Commas  
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642259437596-3699d4a5-7e90-410f-8ace-0820965388d4.png#clientId=uf763c8a0-5c4a-4&from=paste&height=182&id=u9dca5484&margin=%5Bobject%20Object%5D&name=image.png&originHeight=364&originWidth=861&originalType=binary&ratio=1&size=114196&status=done&style=none&taskId=uae40d9ea-5559-4993-80c4-7fdcb45dedd&width=430.5)
<a name="N5sFl"></a>
##  Object Descriptors  
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642259535741-7fb41dab-0448-480d-b9da-bff76b3154e7.png#clientId=uf763c8a0-5c4a-4&from=paste&height=164&id=u01d21627&margin=%5Bobject%20Object%5D&name=image.png&originHeight=328&originWidth=1568&originalType=binary&ratio=1&size=63161&status=done&style=none&taskId=u39bf1cc8-9c60-45ff-9b31-f3e4db5d2c2&width=784)
<a name="FfaqW"></a>
# Es9（Es2018)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642259620001-ad08a227-629d-48dd-97c8-dfbe5ddfb528.png#clientId=uf763c8a0-5c4a-4&from=paste&height=188&id=u24c52bb0&margin=%5Bobject%20Object%5D&name=image.png&originHeight=376&originWidth=673&originalType=binary&ratio=1&size=55132&status=done&style=none&taskId=u927c49a1-d93d-4a1e-a2f7-a45e53fa1cb&width=336.5)
<a name="KXh69"></a>
# Es10 (Es2019)
<a name="wpi2F"></a>
##  flat  flatmap
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642259817254-221af5fb-da04-40ab-a335-98e10467f6ad.png#clientId=uf763c8a0-5c4a-4&from=paste&height=400&id=ue868bdbb&margin=%5Bobject%20Object%5D&name=image.png&originHeight=800&originWidth=1539&originalType=binary&ratio=1&size=426581&status=done&style=none&taskId=uf95abc6a-7200-4720-a13b-adc66baba2e&width=769.5)
<a name="PMyqZ"></a>
##  Object fromEntries  
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642260795185-573b778a-4fb0-4c88-a89c-5aea897fbb01.png#clientId=uf763c8a0-5c4a-4&from=paste&height=414&id=ub8b5f672&margin=%5Bobject%20Object%5D&name=image.png&originHeight=827&originWidth=1600&originalType=binary&ratio=1&size=517834&status=done&style=none&taskId=uf120ab3f-6d9c-4774-a376-3fef08f49f5&width=800)<br />url后面的参数叫查询字符串，一般是传给服务器，但有时候前端也会做一定解析（路由映射）<br />以上应用是将查询字符串转换为对象 urlsearchparams将字符串转换为一个对象，这个对象可以遍历
<a name="G81Ry"></a>
## trimsrart trimend
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642301531820-3d4c1523-65ed-4e42-b1c6-faf24a01dc15.png#clientId=udcdd6b47-cfb7-4&from=paste&height=251&id=u1637c1ea&margin=%5Bobject%20Object%5D&name=image.png&originHeight=501&originWidth=1219&originalType=binary&ratio=1&size=222817&status=done&style=none&taskId=u154c014f-0002-4b7e-9a12-cbc355f7fbf&width=609.5)<br />trim可以去除所有空格
<a name="xUNOp"></a>
## 其他
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642301587412-5cf125ea-ce32-4740-81af-194257975865.png#clientId=udcdd6b47-cfb7-4&from=paste&height=160&id=ub8d7c46a&margin=%5Bobject%20Object%5D&name=image.png&originHeight=320&originWidth=841&originalType=binary&ratio=1&size=42059&status=done&style=none&taskId=ub35521aa-265b-4586-b2a5-71dedb10f5c&width=420.5)
<a name="LbeZr"></a>
# Es11（Es2020）
<a name="im7DL"></a>
## BigInt
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642301769679-d7cda208-3103-4a08-bb49-f7f471d562c4.png#clientId=udcdd6b47-cfb7-4&from=paste&height=400&id=u6022457e&margin=%5Bobject%20Object%5D&name=image.png&originHeight=800&originWidth=994&originalType=binary&ratio=1&size=363614&status=done&style=none&taskId=u89b787fd-679a-4519-a9a8-f7f14628219&width=497)<br />相加的方法，需要转换成大数<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642301932435-17ec7531-fb22-4e9d-90ac-bc2be011bd2b.png#clientId=udcdd6b47-cfb7-4&from=paste&height=87&id=u6401a0c4&margin=%5Bobject%20Object%5D&name=image.png&originHeight=173&originWidth=385&originalType=binary&ratio=1&size=58317&status=done&style=none&taskId=u797f31ee-001b-4223-b1f1-3f36ec36900&width=192.5)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642301972978-5a52eef8-558e-4bd7-89ae-517c06ffa6c7.png#clientId=udcdd6b47-cfb7-4&from=paste&height=31&id=u1d117f84&margin=%5Bobject%20Object%5D&name=image.png&originHeight=61&originWidth=329&originalType=binary&ratio=1&size=26797&status=done&style=none&taskId=u3505c3a8-11a7-47d2-a562-bedce5c1eec&width=164.5)<br />也可以转换为Number再相加，但是这样不安全，因为有可能数字过大
<a name="ybeaF"></a>
##  Nullish Coalescing Operator  空值合并操作符
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642302046724-6420452f-8fe8-4b16-acc8-66b2bf37e0d5.png#clientId=udcdd6b47-cfb7-4&from=paste&height=254&id=ue2163557&margin=%5Bobject%20Object%5D&name=image.png&originHeight=507&originWidth=1254&originalType=binary&ratio=1&size=237092&status=done&style=none&taskId=u5c0b5dcc-6f7b-4574-aaf8-cc0ba252b96&width=627)<br />逻辑或对于一些0，“”等会直接判断为否<br />因此？？可以如果是undefined或null才会使用默认值
<a name="HUpnV"></a>
##  Optional Chaining  可选链
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642302279651-84a6f0f8-81e3-4a7e-bdd5-66b340ecae16.png#clientId=udcdd6b47-cfb7-4&from=paste&height=408&id=u4518faf6&margin=%5Bobject%20Object%5D&name=image.png&originHeight=816&originWidth=1567&originalType=binary&ratio=1&size=364004&status=done&style=none&taskId=u58337be3-d4b8-4d8a-ae2f-44d31064a66&width=783.5)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642302386695-4097e59a-9b27-494e-9d80-824e8dce60b5.png#clientId=udcdd6b47-cfb7-4&from=paste&height=79&id=u2163f46a&margin=%5Bobject%20Object%5D&name=image.png&originHeight=158&originWidth=466&originalType=binary&ratio=1&size=34209&status=done&style=none&taskId=ucffd1002-6969-4f4c-8688-6673a6504c1&width=233)<br />如果从服务器返回的数据没有对应的值，前端取不到想要的值，就取到undefined，就会报错，js后面的逻辑就没办法执行。因此需要判断，开始es11前使用条件判断，es11出现了可选链
<a name="y4Dx2"></a>
## globalThis全局对象![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642302591487-b4ef40a2-6b6b-49fc-93e2-553ae45c775a.png#clientId=udcdd6b47-cfb7-4&from=paste&height=298&id=uee4334d8&margin=%5Bobject%20Object%5D&name=image.png&originHeight=596&originWidth=1193&originalType=binary&ratio=1&size=200898&status=done&style=none&taskId=ufdf91569-d793-42fb-8982-825e0d52a03&width=596.5)
node环境下没有定义window，node的全局对象（global），如果想一份代码在node和浏览器都可以执行，那就是用globalThis
<a name="yEHnv"></a>
## for in的标准化
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642302844760-e1790c69-56cc-436e-ac9f-cea27c28be92.png#clientId=udcdd6b47-cfb7-4&from=paste&height=339&id=u577d73e0&margin=%5Bobject%20Object%5D&name=image.png&originHeight=677&originWidth=1255&originalType=binary&ratio=1&size=216525&status=done&style=none&taskId=u58a5504a-5681-4aba-a96e-2f3b8edc9c2&width=627.5)
<a name="BBtpe"></a>
## 其他
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642302854938-999bd1f5-766d-4203-b2a0-09e54c27a9e9.png#clientId=udcdd6b47-cfb7-4&from=paste&height=196&id=ub692b495&margin=%5Bobject%20Object%5D&name=image.png&originHeight=391&originWidth=776&originalType=binary&ratio=1&size=67214&status=done&style=none&taskId=ufc8febe6-8add-4b5c-904f-dd65cf213b3&width=388)
<a name="Sinsp"></a>
# Es12（Es2021）
<a name="zqKA5"></a>
##  FinalizationRegistry  
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642304502764-e1394a75-167a-463f-b842-998638c12d5e.png#clientId=udcdd6b47-cfb7-4&from=paste&height=384&id=u81d9966d&margin=%5Bobject%20Object%5D&name=image.png&originHeight=768&originWidth=1575&originalType=binary&ratio=1&size=322575&status=done&style=none&taskId=u8a0a2cf8-c453-462b-b24b-597c42c2c05&width=787.5)
<a name="AaBYO"></a>
## WeakRef
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642312495602-fdcf596b-70b3-4d80-b9c3-5b895bd2791b.png#clientId=udcdd6b47-cfb7-4&from=paste&height=213&id=u4d0c2ba0&margin=%5Bobject%20Object%5D&name=image.png&originHeight=425&originWidth=1122&originalType=binary&ratio=1&size=138856&status=done&style=none&taskId=u564162e8-80c0-4380-803f-636ec14e0fe&width=561)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642312737229-dfbcbfca-7a2c-4e22-9de8-04855ef023d3.png#clientId=udcdd6b47-cfb7-4&from=paste&height=216&id=u31aad491&margin=%5Bobject%20Object%5D&name=image.png&originHeight=431&originWidth=635&originalType=binary&ratio=1&size=188976&status=done&style=none&taskId=u300d681e-5e95-4681-bcea-e1ca93f6bb8&width=317.5)
<a name="frBbg"></a>
## 逻辑赋值运算
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642312813923-7450ea3e-538d-447d-a21c-1e0ee46defbe.png#clientId=udcdd6b47-cfb7-4&from=paste&height=424&id=u9d218e62&margin=%5Bobject%20Object%5D&name=image.png&originHeight=848&originWidth=1170&originalType=binary&ratio=1&size=296438&status=done&style=none&taskId=u5163ceac-3397-4c59-871d-c1144463d50&width=585)
<a name="rxGDd"></a>
## 其他
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642313241823-db746bc2-2e90-4d12-a3e1-26e4aa6e3e33.png#clientId=udcdd6b47-cfb7-4&from=paste&height=155&id=u661ddd26&margin=%5Bobject%20Object%5D&name=image.png&originHeight=310&originWidth=677&originalType=binary&ratio=1&size=36169&status=done&style=none&taskId=u661f5e3e-2699-4a1d-8809-18cad8c521e&width=338.5)
<a name="gCxgE"></a>
# Proxy(es6新增的类)
<a name="yAJto"></a>
## 监听对象的操作
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642337645592-d63e3e20-ab61-4f73-8812-dbe20165c860.png#clientId=udcdd6b47-cfb7-4&from=paste&height=430&id=uea4834f6&margin=%5Bobject%20Object%5D&name=image.png&originHeight=859&originWidth=1547&originalType=binary&ratio=1&size=518167&status=done&style=none&taskId=ue4631089-0097-44dd-9547-47cb52c502b&width=773.5)
<a name="cJI5X"></a>
## 基本
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642337919489-9466c295-a4ca-4126-9ea7-d3af4ab46bee.png#clientId=udcdd6b47-cfb7-4&from=paste&height=426&id=AsLMG&margin=%5Bobject%20Object%5D&name=image.png&originHeight=852&originWidth=1547&originalType=binary&ratio=1&size=340191&status=done&style=none&taskId=u1492ef88-ea95-4111-8712-99459cd2e30&width=773.5)<br />第一个参数是要代理的对象，第二个是捕获器
<a name="DWgBU"></a>
## 捕获器
<a name="Q4Osq"></a>
### 基本
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642338468860-93f2158d-a278-492e-ac4b-bdeaba85c976.png#clientId=udcdd6b47-cfb7-4&from=paste&height=402&id=HPMAR&margin=%5Bobject%20Object%5D&name=image.png&originHeight=803&originWidth=1404&originalType=binary&ratio=1&size=239891&status=done&style=none&taskId=u1860ffe2-38b8-4468-9f7b-8f0768baed6&width=702)<br />apply和construct有用于对函数对象的监听<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642398848984-49acd5e1-88f2-4144-89f0-ec2c24f34980.png#clientId=udcdd6b47-cfb7-4&from=paste&height=396&id=uceb78b43&margin=%5Bobject%20Object%5D&name=image.png&originHeight=792&originWidth=1262&originalType=binary&ratio=1&size=425176&status=done&style=none&taskId=ua17199da-f1ba-43af-93b6-708930dc925&width=631)
<a name="rgNxo"></a>
### set和get
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642338252266-5981ba2d-a4e6-4a44-bfd4-139329f690f1.png#clientId=udcdd6b47-cfb7-4&from=paste&height=409&id=uf60b8b6a&margin=%5Bobject%20Object%5D&name=image.png&originHeight=817&originWidth=1370&originalType=binary&ratio=1&size=508971&status=done&style=none&taskId=u61e49a12-6e1a-4859-9253-7d773b0a9e6&width=685)
<a name="eSbHm"></a>
# Reflect（es6新增的对象/构造函数）
<a name="bmQET"></a>
## 基本
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642398871955-7b0cf822-4ea1-4c51-b860-ef4c7a0d34da.png#clientId=udcdd6b47-cfb7-4&from=paste&height=357&id=u20ff15be&margin=%5Bobject%20Object%5D&name=image.png&originHeight=714&originWidth=1310&originalType=binary&ratio=1&size=250962&status=done&style=none&taskId=u7b04a950-74a6-4e3d-b5de-c30df1d23ee&width=655)<br />[https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Reflect/Comparing_Reflect_and_Object_methods](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Reflect/Comparing_Reflect_and_Object_methods)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642398529326-f3a305dc-939f-4ab6-bfb5-b9419e0c8651.png#clientId=udcdd6b47-cfb7-4&from=paste&height=389&id=u67892f98&margin=%5Bobject%20Object%5D&name=image.png&originHeight=777&originWidth=1208&originalType=binary&ratio=1&size=445802&status=done&style=none&taskId=ub07ef726-7d59-4e79-b12b-e9035d034d7&width=604)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642399202038-419c4ef1-0d63-41c6-b9e6-2719fafbf92a.png#clientId=udcdd6b47-cfb7-4&from=paste&height=395&id=u41091ddc&margin=%5Bobject%20Object%5D&name=image.png&originHeight=789&originWidth=1172&originalType=binary&ratio=1&size=445910&status=done&style=none&taskId=u86c58fab-0924-4714-b2aa-d32e302ba83&width=586)
<a name="AnkrC"></a>
## 方法（对应于proxy）
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642399193218-42083ab9-9379-4586-905b-b61e1e8ee282.png#clientId=udcdd6b47-cfb7-4&from=paste&height=390&id=u5268ffcb&margin=%5Bobject%20Object%5D&name=image.png&originHeight=780&originWidth=1447&originalType=binary&ratio=1&size=360367&status=done&style=none&taskId=u000e855e-b7d8-48e5-b6c6-aa5050f7040&width=723.5)
<a name="XMj55"></a>
## Receiver参数
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642403696946-5a1f2ae9-509b-4bbb-b636-53be7839d4a3.png#clientId=udcdd6b47-cfb7-4&from=paste&height=410&id=uca2ce1d0&margin=%5Bobject%20Object%5D&name=image.png&originHeight=819&originWidth=1442&originalType=binary&ratio=1&size=422289&status=done&style=none&taskId=ub7bc2ac2-7838-4d0e-9e96-a29bfd8e5d1&width=721)<br />receiver指的是代理代理对象<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642403860595-eca7c97e-35b0-49b4-a013-6c80f5cd96c1.png#clientId=udcdd6b47-cfb7-4&from=paste&height=372&id=udfaf641c&margin=%5Bobject%20Object%5D&name=image.png&originHeight=744&originWidth=1413&originalType=binary&ratio=1&size=372521&status=done&style=none&taskId=u0ade9bf0-b670-44a0-9599-327c3056bec&width=706.5)<br />_name是私有属性，name是外界访问的属性，因为外界直接访问的是name，对象中的this指向的是obj对象,因此相当于直接给_name赋值，没有经过代理对象<br />传入了receiver参数，获得了一个对象（是代理对象），就会改变this的指向，指向代理对象，因此会再次调用代理对象的捕获器（总共调用两次），达到了监听name和_name属性的效果
<a name="h4LA7"></a>
## construct方法
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642405279455-cf899651-d5f2-4d8c-ae3a-4c92f0210cb8.png#clientId=u89bce8e0-94a4-4&from=paste&height=308&id=u7e24d0c6&margin=%5Bobject%20Object%5D&name=image.png&originHeight=615&originWidth=1047&originalType=binary&ratio=1&size=251832&status=done&style=none&taskId=u5cfe7096-ec92-4908-b892-42a588f6dcd&width=523.5)<br />执行student的方法，但是创建出来的对象类型是teacher，而且创建出来的隐式原型也是等于Teacher的显式原型
<a name="vYAwr"></a>
# 响应式原理
<a name="e4EsH"></a>
## 基本
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642405484036-7a756254-8326-4097-ba6c-7b8e2bd329f1.png#clientId=u89bce8e0-94a4-4&from=paste&height=341&id=u864b329e&margin=%5Bobject%20Object%5D&name=image.png&originHeight=681&originWidth=1090&originalType=binary&ratio=1&size=247316&status=done&style=none&taskId=ue6d1cbb1-f2ef-46fe-8ab9-69bd8ba57c9&width=545)<br />当数据/对象发生变化，其对应的依赖都会自动重新执行一次叫响应式
<a name="MAM5N"></a>
# Promise（Es6新增的类）
<a name="Tr4JC"></a>
## 异步任务的处理
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642690589559-a7e92a91-6642-411e-bb6c-af115345c253.png#clientId=u89f53bcc-0cbd-4&from=paste&height=355&id=u635e8a10&margin=%5Bobject%20Object%5D&name=image.png&originHeight=710&originWidth=1259&originalType=binary&ratio=1&size=367925&status=done&style=none&taskId=u542881a1-1bf0-45a1-8db6-39517378ce4&width=629.5)
<a name="huiQH"></a>
## 基本
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642691183214-21a3d43c-61c1-402e-8f7d-b88e28ea118b.png#clientId=u89f53bcc-0cbd-4&from=paste&height=359&id=u9241311f&margin=%5Bobject%20Object%5D&name=image.png&originHeight=717&originWidth=1291&originalType=binary&ratio=1&size=268239&status=done&style=none&taskId=u7794aa06-5459-40ab-b41a-50f49a08756&width=645.5)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642692126457-2649c877-0201-4e48-8e4a-4b6a0d4f8d65.png#clientId=u89f53bcc-0cbd-4&from=paste&height=339&id=u8a952246&margin=%5Bobject%20Object%5D&name=image.png&originHeight=678&originWidth=1277&originalType=binary&ratio=1&size=256624&status=done&style=none&taskId=u86f30419-6026-4eae-b985-999668ce26a&width=638.5)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642750055497-cd1170c6-d8ea-456c-abcd-961a5511e0ff.png#clientId=u89f53bcc-0cbd-4&from=paste&height=333&id=u84a297f2&margin=%5Bobject%20Object%5D&name=image.png&originHeight=665&originWidth=853&originalType=binary&ratio=1&size=258701&status=done&style=none&taskId=uae3fafaf-1817-44b8-b297-4e61e1e43d3&width=426.5)
<a name="RQQAm"></a>
## Excutor
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642750071219-e3c7e10e-7917-44d8-b8eb-8b023b9de1df.png#clientId=u89f53bcc-0cbd-4&from=paste&height=354&id=u0d53d542&margin=%5Bobject%20Object%5D&name=image.png&originHeight=708&originWidth=1220&originalType=binary&ratio=1&size=249861&status=done&style=none&taskId=u7317a0d2-bc79-4936-b95e-700b52902cf&width=610)
<a name="K83NH"></a>
## resolve传入不同的值
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642750133147-54a27e27-34e4-47c7-af02-f700137dad4a.png#clientId=u89f53bcc-0cbd-4&from=paste&height=351&id=u3145818a&margin=%5Bobject%20Object%5D&name=image.png&originHeight=702&originWidth=1287&originalType=binary&ratio=1&size=403068&status=done&style=none&taskId=u570e971c-0e6f-4357-a09f-367dd2d20b0&width=643.5)
<a name="fL5Kw"></a>
## Promise实例方法
<a name="QdBKJ"></a>
### then方法
<a name="HFEr9"></a>
#### 参数
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642750191612-e12a3f24-0be2-4de5-acad-bd29305e6508.png#clientId=u89f53bcc-0cbd-4&from=paste&height=360&id=uce293f94&margin=%5Bobject%20Object%5D&name=image.png&originHeight=719&originWidth=1072&originalType=binary&ratio=1&size=231847&status=done&style=none&taskId=uafd08ca7-18a0-4eb7-80fd-c3eb98979f0&width=536)
<a name="PmcKw"></a>
#### 返回值
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642835078915-8eef83db-5534-407e-a54a-378b4aff9fe8.png#clientId=u89f53bcc-0cbd-4&from=paste&height=330&id=u8e026afd&margin=%5Bobject%20Object%5D&name=image.png&originHeight=660&originWidth=1264&originalType=binary&ratio=1&size=170715&status=done&style=none&taskId=uc241715f-f608-4696-80e2-2cf38bafd69&width=632)返回普通的值（数值/字符串/普通对象/undefined）<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642835192231-4025c37b-981b-4aff-a7ba-64c547a01c3a.png#clientId=u89f53bcc-0cbd-4&from=paste&height=73&id=ubd2e14be&margin=%5Bobject%20Object%5D&name=image.png&originHeight=145&originWidth=910&originalType=binary&ratio=1&size=112942&status=done&style=none&taskId=u6b8b41ef-22e0-4dc7-a50e-da2fb26426b&width=455)<br />如果没有返回值，那么就默认是新promise的resolve值为undefined
<a name="Omsbl"></a>
### catch方法
catch方法是then传入第二个回调函数的语法糖，但是这个方法是不符合promise/a+方法<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642836469518-3897775b-299a-404b-9c60-9ce7ada324b8.png#clientId=u89f53bcc-0cbd-4&from=paste&height=351&id=ucd21a8d0&margin=%5Bobject%20Object%5D&name=image.png&originHeight=701&originWidth=1245&originalType=binary&ratio=1&size=193504&status=done&style=none&taskId=ude7f60dd-dd17-4227-9720-e5731817155&width=622.5)<br />then的传入的第二个回调既可以捕获上一个promise的reject也可以捕获上一个promise抛出的异常，catch方法也是<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642836593384-1e102bc7-f61d-4797-8025-167d18a5c1da.png#clientId=u89f53bcc-0cbd-4&from=paste&height=30&id=ud2d7d60e&margin=%5Bobject%20Object%5D&name=image.png&originHeight=60&originWidth=345&originalType=binary&ratio=1&size=24486&status=done&style=none&taskId=u3c63657c-b237-4a2e-82cf-775b67f6bf8&width=172.5)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642836769092-6adf4768-fa8e-4241-b4f6-e4a855963d59.png#clientId=u89f53bcc-0cbd-4&from=paste&height=78&id=uba38927a&margin=%5Bobject%20Object%5D&name=image.png&originHeight=155&originWidth=273&originalType=binary&ratio=1&size=31401&status=done&style=none&taskId=ub5e7ac0b-f742-467b-b067-fba43df6139&width=136.5)<br />以上的catch捕获的是最原始的promise的错误或者异常，并不是<br />then返回的新promise的错误或者异常，跟then.then的链式调用不是一回事
<a name="i1aOx"></a>
#### 返回值
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642837279959-71d4da06-f608-4123-9308-6911ed7adcb6.png#clientId=u89f53bcc-0cbd-4&from=paste&height=354&id=u81458755&margin=%5Bobject%20Object%5D&name=image.png&originHeight=707&originWidth=1273&originalType=binary&ratio=1&size=278737&status=done&style=none&taskId=ub4adcad2-620f-4927-8249-20bf6ce0eab&width=636.5)​<br />
<br />cat执行完返回的一新promise，依然是将回调函数的返回值包裹在resolve里面的
<a name="XDphc"></a>
### finally方法
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642837839400-eaa7ab81-9060-4eed-8d09-b02491a3a079.png#clientId=u89f53bcc-0cbd-4&from=paste&height=348&id=u87f6e749&margin=%5Bobject%20Object%5D&name=image.png&originHeight=695&originWidth=1293&originalType=binary&ratio=1&size=256670&status=done&style=none&taskId=u3b216164-2871-4ed6-807e-5639d7e88fc&width=646.5)
<a name="PflsU"></a>
## Promise类方法
<a name="ahdua"></a>
### resolve
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642838328265-e0530ba9-ac55-45fd-94db-aac4079284ad.png#clientId=u89f53bcc-0cbd-4&from=paste&height=349&id=u5bc29c1a&margin=%5Bobject%20Object%5D&name=image.png&originHeight=698&originWidth=1275&originalType=binary&ratio=1&size=206267&status=done&style=none&taskId=u6ae7d31f-84b8-40cc-94fa-13389af950d&width=637.5)
<a name="FgNLK"></a>
### reject
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642838342326-a074b171-6110-4501-b131-bdbd959105fb.png#clientId=u89f53bcc-0cbd-4&from=paste&height=258&id=ud0ce7596&margin=%5Bobject%20Object%5D&name=image.png&originHeight=516&originWidth=1074&originalType=binary&ratio=1&size=161987&status=done&style=none&taskId=u02b31466-c0b4-4b59-ae59-bc58ce594f6&width=537)注意第三点，reject无论里面的值是什么，都会当作参数传递给catch而不会像resolve一样有三种情况
<a name="JM2ez"></a>
### all
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642838557942-af5b6992-7c02-417e-8747-8fccb9f31739.png#clientId=u89f53bcc-0cbd-4&from=paste&height=362&id=u34c00c0b&margin=%5Bobject%20Object%5D&name=image.png&originHeight=723&originWidth=1297&originalType=binary&ratio=1&size=309971&status=done&style=none&taskId=u146721ba-ecd6-4074-b31f-594e112fd78&width=648.5)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642838735832-f87bde89-87e5-4b1e-82cc-116960003816.png#clientId=u89f53bcc-0cbd-4&from=paste&height=43&id=u8d177c4d&margin=%5Bobject%20Object%5D&name=image.png&originHeight=85&originWidth=476&originalType=binary&ratio=1&size=33796&status=done&style=none&taskId=ud9e0c9ea-aa6d-4c15-b6d7-bc4cf99d3cd&width=238)<br />参数的数组可以放入普通值，相当于将普通值调用Promise.resolve方法，生成一个promise
<a name="S6DbY"></a>
### allSettled
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642839004787-b33b98c6-9031-4a3d-bbc1-5f3c04713b45.png#clientId=u89f53bcc-0cbd-4&from=paste&height=363&id=u8958741d&margin=%5Bobject%20Object%5D&name=image.png&originHeight=725&originWidth=1278&originalType=binary&ratio=1&size=260517&status=done&style=none&taskId=u309b9d1e-0776-416e-a90f-683ce970de5&width=639)
<a name="eFyz1"></a>
### race
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642839130747-ae38c62b-bcb6-4d32-bf3a-f1a05832e058.png#clientId=u89f53bcc-0cbd-4&from=paste&height=215&id=u2bd6930f&margin=%5Bobject%20Object%5D&name=image.png&originHeight=429&originWidth=1128&originalType=binary&ratio=1&size=149850&status=done&style=none&taskId=u5dab1583-5167-45a0-aa95-a4896d99ea8&width=564)<br />但是如果有一个promise的状态是rejected，那么race返回的这个promise就直接编程rejected
<a name="skXpZ"></a>
### any
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1642839346376-4e3b9dfb-650c-4ee5-8208-0b926fcb25e0.png#clientId=u89f53bcc-0cbd-4&from=paste&height=304&id=u85d586be&margin=%5Bobject%20Object%5D&name=image.png&originHeight=607&originWidth=1062&originalType=binary&ratio=1&size=184063&status=done&style=none&taskId=ua1d21b88-c55b-422e-9748-9443e018178&width=531)<br />有一个promise的状态是rejected，也不会像race一样直接rejected，而是等其他结果，如果所有结果都是rejected，那么才会rejected
<a name="IZr40"></a>
## 手写promise
<a name="iEwzg"></a>
## promises/A+社区规范文档（与Es6的promise是有区别的）
[https://promisesaplus.com/](https://promisesaplus.com/)
<a name="m6Q37"></a>
# 迭代器
<a name="qWhpW"></a>
## 基本
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1644383669419-fa63f674-b0ed-4ffd-9704-9fd30e71d666.png#clientId=ub7765431-7548-4&from=paste&height=416&id=u9c5e9ace&margin=%5Bobject%20Object%5D&name=image.png&originHeight=831&originWidth=1546&originalType=binary&ratio=1&size=315757&status=done&style=none&taskId=uc1d8c2ea-9f9f-4640-8efb-df8b77836cc&width=773)
<a name="MdzTZ"></a>
## 基本迭代器的实现
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1644394860269-b5642131-b6bb-47e2-bc67-39631f6f27d5.png#clientId=ub7765431-7548-4&from=paste&height=404&id=u145bda7b&margin=%5Bobject%20Object%5D&name=image.png&originHeight=807&originWidth=1468&originalType=binary&ratio=1&size=655374&status=done&style=none&taskId=ua13e54c4-42d5-4c0d-9e0c-7a3f1ef6c4b&width=734)
<a name="CruB9"></a>
### 无限迭代器（了解）
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1644394916468-df88743d-b5c7-4408-9b60-6177683edf9f.png#clientId=ub7765431-7548-4&from=paste&height=124&id=ua1ddf709&margin=%5Bobject%20Object%5D&name=image.png&originHeight=247&originWidth=486&originalType=binary&ratio=1&size=89339&status=done&style=none&taskId=u7d397c19-41fa-44b5-a8a6-6ab8837a494&width=243)
<a name="LI5dK"></a>
## 可迭代对象
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1644395056431-7678b343-49df-4753-bd2c-5f60dea93891.png#clientId=ub7765431-7548-4&from=paste&height=402&id=u39b274f1&margin=%5Bobject%20Object%5D&name=image.png&originHeight=804&originWidth=1492&originalType=binary&ratio=1&size=235496&status=done&style=none&taskId=u136b18d8-7096-4497-90ef-e5ff300b23e&width=746)
<a name="m6CY7"></a>
### 原生迭代器对象
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1644401123945-0509ef1b-dd62-4160-9e0b-6ad63b9807a2.png#clientId=ub7765431-7548-4&from=paste&height=421&id=u36c7b188&margin=%5Bobject%20Object%5D&name=image.png&originHeight=841&originWidth=1461&originalType=binary&ratio=1&size=563733&status=done&style=none&taskId=u571d1c0f-b664-4473-9985-286106dba6a&width=730.5)
<a name="MquHu"></a>
### 可迭代器的应用
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1644401141663-2e46d856-b516-47e1-9d00-c3c9e3ac692c.png#clientId=ub7765431-7548-4&from=paste&height=418&id=u97e48b62&margin=%5Bobject%20Object%5D&name=image.png&originHeight=835&originWidth=1600&originalType=binary&ratio=1&size=399779&status=done&style=none&taskId=uee40825b-935d-4175-8859-c1353731395&width=800)<br />注意：Es9中新增特性：展开运算符和解构运算都是可以对普通对象进行运算的，之前不可以（因为普通对象不是可迭代对象），这个新增特性运用的就不是迭代器
<a name="aTD70"></a>
### 自定义类的迭代
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1644402200608-0795c175-2e85-4e91-9320-ce24fd22b0a6.png#clientId=ub7765431-7548-4&from=paste&height=352&id=ufb5b6172&margin=%5Bobject%20Object%5D&name=image.png&originHeight=704&originWidth=1459&originalType=binary&ratio=1&size=178413&status=done&style=none&taskId=u1565694e-bb59-458f-86d7-1a66304654f&width=729.5)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1644402296637-298e8b75-0ca3-4363-b663-d50bf6e7978d.png#clientId=ub7765431-7548-4&from=paste&height=415&id=u87687208&margin=%5Bobject%20Object%5D&name=image.png&originHeight=829&originWidth=1566&originalType=binary&ratio=1&size=434814&status=done&style=none&taskId=ua95fc6cf-2b56-4b3a-bd9c-0b66153166d&width=783)
<a name="qhTZX"></a>
## 迭代器中断（少见）
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1644407880425-ca475481-c22f-45b3-afeb-04c19882fcdc.png#clientId=ub7765431-7548-4&from=paste&height=423&id=u788c1442&margin=%5Bobject%20Object%5D&name=image.png&originHeight=846&originWidth=1449&originalType=binary&ratio=1&size=419600&status=done&style=none&taskId=u3039d793-8138-46a7-b153-06717b69fa3&width=724.5)
<a name="u63bK"></a>
# 生成器
<a name="d9Kyj"></a>
## 基本![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1644410751530-2ab00542-b463-4100-aafe-02b6325bf35f.png#clientId=ub7765431-7548-4&from=paste&height=389&id=u7296284e&margin=%5Bobject%20Object%5D&name=image.png&originHeight=778&originWidth=1564&originalType=binary&ratio=1&size=215591&status=done&style=none&taskId=u330e3bb4-b1a0-4727-aafc-0ba97c76193&width=782)
<a name="T0SDV"></a>
## 执行
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1644410814393-ba61b274-5e18-4db8-812b-10795d99f24f.png#clientId=ub7765431-7548-4&from=paste&height=425&id=u89e8846a&margin=%5Bobject%20Object%5D&name=image.png&originHeight=849&originWidth=1529&originalType=binary&ratio=1&size=473951&status=done&style=none&taskId=ud9505263-0a6c-460f-8777-297375f34b0&width=764.5)<br />return相当于一个特殊的yelid，return后再次调用next，返回值都是{value：undefined，done：true}
<a name="ugyBU"></a>
## 传递参数
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1644411881406-dc186b50-b759-4f31-b43c-612804e633ed.png#clientId=ub7765431-7548-4&from=paste&height=425&id=u1fdb9077&margin=%5Bobject%20Object%5D&name=image.png&originHeight=850&originWidth=1559&originalType=binary&ratio=1&size=476051&status=done&style=none&taskId=uea0aa68e-7d73-442c-9386-4c4edd3a855&width=779.5)
<a name="w3kau"></a>
## 提前结束
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1644412224678-afad61fb-ad75-4a4e-9276-65171e459dd3.png#clientId=ub7765431-7548-4&from=paste&height=405&id=u910d8437&margin=%5Bobject%20Object%5D&name=image.png&originHeight=809&originWidth=1233&originalType=binary&ratio=1&size=418531&status=done&style=none&taskId=u42d6ac00-669a-4f57-8352-ff2645cb333&width=616.5)<br />调用return方法的话当前这段也不会执行，相当于在当前代码的开头return
<a name="dzxmJ"></a>
## 抛出异常
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1644413468164-da5fa421-3fb8-4a4f-93fe-77fedb9f4df5.png#clientId=ub7765431-7548-4&from=paste&height=145&id=ubbccb05d&margin=%5Bobject%20Object%5D&name=image.png&originHeight=290&originWidth=1202&originalType=binary&ratio=1&size=64744&status=done&style=none&taskId=u6337af7c-b9e4-4cec-bd86-90ddc922930&width=601)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1644413475081-2afab418-8073-403e-ab8a-c9a4e1616725.png#clientId=ub7765431-7548-4&from=paste&height=258&id=ua6e6b54e&margin=%5Bobject%20Object%5D&name=image.png&originHeight=516&originWidth=1183&originalType=binary&ratio=1&size=321192&status=done&style=none&taskId=u9082b628-fc94-48f4-b075-1be4e646a07&width=591.5)<br />throw是相当于在上一个yelid中抛出错误，如果又捕获的话，就会继续执行直到yelid，相当于next一样
<a name="Ewmbn"></a>
## 代替迭代器
<a name="MKCQo"></a>
### 基本
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1644419141795-ed9a1b9c-b159-4b05-8797-327122dc3d75.png#clientId=u6503bf6c-b808-4&from=paste&height=421&id=ue7686d3e&margin=%5Bobject%20Object%5D&name=image.png&originHeight=842&originWidth=1534&originalType=binary&ratio=1&size=602114&status=done&style=none&taskId=uca41d9f2-8425-4a61-b5fa-88cfab566b2&width=767)
<a name="g8et4"></a>
###  自定义类迭代 – 生成器实现  
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1644419176959-851d76aa-bb5f-4a36-af73-fd31d99c6ac9.png#clientId=u6503bf6c-b808-4&from=paste&height=409&id=u635cf6fc&margin=%5Bobject%20Object%5D&name=image.png&originHeight=818&originWidth=1240&originalType=binary&ratio=1&size=341830&status=done&style=none&taskId=ue0877274-cfd7-4508-817b-75a9fb3a214&width=620)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1644419240132-7ea1c925-66c3-45dd-ad0c-37e6f6e49444.png#clientId=u6503bf6c-b808-4&from=paste&height=48&id=u829394ef&margin=%5Bobject%20Object%5D&name=image.png&originHeight=96&originWidth=359&originalType=binary&ratio=1&size=27730&status=done&style=none&taskId=uac336286-6cf6-4d7a-8f88-49408d87a5f&width=179.5)<br />这样也是可以的
<a name="BhGeM"></a>
# js错误处理方案
<a name="hJsYR"></a>
## 基本
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643098097081-e301e989-4e4a-4151-98dd-2be2dc8d090f.png#clientId=u1c9a604e-2b1d-4&from=paste&height=430&id=u3c0afc3c&margin=%5Bobject%20Object%5D&name=image.png&originHeight=859&originWidth=1480&originalType=binary&ratio=1&size=282855&status=done&style=none&taskId=ubb0da06f-3221-4560-a96e-97b161ec7dc&width=740)
<a name="ogB9N"></a>
## throw关键字
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643098528489-77a25f7f-30bb-4926-b2e8-0c6c6331010d.png#clientId=u1c9a604e-2b1d-4&from=paste&height=397&id=u85780712&margin=%5Bobject%20Object%5D&name=image.png&originHeight=793&originWidth=1336&originalType=binary&ratio=1&size=255359&status=done&style=none&taskId=ue506cf6a-4bd1-4104-bd38-e567bda268f&width=668)
<a name="KNHrZ"></a>
## Error类
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643098603300-2e9b2404-cf95-4dd3-ad3a-ed12b6f04594.png#clientId=u1c9a604e-2b1d-4&from=paste&height=402&id=u8113796c&margin=%5Bobject%20Object%5D&name=image.png&originHeight=804&originWidth=1441&originalType=binary&ratio=1&size=259182&status=done&style=none&taskId=u97bd151e-6041-4a64-b13a-90bb3fcc78d&width=720.5)
<a name="yeUNK"></a>
## 异常处理
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643100068727-ac961208-c97f-44ed-b30d-30a68fc028be.png#clientId=u1c9a604e-2b1d-4&from=paste&height=401&id=ubc4aee59&margin=%5Bobject%20Object%5D&name=image.png&originHeight=801&originWidth=1466&originalType=binary&ratio=1&size=360017&status=done&style=none&taskId=u20acb526-d73d-46c2-aff8-3788a7568ea&width=733)
<a name="bgLVg"></a>
## 异常捕获
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643100111642-7d1f99c7-70b5-4874-8831-4e77fbeee15b.png#clientId=u1c9a604e-2b1d-4&from=paste&height=409&id=u00fda3aa&margin=%5Bobject%20Object%5D&name=image.png&originHeight=818&originWidth=1398&originalType=binary&ratio=1&size=279333&status=done&style=none&taskId=u86ceb9ed-acc2-4cf4-8780-fabff040ac8&width=699)
<a name="mr5ed"></a>
# js模块化
<a name="UbFyA"></a>
## 基本
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643101776616-3e05f038-1882-4242-831d-8dea54bec407.png#clientId=u1c9a604e-2b1d-4&from=paste&height=405&id=uf6a7ab13&margin=%5Bobject%20Object%5D&name=image.png&originHeight=810&originWidth=1474&originalType=binary&ratio=1&size=302515&status=done&style=none&taskId=uaf72f372-9217-4a69-a16f-f1c7ba77f62&width=737)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643174967212-c90e59a5-f30e-488c-8797-d161ad5258fc.png#clientId=u1c9a604e-2b1d-4&from=paste&height=402&id=uc420900d&margin=%5Bobject%20Object%5D&name=image.png&originHeight=803&originWidth=1368&originalType=binary&ratio=1&size=300183&status=done&style=none&taskId=uf090d7e1-676c-4784-9be6-678149874ab&width=684)
<a name="TDo0U"></a>
## 历史
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643101789530-47a2950b-91ac-4ba6-90ff-1651953ab6ca.png#clientId=u1c9a604e-2b1d-4&from=paste&height=410&id=ud57e4e63&margin=%5Bobject%20Object%5D&name=image.png&originHeight=819&originWidth=1467&originalType=binary&ratio=1&size=338004&status=done&style=none&taskId=u65fd653c-5948-411a-9c83-2b7a832584d&width=733.5)
<a name="jn4xW"></a>
## CJS
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643175000054-039a59d7-467d-4035-8a76-e47a11dff85f.png#clientId=u1c9a604e-2b1d-4&from=paste&height=391&id=u629dbddd&margin=%5Bobject%20Object%5D&name=image.png&originHeight=782&originWidth=1466&originalType=binary&ratio=1&size=295344&status=done&style=none&taskId=u46d4ff04-a5bc-4cac-b884-8a853017c1f&width=733)
<a name="xwzAj"></a>
### exports
exports的存在是为了符合cjs的规范，node本质导出的是module.exports<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643182782822-26efa22e-e682-443e-95a3-f74d307190d9.png#clientId=u1c9a604e-2b1d-4&from=paste&height=404&id=ua83781e6&margin=%5Bobject%20Object%5D&name=image.png&originHeight=808&originWidth=1272&originalType=binary&ratio=1&size=270160&status=done&style=none&taskId=u3b5cdaee-dbfe-4945-a4b6-0bfe7980e20&width=636)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643183199657-a4534c5c-4c40-4ba0-8853-44491e793b03.png#clientId=u1c9a604e-2b1d-4&from=paste&height=89&id=u1b0a8ffe&margin=%5Bobject%20Object%5D&name=image.png&originHeight=177&originWidth=219&originalType=binary&ratio=1&size=18329&status=done&style=none&taskId=u8c7f5f03-e71a-47d1-8162-60324b206d5&width=109.5)<br />以上直接改变exports的指向<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643183280743-1b15b637-8307-4284-9643-d9684f66b7c4.png#clientId=u1c9a604e-2b1d-4&from=paste&height=96&id=u1e9f1cf4&margin=%5Bobject%20Object%5D&name=image.png&originHeight=192&originWidth=256&originalType=binary&ratio=1&size=34273&status=done&style=none&taskId=ub8c816e9-d3b2-477c-b5f4-d6dfc66faba&width=128)<br />以上也是没有导出的<br />根本原因：源码实现如下<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643183311802-f54820b0-49c9-480a-8853-f0f5bd333460.png#clientId=u1c9a604e-2b1d-4&from=paste&height=36&id=ub1c0a7c9&margin=%5Bobject%20Object%5D&name=image.png&originHeight=71&originWidth=238&originalType=binary&ratio=1&size=20525&status=done&style=none&taskId=uf1be202c-6562-4ec2-8815-122cd553351&width=119)
<a name="tVw5I"></a>
### module.exports
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643182801809-e674a39f-1428-46f7-ae40-2de017c25a14.png#clientId=u1c9a604e-2b1d-4&from=paste&height=401&id=ua114dcb7&margin=%5Bobject%20Object%5D&name=image.png&originHeight=802&originWidth=1431&originalType=binary&ratio=1&size=220091&status=done&style=none&taskId=ua1ac1522-88e9-432b-b014-9f22647a831&width=715.5)
<a name="O9Ob8"></a>
### require
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643183648127-a169f70d-7c8c-46cd-a621-1cfa51f2098b.png#clientId=u1c9a604e-2b1d-4&from=paste&height=353&id=u0e59b1b9&margin=%5Bobject%20Object%5D&name=image.png&originHeight=706&originWidth=1271&originalType=binary&ratio=1&size=138475&status=done&style=none&taskId=u4a48baf2-8640-4a99-bdd0-f87f72b4f96&width=635.5)<br />[https://nodejs.org/dist/latest-v14.x/docs/api/modules.html](https://nodejs.org/dist/latest-v14.x/docs/api/modules.html)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643183818959-d82a373d-0d9d-4f06-96fd-b2f47f1a97b0.png#clientId=u1c9a604e-2b1d-4&from=paste&height=405&id=u7963cd2b&margin=%5Bobject%20Object%5D&name=image.png&originHeight=809&originWidth=992&originalType=binary&ratio=1&size=148993&status=done&style=none&taskId=u7d320731-4a6f-442e-aefc-36da365086c&width=496)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643184229723-0d2fcd04-287c-47ae-b6ed-f117eb4c3831.png#clientId=u1c9a604e-2b1d-4&from=paste&height=265&id=u1fe6143b&margin=%5Bobject%20Object%5D&name=image.png&originHeight=530&originWidth=1479&originalType=binary&ratio=1&size=232751&status=done&style=none&taskId=u211a199a-7e5f-4eda-b2a7-4885212e95f&width=739.5)
<a name="B8Jqm"></a>
### 模块加载过程
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643184582758-8931e18a-f432-4851-9190-72e5bb220422.png#clientId=u1c9a604e-2b1d-4&from=paste&height=396&id=ued9c7f2f&margin=%5Bobject%20Object%5D&name=image.png&originHeight=791&originWidth=1471&originalType=binary&ratio=1&size=384214&status=done&style=none&taskId=u4dae0edc-2815-4be6-ac0e-3b73d4d69ac&width=735.5)<br />每一个js文件相当于一个module实例，每一个module实例里面有一个loaded属性，默认为false，加载一次后变为true
<a name="WHMjU"></a>
### cjs缺点
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643185023652-67bcd334-eb0e-4513-ba03-379383daa53e.png#clientId=u1c9a604e-2b1d-4&from=paste&height=403&id=ub00d04bf&margin=%5Bobject%20Object%5D&name=image.png&originHeight=806&originWidth=1466&originalType=binary&ratio=1&size=287848&status=done&style=none&taskId=u8a1919f5-3122-40d7-9ca9-d9948ab79cc&width=733)<br />node的代码执行是同步的，node是跑在服务器环境中的，很少会出现cjs通过引用其他服务器的资源，引用的文件都是本地服务器的，如果使用的是不同功能部署到不同服务器，那么使用的是http请求，socket和axios等等<br />同步的方式会造成阻塞，在前端（浏览器中）不适合，当然也有一些能实现异步加载的的库，例如Browserify<br />webpack中配置使用cjs，搭建项目也可以用cjs/esmodule/amd/cmd因为webpack都可以将这些代码转换为浏览器可以识别的代码
<a name="dRD3x"></a>
## AMD CMD
<a name="P9Ain"></a>
### AMD（社区存在规范/非官方）
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643185866038-2e1de1be-d442-4fc2-ac30-a75da2e2d9fd.png#clientId=u1c9a604e-2b1d-4&from=paste&height=269&id=u971f32f3&margin=%5Bobject%20Object%5D&name=image.png&originHeight=538&originWidth=1415&originalType=binary&ratio=1&size=147649&status=done&style=none&taskId=u99ca3c0f-f293-4016-b58d-73834570fd9&width=707.5)
<a name="bL8vs"></a>
#### require.js
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643185960212-9485d3d1-fed5-4437-99ee-54526cce0aa6.png#clientId=u1c9a604e-2b1d-4&from=paste&height=386&id=u533d3253&margin=%5Bobject%20Object%5D&name=image.png&originHeight=772&originWidth=1446&originalType=binary&ratio=1&size=423180&status=done&style=none&taskId=uaa4f635f-694e-4179-87f8-ea2e909aea6&width=723)
<a name="yoads"></a>
### CMD![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643187046718-f0111100-1042-4770-a38a-a89f698b2626.png#clientId=u1c9a604e-2b1d-4&from=paste&height=283&id=u8b2185f2&margin=%5Bobject%20Object%5D&name=image.png&originHeight=566&originWidth=1008&originalType=binary&ratio=1&size=101021&status=done&style=none&taskId=udc0c077c-90ce-4459-a811-5968f869207&width=504)
<a name="WELRE"></a>
####  SeaJS  
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643187074572-49d51959-5a73-498a-aedf-92cea4b03095.png#clientId=u1c9a604e-2b1d-4&from=paste&height=393&id=uc2a58bf9&margin=%5Bobject%20Object%5D&name=image.png&originHeight=785&originWidth=1323&originalType=binary&ratio=1&size=455038&status=done&style=none&taskId=ucb42c3dc-a7c1-4dca-81e0-ff80fb81738&width=661.5)
<a name="GZON7"></a>
## Es Module
<a name="Q82In"></a>
### 基本
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643202588333-ccf6ae71-90e2-4dc2-b2b4-d692925283a1.png#clientId=u1c9a604e-2b1d-4&from=paste&height=406&id=u94142acd&margin=%5Bobject%20Object%5D&name=image.png&originHeight=811&originWidth=1455&originalType=binary&ratio=1&size=238632&status=done&style=none&taskId=u2d22c19b-d963-4f51-8e72-68e13269ae7&width=727.5)
<a name="YBKBn"></a>
### 注意事项
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643269870603-ba7f7113-1809-4622-82de-92cb2c11544e.png#clientId=u1c9a604e-2b1d-4&from=paste&height=399&id=u24721827&margin=%5Bobject%20Object%5D&name=image.png&originHeight=798&originWidth=1459&originalType=binary&ratio=1&size=525170&status=done&style=none&taskId=uc28ce599-99e3-4868-9fde-701930e3469&width=729.5)<br />需要加上type属性，如果不加浏览器将会将其当成一个普通的js来是执行，而不是一个模块、<br />file文件协议不能加载模块，需要http或者https协议才可以加载模块，因此可以使用live server开启一个本地服务
<a name="bbhTW"></a>
### exports关键字
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643270212560-a5d5bd53-73d3-4d7b-9f7f-e255ff1fea5c.png#clientId=u1c9a604e-2b1d-4&from=paste&height=328&id=u7575da14&margin=%5Bobject%20Object%5D&name=image.png&originHeight=655&originWidth=1138&originalType=binary&ratio=1&size=145759&status=done&style=none&taskId=u560a6fd4-3227-4175-9df8-53c5c491e90&width=569)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643270585811-72406ece-c84b-4414-bc2d-eeadb392bc01.png#clientId=u1c9a604e-2b1d-4&from=paste&height=125&id=udb11de91&margin=%5Bobject%20Object%5D&name=image.png&originHeight=249&originWidth=321&originalType=binary&ratio=1&size=65723&status=done&style=none&taskId=u7f86abe9-54e8-4c05-be2e-cbe3a312558&width=160.5)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643270556479-46d908c2-1208-45fa-bdc2-71a6a441766a.png#clientId=u1c9a604e-2b1d-4&from=paste&height=160&id=u9a4d73be&margin=%5Bobject%20Object%5D&name=image.png&originHeight=319&originWidth=376&originalType=binary&ratio=1&size=61452&status=done&style=none&taskId=ub8950108-9f08-4929-87bc-164af24a1cd&width=188)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643270609987-d5a7d136-2383-4427-951f-a8da567bded9.png#clientId=u1c9a604e-2b1d-4&from=paste&height=90&id=u12b86309&margin=%5Bobject%20Object%5D&name=image.png&originHeight=180&originWidth=344&originalType=binary&ratio=1&size=37477&status=done&style=none&taskId=ue897ca94-1dca-4618-a682-8883e7c21e7&width=172)
<a name="Z9c2X"></a>
### import关键字
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643270689536-ab0184cc-8361-45e1-86d1-192ac28fddf3.png#clientId=u1c9a604e-2b1d-4&from=paste&height=315&id=u2fd3abd7&margin=%5Bobject%20Object%5D&name=image.png&originHeight=630&originWidth=1036&originalType=binary&ratio=1&size=115407&status=done&style=none&taskId=ud364659e-e604-4d3d-96e4-aebf63d28f0&width=518)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643270682511-1a2960ba-0ddf-4242-86a1-982ff756c3b5.png#clientId=u1c9a604e-2b1d-4&from=paste&height=56&id=ua95aacea&margin=%5Bobject%20Object%5D&name=image.png&originHeight=112&originWidth=465&originalType=binary&ratio=1&size=44305&status=done&style=none&taskId=ucea0f351-020a-419a-89ea-47764d65dab&width=232.5)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643270731844-f396cd9e-8075-4fb0-ad32-7a00d301ad95.png#clientId=u1c9a604e-2b1d-4&from=paste&height=39&id=u96018aa4&margin=%5Bobject%20Object%5D&name=image.png&originHeight=77&originWidth=669&originalType=binary&ratio=1&size=34220&status=done&style=none&taskId=u62d7e749-5254-444a-88f0-6f815a69aa9&width=334.5)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643270799518-3699d2d5-a127-41d9-a17a-27cb2dab7d8b.png#clientId=u1c9a604e-2b1d-4&from=paste&height=112&id=ucc99c6fd&margin=%5Bobject%20Object%5D&name=image.png&originHeight=223&originWidth=435&originalType=binary&ratio=1&size=58812&status=done&style=none&taskId=u2ce2bf4d-36a8-4e3d-808d-2b1eadf62d7&width=217.5)
<a name="qiESq"></a>
###  export和import结合使用  （统一出口文件）

<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643271289486-3fedbf8a-be36-4374-818c-388101f8bfc1.png#clientId=u1c9a604e-2b1d-4&from=paste&height=292&id=uf0d338f8&margin=%5Bobject%20Object%5D&name=image.png&originHeight=583&originWidth=1222&originalType=binary&ratio=1&size=152829&status=done&style=none&taskId=u97324ada-ee07-433d-b1cd-867f4ee3e26&width=611)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643271389889-568062fd-361a-4cc6-8f92-116cebe7c17e.png#clientId=u1c9a604e-2b1d-4&from=paste&height=312&id=u940417fe&margin=%5Bobject%20Object%5D&name=image.png&originHeight=624&originWidth=832&originalType=binary&ratio=1&size=165464&status=done&style=none&taskId=u626b3279-142c-4236-a02c-84f0d3dc20e&width=416)
<a name="oCaRw"></a>
### default
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643271560881-c38f0d08-d00f-4b50-9ff2-7779ac6fcf05.png#clientId=u1c9a604e-2b1d-4&from=paste&height=364&id=u82c78a8d&margin=%5Bobject%20Object%5D&name=image.png&originHeight=728&originWidth=1143&originalType=binary&ratio=1&size=145870&status=done&style=none&taskId=u3962c91c-ed7a-4f3c-b840-201f9f62b3a&width=571.5)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643271609063-9de8eb30-edce-48bb-bebe-23b29a708817.png#clientId=u1c9a604e-2b1d-4&from=paste&height=177&id=uca1a5665&margin=%5Bobject%20Object%5D&name=image.png&originHeight=353&originWidth=339&originalType=binary&ratio=1&size=69888&status=done&style=none&taskId=u0f103e7e-0f51-4c27-ab43-a582f619f58&width=169.5)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643271650847-402a8e77-c243-4ceb-b50e-2593fc9b6b86.png#clientId=u1c9a604e-2b1d-4&from=paste&height=66&id=u3699fdfc&margin=%5Bobject%20Object%5D&name=image.png&originHeight=132&originWidth=294&originalType=binary&ratio=1&size=28982&status=done&style=none&taskId=u2ba7234a-7076-41de-8bf1-390066a8c00&width=147)
<a name="rXS3M"></a>
### import函数
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643271880398-ec0853c9-8764-4d83-b5f6-fa47bb93f5f6.png#clientId=u1c9a604e-2b1d-4&from=paste&height=418&id=u25f8886b&margin=%5Bobject%20Object%5D&name=image.png&originHeight=835&originWidth=1394&originalType=binary&ratio=1&size=385117&status=done&style=none&taskId=u2085fa24-ff65-4d0b-bfea-09c183ae9cc&width=697)<br />通过普通import关键字导入模块相当于同步代码，因此要等到模块加载完成才能执行下面的代码，这样会造成阻塞，因此可以通过import函数来异步：import函数返回一个promise对象，当文件加载完成后内部会自动执行resolve，所以我们可以设置相对应的回调函数<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643273623937-6ad221a0-9f31-4190-bf23-c3c41f663641.png#clientId=u1c9a604e-2b1d-4&from=paste&height=185&id=u4dd15ecb&margin=%5Bobject%20Object%5D&name=image.png&originHeight=370&originWidth=1079&originalType=binary&ratio=1&size=68827&status=done&style=none&taskId=ud47115c1-994d-40d2-b8c4-17f2d4a6082&width=539.5)
<a name="TJn3J"></a>
### meta
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643273653898-28eb6f7b-b531-44ad-a853-d2422fd38c20.png#clientId=u1c9a604e-2b1d-4&from=paste&height=43&id=u27ab6cc1&margin=%5Bobject%20Object%5D&name=image.png&originHeight=86&originWidth=355&originalType=binary&ratio=1&size=25851&status=done&style=none&taskId=ubc47933b-2778-43d8-acba-6285f0264cc&width=177.5)
<a name="OKmAD"></a>
### 原理
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643274452193-093842af-cdbc-4337-90c9-dd6b1b1693f7.png#clientId=u1c9a604e-2b1d-4&from=paste&height=406&id=uded82809&margin=%5Bobject%20Object%5D&name=image.png&originHeight=812&originWidth=1559&originalType=binary&ratio=1&size=461219&status=done&style=none&taskId=uf93de618-ca4c-40de-b015-47228aa6b74&width=779.5)
<a name="FCBWO"></a>
#### 构建
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643274599831-c548f7bb-9b88-467d-bdce-cfc7d4b9cf37.png#clientId=u1c9a604e-2b1d-4&from=paste&height=417&id=u945a28f7&margin=%5Bobject%20Object%5D&name=image.png&originHeight=833&originWidth=1497&originalType=binary&ratio=1&size=773722&status=done&style=none&taskId=u98009afe-603a-4baf-a70c-362fb6e0e26&width=748.5)<br />根据地向服务器请求到main.js文件，然后做静态解析（只会解析那些import和export语句，并不会执行具体的代码（这也是不能将import和export写道条件判断中的原因），然后生成module record的数据结构，然后再去下载相关依赖的其他模块<br />内部专门有一个module map记录相关缓存，已经加载过的就会被记录下来，避免重复加载
<a name="VmhTL"></a>
#### 实例化 求值
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643275626542-08c47795-1a7c-4ce5-bd9d-64a702dbe1e2.png#clientId=u1c9a604e-2b1d-4&from=paste&height=419&id=u922521df&margin=%5Bobject%20Object%5D&name=image.png&originHeight=838&originWidth=1565&originalType=binary&ratio=1&size=896485&status=done&style=none&taskId=u5283432f-34d8-43dd-876e-a33dfcea144&width=782.5)<br />实例化阶段：在module record中，导出的内容对应bindings，导入的内容对应importentries。然后进行实例化（类似于类），生成module environment record，并分配对应的内存（此时还没有动态执行对应的代码），因此内存中的数据还是undefined<br />求值阶段: 动态执行代码，然后给内存中赋值
<a name="jiYnb"></a>
## EsModule和cjs的相互结合
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643276044716-79e815cf-4af3-42ca-b6c9-ed516c0f316a.png#clientId=u1c9a604e-2b1d-4&from=paste&height=334&id=u08d22bd4&margin=%5Bobject%20Object%5D&name=image.png&originHeight=668&originWidth=1111&originalType=binary&ratio=1&size=252193&status=done&style=none&taskId=ud6a27caa-25a0-4c83-959d-31b9186809a&width=555.5)<br />在平时开发环境（也就是webpack）是可以导入导出相互结合的
<a name="ZxRr8"></a>
# JSON
<a name="Ljwtl"></a>
## 概述
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643378407086-e01c5a1e-5d03-47c2-94b9-5c3f120461e7.png#clientId=u88af228c-025e-4&from=paste&height=362&id=ud1b9ad9b&margin=%5Bobject%20Object%5D&name=image.png&originHeight=723&originWidth=1542&originalType=binary&ratio=1&size=292948&status=done&style=none&taskId=u98fdf3aa-addc-43b5-8c46-29e6781f091&width=771)
<a name="FV3eh"></a>
## 基本用法
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643385317074-842d5a8c-5e99-411f-ae5e-09d0bd312702.png#clientId=u88af228c-025e-4&from=paste&height=398&id=uc966a582&margin=%5Bobject%20Object%5D&name=image.png&originHeight=795&originWidth=1559&originalType=binary&ratio=1&size=268934&status=done&style=none&taskId=u2e80cefa-f683-4b79-ab55-4bde95854b4&width=779.5)
<a name="BTKtr"></a>
## JSON序列化
<a name="AoPP5"></a>
### 基本
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643385347936-55494c55-74f5-44ea-b1cc-c7e2dbb4baae.png#clientId=u88af228c-025e-4&from=paste&height=421&id=u3d04ce07&margin=%5Bobject%20Object%5D&name=image.png&originHeight=842&originWidth=1573&originalType=binary&ratio=1&size=307285&status=done&style=none&taskId=u0be2f1bf-02a4-4988-ba63-9a8d4f6724a&width=786.5)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643385380421-35230344-9c8b-4842-a022-5837d5b4d8b9.png#clientId=u88af228c-025e-4&from=paste&height=397&id=u3265eef4&margin=%5Bobject%20Object%5D&name=image.png&originHeight=794&originWidth=1076&originalType=binary&ratio=1&size=343728&status=done&style=none&taskId=u806b4c2f-f104-48a9-a93d-91be6f28a01&width=538)
<a name="FXjBB"></a>
### stringify
<a name="MWg8E"></a>
#### replace
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643385625234-3f970397-ce65-4719-bc13-947d42270d29.png#clientId=u88af228c-025e-4&from=paste&height=420&id=ufeceb0b9&margin=%5Bobject%20Object%5D&name=image.png&originHeight=839&originWidth=1202&originalType=binary&ratio=1&size=362192&status=done&style=none&taskId=u3b183979-6f5a-4dba-a03b-bc67b207373&width=601)
<a name="ksaJs"></a>
#### place
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643385784344-c9a264f4-c08a-4785-be2e-a10b469272e7.png#clientId=u88af228c-025e-4&from=paste&height=416&id=u9589cf14&margin=%5Bobject%20Object%5D&name=image.png&originHeight=831&originWidth=1421&originalType=binary&ratio=1&size=436999&status=done&style=none&taskId=ua593d7cb-550c-4f84-a025-9846ed65875&width=710.5)
<a name="PDtx0"></a>
### parse

<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643385952332-08142edb-fda9-402d-811f-f17e90c3de88.png#clientId=u88af228c-025e-4&from=paste&height=346&id=ua0ebf4ec&margin=%5Bobject%20Object%5D&name=image.png&originHeight=691&originWidth=1249&originalType=binary&ratio=1&size=245573&status=done&style=none&taskId=u5577d5f8-b72f-43ee-85ac-437261bbbc5&width=624.5)
<a name="hFdi5"></a>
### 序列化实现深拷贝
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643441199148-6114ecad-cdf0-4f29-8251-c78850a6b12b.png#clientId=ufe5fe6f9-13fb-4&from=paste&height=391&id=u71d1e1c4&margin=%5Bobject%20Object%5D&name=image.png&originHeight=782&originWidth=1344&originalType=binary&ratio=1&size=341074&status=done&style=none&taskId=uda913ea2-6f83-4179-8f3a-ff9ba402615&width=672)
<a name="ski0j"></a>
# Storge
<a name="bn0Ix"></a>
## 基本
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643441473428-825173a0-d6ba-4c5b-ab31-cd59fe488871.png#clientId=u14fc2787-5f6c-4&from=paste&height=408&id=u7823aa29&margin=%5Bobject%20Object%5D&name=image.png&originHeight=816&originWidth=1446&originalType=binary&ratio=1&size=365048&status=done&style=none&taskId=u93b87feb-d8f6-4b8a-acdc-ddd47a6f77b&width=723)
<a name="RgWoq"></a>
## 区别
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643442039235-f8a0fe61-33cd-46f2-b685-2d7ac555b2d7.png#clientId=u14fc2787-5f6c-4&from=paste&height=254&id=ue6562e1e&margin=%5Bobject%20Object%5D&name=image.png&originHeight=508&originWidth=1442&originalType=binary&ratio=1&size=148104&status=done&style=none&taskId=u24941b00-9a91-4555-8185-74af8152f5e&width=721)
<a name="MnpHE"></a>
## 常见方法和属性
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643442410870-229312b2-120f-4a68-b234-97d6f5f6fb52.png#clientId=u14fc2787-5f6c-4&from=paste&height=395&id=u7a8cf765&margin=%5Bobject%20Object%5D&name=image.png&originHeight=790&originWidth=1297&originalType=binary&ratio=1&size=216601&status=done&style=none&taskId=uf879915f-bb67-4966-9427-35d4165ee3d&width=648.5)
<a name="Z7cuD"></a>
## 封装storge
![image.png](https://cdn.nlark.com/yuque/0/2022/png/10362360/1643443032807-3484aa71-313f-41ae-b6d9-857df9f7c68d.png#clientId=u14fc2787-5f6c-4&from=paste&height=407&id=u90d6612c&margin=%5Bobject%20Object%5D&name=image.png&originHeight=813&originWidth=1451&originalType=binary&ratio=1&size=467846&status=done&style=none&taskId=u07f93fd4-2362-46a2-8d17-7bc26608108&width=725.5)
<a name="XgoFq"></a>
# ​<br />


