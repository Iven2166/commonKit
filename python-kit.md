
# python kit

x, d = divmod(n)

# Tensorflow

## 通用类

### if \_\_name__ == "\_\_main__"
- （1）单独运行时，该 module 的 \_\_name__ 会被定义为 \_\_main__ 
- （2）module 被导入进其他 module 时，\_\_name__ 被定义为module名称
- 因此，用 if \_\_name__ == "\_\_main__" 能够被用于控制该module被导入其他module时，避免运行该块代码


[参考](https://www.freecodecamp.org/news/if-name-main-python-example/#:~:text=We%20can%20use%20an%20if,name%20if%20it%20is%20imported.)
> There is a really nice use case for the __name__ variable, whether you want a file that can be run as the main program or imported by other modules. We can use an if __name__ == "__main__" block to allow or prevent parts of code from being run when the modules are imported.
When the Python interpreter reads a file, the __name__ variable is set as __main__ if the module being run, or as the module's name if it is imported.


### placeholder()
- 用以规定 dtype, shape, name
- [官网说明](https://www.tensorflow.org/api_docs/python/tf/compat/v1/placeholder)

### tf.compat.v1.get_variable()
- 用以获取某个规定参数的变量或者重新创建
- [官网说明](https://www.tensorflow.org/api_docs/python/tf/compat/v1/get_variable)
- 案例
```python
def foo():
  with tf.variable_scope("foo", reuse=tf.AUTO_REUSE):
    v = tf.get_variable("v", [1])
  return v

v1 = foo()  # Creates v.
v2 = foo()  # Gets the same, existing v.
assert v1 == v2
```

## 深度学习类

### 教程

|教程   	|link                                                    	|
|---	|----------------------------------------------------	|
|datawhale教程！！！|https://github.com/orgs/datawhalechina/repositories?type=all
|统计学习方法-书公式|https://github.com/SmirkCao/Lihang|
|统计学习方法（第二版）习题解答|https://github.com/datawhalechina/statistical-learning-method-solutions-manual|
|南瓜书PumpkinBook|https://github.com/datawhalechina/pumpkin-book|
|深入浅出pytorch   	| https://github.com/datawhalechina/thorough-pytorch 	|
|PyTorch 中文手册（pytorch handbook）|https://github.com/zergtant/pytorch-handbook|
|机器学习集成学习与模型融合(基于python)   	|https://github.com/datawhalechina/ensemble-learning                                                    	|
|动手学CV-Pytorch|https://datawhalechina.github.io/dive-into-cv-pytorch/#/chapter01_preliminary_knowledge/1.1_environment_install/README|
|业务类-推荐系统|https://github.com/datawhalechina/fun-rec|
|前沿跟踪-推荐系统|https://github.com/ruyiluo/Reco-Res|


[CV的pooling-demo & 课程](https://deeplizard.com/resource/pavq7noze3)

### tf.nn.embedding_lookup
- Looks up embeddings for the given ids from a list of tensors.

### Keras 中的遮盖和填充
- [官网说明](https://www.tensorflow.org/guide/keras/masking_and_padding)
tf.keras.preprocessing.sequence.pad_sequences

### torch.nn
> [官网参考](https://pytorch.org/docs/stable/nn.html)

### torch.nn.Conv2d

> torch.nn.Conv2d(in_channels, out_channels, kernel_size, stride=1, padding=0, dilation=1, groups=1, bias=True, padding_mode='zeros', device=None, dtype=None)
> [官网参考](https://pytorch.org/docs/stable/generated/torch.nn.Conv2d.html)

```python
# With square kernels andequal stride
import torch
import torhc.nn as nn
m = nn.Conv2d(16, 33, (3,3), stride=2) # in_channels=16, out_channels=33
input1 = torch.randn(20, 16, 50, 100) # batch_size = 20, in_channels = 16, matrix shape = (50,100)
output = m(input1) 
print(output.shape) # torch.Size([20, 33, 24, 49]) : return shape of batch_size = 20, out_channels = 33, (24, 49) as product size  
print(output[0][0].shape)  # torch.Size([50, 100]) : one of the matrix shape is (50, 100)
```

### torch.nn.ModuleList(modules=None)
> ModuleList can be indexed like a regular Python list, but modules it contains are properly registered, and will be visible by all Module methods.
> [官网参考](https://pytorch.org/docs/stable/generated/torch.nn.ModuleList.html?highlight=nn%20modulelist#torch.nn.ModuleList)

