# codewar-practice
很不错的练题网站： [codewar](https://www.codewars.com/)
## 范围提取（Range Extraction）
用于表达有序整数列表的格式是使用以逗号分割的列表,最终按升序排列整数列表并返回范围格式中格式正确的字符串。  

**要求：**  
1. 单个不连续整数
2. 由起始整数表示的整数范围，范围中的结束整数与短划线“-”分开。范围包括间隔中间的所有整数，包括两个端点。只有当至少包含3个数字时，才被视为一个范围。例如 ("12, 13, 15-17")  
例如：
```js
数组为: [-6, -3, -2, -1, 0, 1, 3, 4, 5, 7, 8, 9, 10, 11, 14, 15, 17, 18, 19, 20];
返回： returns  "-6,-3-1,3-5,7-11,14,15,17-20";
```
实现：
```js
function solution(list){
    for(var i = 0; i < list.length; i++){
        var j = i;
        while(list[j] - list[j+1] == -1) j++;
        if(j != i && j-i > 1) list.splice(i, j-i+1, list[i] + '-' + list[j]);
    }
    return list.join();
}

var list = [-6, -3, -2, -1, 0, 1, 3, 4, 5, 7, 8, 9, 10, 11, 14, 15, 17, 18, 19, 20];
solution(list)
```

