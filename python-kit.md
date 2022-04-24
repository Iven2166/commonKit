
# python kit

x, d = divmod(n)

# Tensorflow

## 通用类

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

### tf.nn.embedding_lookup
- Looks up embeddings for the given ids from a list of tensors.

### Keras 中的遮盖和填充
- [官网说明](https://www.tensorflow.org/guide/keras/masking_and_padding)
tf.keras.preprocessing.sequence.pad_sequences

