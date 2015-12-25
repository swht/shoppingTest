# shoppingTest 
说明：这是本人在学习python的过程中的练习代码，代码多有不足，请多多指教。
测试账号：二手交易：shen1234 123456 信用卡交易中心：1018584989 123456

实现功能：

	1. 南非波波小屋两大功能：二手数码交易中心、信用卡交易中心
	2. 二手数码交易中心：模拟购物平台的流程，实现对商品的添加、结算、查询等；
	3. 信用卡交易中心：实现查询余额、交易记录、转账、还款、购物支付的功能；

不足：

	1.购物车这边没有删减商品的功能；信用卡交易这边没有做用户的管理、已经转账用户的交易记录；
	2.大量代码冗余；
	3.缺少面向对象编程的思想；

总结：

	1.在练习过程中，使用代码`linecache.getline(filename,linenum)`获取文件的某一行数据时，没有使用`linecache.clearcache()`做缓存清除处理，导致测试的过程中，第一次功能可以实现，重新测试就会报错。原来`linecache.getline()`主要的机制就是使数据缓存化，方便后面的数据调用，但是如果在一个程序中出现多次调用同一个参数的时候，并且该参数的值会增加，那么缓存的值就会影响程序的判断，所以在每次调用之前都要进行缓存数据的清除工作；
	2.由于第1条内容的导致，我一直以为是在处理文件的时候没有及时将数据刷新。有这个怀疑查询了一番：
	文件在f.close()的时候会自动调用内部的flush机制函数，现将缓存中的数据保存到文件（硬盘）中，然后在执行关闭文件的操作。这种机制的好处就是很好的支持数据的完整性。所以在对文件的处理中要注意按照下面的格式：
	    	f = open(filename,cmd)
    		f.write(list)
    		f.close()

流程图：
![信用卡流程图](http://i.imgur.com/drv0WXb.jpg)