# 维度
创建数据   
np.array()  
array.ndim  
添加数据  
np.concatenate()  
np.expand_dims()  
合并数据  
np.concatenate()  
np.vstack()  
np.hstack()  
观察形态  
array.size  
array.shape  


一维
import numpy as np  

cars = np.array([5, 10, 12, 6])  
print("数据：", cars, "\n维度：", cars.ndim)  
结果  
数据： [ 5 10 12  6]   
维度： 1  


二维    
cars = np.array([  
[5, 10, 12, 6],  
[5.1, 8.2, 11, 6.3],  
[4.4, 9.1, 10, 6.6]  
])  

print("数据：\n", cars, "\n维度：", cars.ndim)  
