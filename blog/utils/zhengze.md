# 正则表达式

## 基本含义

> /^abc/i  i部分是修饰符,i的意思是表示忽略大小写


## 简单字符

> 没有特殊意义的字符都是简单字符,简单字符代表自身,绝大部分字符都是简单字符
>
> 例如 /abc/ ==> 匹配的就是abc  /赵元达/ ==> 匹配的就是赵元达 
> 

---
## 转义字符

|  字符   | 含义  |
|  ----  | ----  |
|  \n | 匹配换行符 |
|  \r | 匹配回车符 |
|  \t | 匹配tab键 |
|  \v | 匹配垂直制表符 |
|  \w | 匹配任何一个字母或者数字或者下划线 |
|  \W | 匹配任何一个字母或数字或者下划线之外的字符 |
|  \s | 匹配空白字符比如空格或者tab键 |
|  \S | 匹配非空白字符 |
|  \d | 匹配数字字符0-9 |
|  \D | 匹配非数字字符 |
|  \b | 匹配单词的边界 |
|  \B | 匹配非单词边界 |

---

## 字符集合

> 有时候我们需要匹配一类集合,字符集可以实现这些,语法是[]
>
> 例如[abc] ==> 可以匹配到a或b或c
>
>如果要表示字符很多,可以使用 - 表示一个范围内的字符 例如[0-9] ==== 等价于 [0123456789] 
>
>在前面加^ 可以表示取非  例如[^ab] ===> 匹配到ab以外得任何字符
>

--- 


## 量词

|  字符   | 含义  |
|  ----  | ----  |
|  {n} | 匹配n次 比如a{2}==>匹配aa |
|  {m,n} | 匹配m-n次,优先匹配n次,比如a{1,3} ==> 匹配aaa aa a |
|  ? | 匹配0次或者1次,优先匹配1次相当于{0,1} |
|  + | 匹配1-n次,优先匹配n次,相当于{1,} |
|  * | 匹配0-n次 优先匹配n次 相当于{0,n} |

>正则默认是贪婪模式,都会优先匹配上限而不是下限
>
> 有时候我们并不想要贪婪模式,而是匹配下限得情况,就需要在量词后面呢加? 例如a{1,3}? ==> 匹配的是a
>
---


## 字符边界

> 有时候我们会遇到边界匹配的情况,比如以xxx开头 以xxx结尾
>
> ^在[]外表示匹配开头的意思  例如 /^abc/ ==> 匹配的是abc 而不是aabc
>
> $表示匹配结尾的意思 例如 /abc$/ 可以匹配abc，但是不能匹配abcc
>

----

## 选择表达式

>
>
>
>
>
>
>
>
>

---


## 限制输入的长度并且必须是数字(利用keypress事件)

```javascript
// 传入的是输入框的值
  isNumber(value) {
      let evt = window.event
      if (value.length == 8) {
        evt.preventDefault()
      }
      var charCode = evt.which ? evt.which : evt.keyCode
      if (charCode > 31 && (charCode < 48 || charCode > 57) && charCode !== 46) {
        evt.preventDefault()
      } else {
        return true
      }
    },



```