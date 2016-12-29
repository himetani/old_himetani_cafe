+++
date = "2016-12-11T01:27:22+09:00"
title = "3値論理について"
tags = ['sql']
+++

3値論理について書きました。

<!--more-->

# 3値論理とは
[3値論理 - Wikipedia](https://ja.wikipedia.org/wiki/3値論理)より引用。  

> 
3値論理（英語：ternary, three-valued or trivalent logic）とは、通常の真（true）と偽（false）から成る真偽値の他にもうひとつの真理値を持つ論理体系で、多値論理のひとつである。

SQLの本を読んでいるとよく出てくる話題です。  
忘れることが多いので、まとめます。

# 3値論理の真理値表

## NOT
| A    |   NOT A|
|:-----|:------:|
| True | False  |
| False| True   |
| NULL | NULL   |

## AND 
| A    | B    | A AND B|
|:-----|:-----|:------:|
| True | True | True   |
| True | False| False  |
| True | NULL | **※NULL**  |
| False| True | False  |
| False| False| False  |
| False| NULL | **※False**  |
| NULL | True | **※NULL**   |
| NULL | False| **※False**  |
| NULL | NULL | NULL   |


## OR
| A    | B    | A OR B|
|:-----|:-----|:------:|
| True | True | True   |
| True | False| True   |
| True | NULL | **※True**  |
| False| True | True   |
| False| False| False  |
| False| NULL | **※NULL**   |
| NULL | True | **※True**   |
| NULL | False| **※NULL**   |
| NULL | NULL | NULL   |

## その他
| 式  | 評価|
|:---------|:-----|
| NULL=0 | NULL | 
| NULL=12345 | NULL | 
| NULL<>12345 | NULL | 
| NULL+12345 | NULL | 
| NULL \|\| 'string' | NULL | 
| NULL = NULL | NULL | 
| NULL <> NULL | NULL | 

## まとめ
- NULLは演算できない（演算してもNULLになる）  
- AND FALSE の真理値は必ずFALSEになる  
- OR TRUE の真理値は必ずTRUEになる
