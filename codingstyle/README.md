# codingstyle

## 分號
- 不要用分號作為一行的結束且不要用分號作為兩行之間的分隔。

## 分行
- 一行不要超過80個字，除非其中有包含長URL的註解和很長的引入敘述。
- 不要使用反斜線來接續兩行。
- 確保隱行被放在括弧(大、中、小)中，如有必要可以在表達式外額外新增括弧。
 
 ```
 foo_bar(self, width, height, color='black', design=None, x='foo',
      emphasis=None, highlight=0) 
 ```
 
 ```
 if(width == 0 and height == 0 and
     color == 'red' and emphasis == 'strong')
 ```
 
- 當字串長度大於一行時，將其分行並使用括弧將整個字串包起來。
  
  ```
  x=('This will build a very long long'
      'long long long long long long string')
 ```
 
- 放在註解中的URL連結盡量避免分行，如有需要，連結可以放在獨立的一行
  
  ```
  正確: 
  #See details at
  #http://www.example.com/us/developer/documentation/api/content/v2.0/csv_file_name_extension_full_specification.html
  ```
  
  ```
  錯誤: 
  # See details 
  # http://www.example.com/us/developer/documentation/api/content/\
  # v2.0/csv_file_name_extension_full_specification.html
  ```
  
  注意以上案例的縮排情形。
  
## 括弧
盡量減少括弧的使用。回傳值和判斷式除非包含函式或是隱行否則避免使用。

```
if foo:
    bar()
while x:
    x=bar()
if x and y:
    bar()
return foo
for (x,y) in dict.items():
    print x + y
```

##縮排

縮排距離為四格空白。請不用使用tab縮排，可以設定編輯器將tab鍵動作改成輸入四格空白。

```
# 在括弧或是引號等定界符內，參數第一欄縱向對齊要有數值
foo = long_function_name(var_one,var_two,
              var_three, var_four)

# 在dictionary的定界符號內
foo = {
    long_dictionary_key: value1 +
                value2,
    ...
}
# 第一行沒有包含參數，第二行要縮排四格空格
foo = long_function_name(
    var_one, var_two, var_three,
    var_four)
```

##空白行
在開頭重要的Class以及函式宣告和後面的程式之間用兩空白行隔開，寫在程式裡的函式宣告只需要一空白行隔開。

##空格
在括弧內的參數不添加任何空格。

```
spam(ham[1],{eggs: 2},[])
```

在冒號、分號、逗號前不要加空格，加在後面。

```
if x == 4:
    print x, y
```

括弧的第一個參數前後均不加任何空白。

```
spam(1)
dict['key'] = list[index]
```

運算元或是邏輯符號前後均加空格。當'='在參數表達裡，前後不加空格。

```
x = x + y
x and y
x == y
x > y
def complex(src=img,dst=frame)
```

不要使用空格對齊'#'後的註解或是'='後面的數值。
