# YML 语法

Retrieved from [here](https://blog.csdn.net/michaelhan3/article/details/69664932)

## 基本语法规则

> - 大小写敏感
> - 使用缩进表示层级关系
> - 缩进时不允许使用Tab键，只允许使用空格
> - 缩进的空格数目不重要，只要相同层级的元素左侧对齐即可

注释用#来表示，从这个字符一直到行尾，都会被解析器忽略

Yaml支持的数据结构有三种：

> - 对象：键值对的集合，又被称为映射 Mapping、哈希 hashes和字典 dictionary
> - 数组
> - 纯量

### 对象

一组键值对，使用冒号结构表示：  
```
animal: pets
```

转换成JavaScript如下：

```
{ animal: 'pets' }
```

Yaml还有另外一种写法，将所有的键值写成一个行内对象：  
```
hash: { name: Steve, foo: bar }
```

转成Javascript如下：  
```
{ hash: { name: 'Steve', foo: 'bar' } }
```

### 数组

一组连词线开头的行：  
```
- Cat
- Dog
- Goldfish
```

转为JavaScript如下：  
```
[ 'Cat', 'Dog', 'Goldfish' ]
```

数据结构的子成员是一个数组，则可以在该项下面缩进一个空格：  
```
- 
 - Cat
 - Dog
 - Goldfish
```

转为JavaScript如下：  
```
[ [ 'Cat', 'Dog', 'Goldfish' ] ]
```

数组也可以采用行内表示法：  
```
animal: [Cat, Dog ]
```

转为JavaScript如下：  
```
{ animal: [ 'Cat', 'Dog' ] }
```

### 复合结构

对象和数组可以结合使用，形成复合结构：  
```
Language:
 - Ruby
 - Perl
 - Python
 Website:
  YAML: yaml.org
  Ruby: ruby-lang.org
  Python: python.org
  Perl: use.perl.org 
```

转为JavaScript如下：
```Javascript
{ Language: ['Ruby', 'Perl', 'Python' ] ,
  Website:
  { YAML: 'yaml.org',
    Ruby: 'ruby-lang.org',
    Python: 'python.org',
    Perl: 'user.perl.org' } }
```

