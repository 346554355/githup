# 一、ndarray
## 1.ndarray的特性
### 多维性


```python
import numpy as np
```


```python
arr = np.array(5) # 创建0维度的ndarray数组
print(arr)
print('arr的维度:',arr.ndim)  # 数组的维度number of dimensions   arr
print('数组的形状:',arr.shape)
print('元素的个数:',arr.size)
print('元素的数据类型',arr.dtype)
```

    5
    arr的维度: 0
    数组的形状: ()
    元素的个数: 1
    元素的数据类型 int64
    


```python
arr = np.array([1,2,3])  # 创建1维度的ndarray数组    arr
print(arr)
print('数组的维度:',arr.ndim)  # 数组的维度number of dimensions
print('数组的形状:',arr.shape)
print('元素的个数:',arr.size)
print('元素的数据类型',arr.dtype)
```

    [1 2 3]
    数组的维度: 1
    数组的形状: (3,)
    元素的个数: 3
    元素的数据类型 int64
    


```python
arr = np.array([[1,2,3],[4,5,6]])  # 创建2维度的ndarray数组    arr
print(arr)
print('数组的维度:',arr.ndim)   # 数组的维度number of dimensions
print('数组的形状:',arr.shape)
print('元素的个数:',arr.size)
print('元素的数据类型',arr.dtype)
```

    [[1 2 3]
     [4 5 6]]
    数组的维度: 2
    数组的形状: (2, 3)
    元素的个数: 6
    元素的数据类型 int64
    

### 同质性


```python
arr = np.array([1,"hello"])  # 不同的数据类型会被强制转换成相同的数据类型
print(arr)
print('arr的维度:',arr.ndim)
print('数组的形状:',arr.shape)
print('元素的个数:',arr.size)
print('元素的数据类型',arr.dtype)
```

    ['1' 'hello']
    arr的维度: 1
    数组的形状: (2,)
    元素的个数: 2
    元素的数据类型 <U21
    


```python
arr = np.array([1,2.5])    #  不同的数据类型会被强制转换成相同的数据类型
print(arr)
print('arr的维度:',arr.ndim)
print('数组的形状:',arr.shape)
print('元素的个数:',arr.size)
print('元素的数据类型',arr.dtype)
```

    [1.  2.5]
    arr的维度: 1
    数组的形状: (2,)
    元素的个数: 2
    元素的数据类型 float64
    

## 2.ndarray的属性


```python
arr = np.array(1)
print(arr)
print('数组的形状:',arr.shape)
print('数组的维度:',arr.ndim)
print('数组元素的个数:',arr.size)
print('元素的数据类型:',arr.dtype)
print('元素的转置:',arr.T)
```

    1
    数组的形状: ()
    数组的维度: 0
    数组元素的个数: 1
    元素的数据类型: int64
    元素的转置: 1
    


```python
arr = np.array([1,2.5,3])
print(arr)
print('数组的形状:',arr.shape)
print('数组的维度:',arr.ndim)
print('数组元素的个数:',arr.size)
print('元素的数据类型:',arr.dtype)
print('元素的转置:',arr.T)
```

    [1.  2.5 3. ]
    数组的形状: (3,)
    数组的维度: 1
    数组元素的个数: 3
    元素的数据类型: float64
    元素的转置: [1.  2.5 3. ]
    


```python
arr = np.array([[1,2,3],[4,5,6]])
print(arr)
print('数组的形状:',arr.shape)
print('数组的维度:',arr.ndim)
print('数组元素的个数:',arr.size)
print('元素的数据类型:',arr.dtype)
print('元素的转置:',arr.T)
```

    [[1 2 3]
     [4 5 6]]
    数组的形状: (2, 3)
    数组的维度: 2
    数组元素的个数: 6
    元素的数据类型: int64
    元素的转置: [[1 4]
     [2 5]
     [3 6]]
    

## 3.ndarray的创建


```python
#基础的创建方法
list1 = [4,5,6]
arr = np.array(list1,dtype=np.float64)   # 强制转换为浮点数
print(arr.ndim)    # 属性
print(arr)
```

    1
    [4. 5. 6.]
    


```python
# copy
arr1 = np.copy(arr)   # 复制上面的arr,元素跟原始的数组相同，但是不是同一个数组了
print(arr1)
arr1[0] = 8   # 修改arr1第一个数值4改为8
print(arr1)
print(arr)    # 不会改变arr的数值
```

    [4. 5. 6.]
    [8. 5. 6.]
    [4. 5. 6.]
    


```python
# 预定义形状
# 全0  全1  未初始化  固定值
# 全0
arr = np.zeros((2,3))  # 创建一个2行3列的
print(arr) 
print(arr.dtype)
```

    [[0. 0. 0.]
     [0. 0. 0.]]
    float64
    


```python
arr = np.zeros((20,),dtype=int)  
print(arr) 
```

    [0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0]
    


```python
# 全1
arr = np.ones((5,8),dtype=int)  
print(arr) 
```

    [[1 1 1 1 1 1 1 1]
     [1 1 1 1 1 1 1 1]
     [1 1 1 1 1 1 1 1]
     [1 1 1 1 1 1 1 1]
     [1 1 1 1 1 1 1 1]]
    


```python
# 未初始化
arr = np.empty((4,3))
print(arr)
```

    [[1.18576667e-311 2.81617418e-322 0.00000000e+000]
     [0.00000000e+000 1.42417221e-306 1.58817677e-052]
     [6.81640086e-091 5.39744910e-062 1.52471910e-052]
     [2.95005410e+179 6.48224659e+170 4.93432906e+257]]
    


```python
# 固定值
arr = np.full((3,4),2025)
print(arr)
```

    [[2025 2025 2025 2025]
     [2025 2025 2025 2025]
     [2025 2025 2025 2025]]
    


```python
# 像某个形状
arr1 = np.zeros_like(arr)
print(arr1)
arr1 = np.empty_like(arr)
print(arr1)
arr1 = np.ones_like(arr)
print(arr1)
arr1 = np.full_like(arr,2026)
print(arr1)
```

    [[0 0 0 0]
     [0 0 0 0]
     [0 0 0 0]]
    [[      2400018452632                  64                   0
                        0]
     [                  0 3763099871435174758 7148399420598478137
      7076335010548430130]
     [3978761183173817650 3546080264359916086 7306020808535729207
      3907264335637000504]]
    [[1 1 1 1]
     [1 1 1 1]
     [1 1 1 1]]
    [[2026 2026 2026 2026]
     [2026 2026 2026 2026]
     [2026 2026 2026 2026]]
    


```python
# 等差数列 1 2 3 4 5
arr = np.arange(1,12,2)   # 1代表开始(start)  12代表结束(end)  2代表步长(step)
print(arr)
arr = np.arange(2,12,3)   # 2代表开始(start)  12代表结束(end)  3代表步长(step)
print(arr)
arr = np.arange(1,50,5)   # 1代表开始(start)  50代表结束(end)  5代表步长(step)
print(arr)
```

    [ 1  3  5  7  9 11]
    [ 2  5  8 11]
    [ 1  6 11 16 21 26 31 36 41 46]
    


```python
# 等间隔数列
arr = np.linspace(0,10,3)  # 0代表开始(start)  10代表结束(end)  3代表个数
print(arr)

```

    [ 0.  5. 10.]
    


```python
# 练习
arr = np.linspace(0,100,5,dtype=int)  # 0代表开始(start)  100代表结束(end)  5代表个数
print(arr)
arr = np.arange(0,101,25)   # 0代表开始(start)  100代表结束(end)  5代表个数
print(arr)
```

    [  0  25  50  75 100]
    [  0  25  50  75 100]
    


```python
# 对数间隔列
arr = np.linspace(0,4,3)   # 计算结果
print(arr)
arr = np.logspace(0,4,3,base=2)  # 通过上面的计算结果在进行计算
print(arr)
arr = np.logspace(0,4,3)   # 得出结果是结果的几次方
print(arr)
```

    [0. 2. 4.]
    [ 1.  4. 16.]
    [1.e+00 1.e+02 1.e+04]
    


```python
# 特殊矩阵
# 单位矩阵:主对角线上的数字为1，其他的数字为0
arr = np.eye(3,4,dtype=int)  # 创建3行4列的整数矩阵
print(arr)
```

    [[1 0 0 0]
     [0 1 0 0]
     [0 0 1 0]]
    


```python
# 对角矩阵:主对角线上非零的数字为0，其他的数字为0
arr = np.diag([1,2,3])  # 创建对角线的数字为1,2,3,其他数字为0
print(arr)
arr1 = np.diag([5,1,2,3])  # 创建对角线的数字为5,1,2,3，其他数字为0
print(arr1)
```

    [[1 0 0]
     [0 2 0]
     [0 0 3]]
    [[5 0 0 0]
     [0 1 0 0]
     [0 0 2 0]
     [0 0 0 3]]
    


```python
# 随机数组的生成
# 生成0-1之间的浮点数(均匀分布)
arr = np.random.rand(2,3)    # 创建2行3列的随机数组范围为0-1,数值为浮点数
print(arr)

```

    [[0.44392677 0.33148596 0.19556527]
     [0.42396585 0.60417472 0.77916287]]
    


```python
# 生成指定范围区间的随机浮点数
arr = np.random.uniform(3,6,(2,3))  # 创建2行3列的数组范围为3-6之间，数值为浮点数
print(arr)
```

    [[5.74127583 5.55108646 4.86374285]
     [4.75312686 4.88666023 3.07427767]]
    


```python
# 生成指定范围区间的随机整数
arr = np.random.randint(3,10,(2,3))  # 创建2行3列的数组范围为3-10之间，数值为整数
print(arr)
```

    [[5 4 4]
     [5 7 8]]
    


```python
# 生成随机整数(正态分布),意思就是两边小，中间大(-3到3之间)
arr = np.random.randn(2,3)
print(arr)
```

    [[ 1.29279458 -1.15162393 -1.02653891]
     [-0.80963927  0.80674975 -0.36640002]]
    


```python
# 设置随机种子
np.random.seed(20)
arr = np.random.randint(1,10,(2,5))  # 创建2行5列的数组范围为1-10之间，数值为整数
print(arr)
```

    [[4 5 7 8 3]
     [1 7 9 6 4]]
    

## 4.ndarray的数据类型
###  布尔类型  bool
### 整点类型 int uint
### 浮点数 float
### 复数 complex


```python
import numpy as np
arr = np.array([1,0,129,0],dtype=np.uint)
print(arr)
```

    [  1   0 129   0]
    

## 5.ndarray的索引与切片
### 1维数组的索引与切片


```python
import numpy as np
arr = np.random.randint(1,100,20)  # 随机生成1-100的数组，个数为20个
print(arr)
```

    [47 60 71 98 24 11 68 90 23 30 13 50 88 35 92 70 87 29 71 62]
    


```python
print(arr[0])   # 打印第一个数据，0代表第一个
```

    47
    


```python
print(arr[:])   # 获取全部的数据
```

    [47 60 71 98 24 11 68 90 23 30 13 50 88 35 92 70 87 29 71 62]
    


```python
print(arr[2:5])  # 获取第三3到第5个个数据，也就是开始第一个数据是2+1，结束是5，切片的时候记得是左边加1，右边不加
```

    [71 98 24]
    


```python
print(arr[slice(2,15,3)])   # 获取第3个到第15个，隔3个获取一个
```

    [71 11 23 50 92]
    


```python
print(arr[arr>10])  # 获取大于10的数据，也就是布尔索引
```

    [47 60 71 98 24 11 68 90 23 30 13 50 88 35 92 70 87 29 71 62]
    


```python
print(arr[(arr>10) & (arr<30)])  # 获取大于10或小于30的数据，也就是布尔索引
```

    [24 11 23 13 29]
    

### 2维数组的索引与切片


```python
arr = np.random.randint(1,100,(4,8))  # 随机生成4行8列1-100的数组
print(arr)
```

    [[12 73 91 29 68  9 73 23]
     [94 60 71 59 48 30 26 99]
     [26 36 40 66 12 31 81 73]
     [30 20  1 25 97 33 58 38]]
    


```python
print(arr[2,3])  # 精确索引，获取第3行第4个数据，代码的第一个是0，所以记得加1就行
```

    66
    


```python
print(arr[1,2:5])  # 获取第2行第3个到第5个的数据，切片的时候记得是左边加1，右边不加
```

    [71 59 48]
    


```python
print(arr[arr>50])  # 获取大于50的数据
```

    [73 91 68 73 94 60 71 59 99 66 81 73 97 58]
    


```python
print(arr[arr>50])  # 获取大于50的数据
```

    [73 91 68 73 94 60 71 59 99 66 81 73 97 58]
    


```python
print(arr[2][arr[2]>50])  # 获取第3行大于50的数据
```

    [66 81 73]
    


```python
print(arr[:,3][arr[:,3]>50])  # 获取第4列大于50的数据
```

    [59 66]
    

## 6.ndarray的运算


```python
# 1维数组的算术运算
a = np.array([1,2,3])
b = np.array([4,5,6])
print(a + b)   # 加法
print(a - b)   # 减法
print(a * b )  # 乘法
print(a / b)   # 除法
print( a ** 2)  # 平方
```

    [5 7 9]
    [-3 -3 -3]
    [ 4 10 18]
    [0.25 0.4  0.5 ]
    [1 4 9]
    


```python
# 原生的python的运算,写起来就稍微麻烦一点，需要写一个for循环
c = [1,2,3]
d = [4,5,6]
for i in range(len(c)):
    d[i] = d[i] + c[i]
print(d)
```

    [5, 7, 9]
    


```python
# 2维数组的算术运算
a = np.array([[1,2,3],[4,5,6],[7,8,9]])
b = np.array([[4,5,6],[7,8,9],[1,2,3]])
print(a + b)   # 加法
print(a - b)   # 减法
print(a * b )  # 乘法
print(a / b)   # 除法
print( a ** 2)  # a的2平方
```

    [[ 5  7  9]
     [11 13 15]
     [ 8 10 12]]
    [[-3 -3 -3]
     [-3 -3 -3]
     [ 6  6  6]]
    [[ 4 10 18]
     [28 40 54]
     [ 7 16 27]]
    [[0.25       0.4        0.5       ]
     [0.57142857 0.625      0.66666667]
     [7.         4.         3.        ]]
    [[ 1  4  9]
     [16 25 36]
     [49 64 81]]
    


```python
# 数组与标量之间的算术运算
a = np.array([[1,2,3],[4,5,6],[7,8,9]])
print(a + 3)  # 把a里面的数据，都加上3
print(a * 3)  # 把a里面的数据，都乘以3
```

    [[ 4  5  6]
     [ 7  8  9]
     [10 11 12]]
    [[ 3  6  9]
     [12 15 18]
     [21 24 27]]
    


```python
# 广播机制  1.获取形状    2.是否广播
# 同一维度:相同、1
a = np.array([1,2,3])    # 数组为1行3列
b = np.array([[4],[5],[6]])   # 数组为3行1列
"""
下面是扩展说明怎么a+b的
a 
1 2 3
1 2 3
1 2 3
b
4 4 4
5 5 5
6 5 5

"""
print(a + b)  
print(b - a)
```

    [[5 6 7]
     [6 7 8]
     [7 8 9]]
    [[3 2 1]
     [4 3 2]
     [5 4 3]]
    


```python
# 下面的案例就是形状不同，所以就不能广播，就会报错
a = np.array([1,2,3])    # 数组为1行3列
b = np.array([4,5])   # 数组为1行2列
print(a + b)
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    Cell In[23], line 4
          2 a = np.array([1,2,3])    # 数组为1行3列
          3 b = np.array([4,5])   # 数组为1行2列
    ----> 4 print(a + b)
    

    ValueError: operands could not be broadcast together with shapes (3,) (2,) 



```python
# 矩阵运算
a = np.array([[1,2,3],[4,5,6],[7,8,9]])  # 3行3列的数组
b = np.array([[4,5,6],[7,8,9],[1,2,3]])  # 3行3列的数组
"""
扩展说明怎么乘法的
a
1 2 3
4 5 6
7 8 9
b
4 5 6
7 8 9
1 2 3

普通乘法就是对应的a里面的第1行第1个乘以b里面的第1行第1个，以此类推
"""
print(a * b)
print(a @ b)
"""
矩阵乘法结果说明比如print(a @ b)结果里面的72是怎么来的呢
找到结果是第2行2列，那就先找到a数组里面的第2行是4 5 6
              在找到b数组里面的第2列s是5 8 2 
                然后再对应相乘 4*5+5*8+6*2=72
"""
```

    [[ 4 10 18]
     [28 40 54]
     [ 7 16 27]]
    [[ 21  27  33]
     [ 57  72  87]
     [ 93 117 141]]
    


```python
# 第15课
```
