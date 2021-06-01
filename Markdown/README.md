# Markdown Syntax

<https://www.markdownguide.org/>
## Contents
- [Heading ID](#-Heading-ID)
- [Paragraph](#-Paragraph)
- [Line Break](#-Line-Break)
- [Emphasis](#-Emphasis)
- [List](#-List)
  - [Ordered List](#Ordered-List)
  - [Unordered List](#Unordered-List)
- [Table](#-Table)
- [Fenced Code Block](#-Fenced-Code-Block)
- [Horizontal Rule](#-Horizontal-Rule)
- [Link](#-Link)
  - [URL Link](#URL-링크)
  - [Hide URL Link](#URL-링크-숨기기)
  - [Link to Heading ID](#Link-to-Heading-ID)
- [Blockquote](#-Blockquote)
## 🐽 Heading ID
```
# 제목1
## 제목2
### 제목3 
#### 제목4 
##### 제목5 
###### 제목6
```
# 제목1
## 제목2
### 제목3 
#### 제목4 
##### 제목5 
###### 제목6

## 🐽 Paragraph
```
This is the first paragraph.

This is the second paragraph.
```
This is the first paragraph.

This is the second paragraph.
## 🐽 Line Break
```
This is the first line.<br>This is the second line.
```
This is the first line.<br>This is the second line.
> 문장 끝에 `<br>`을 붙인다.

## 🐽 Emphasis
```
- **볼드**
- *이탈릭* or _이탈릭_
- ***볼드 & 이탈릭*** or ___볼드 & 이탈릭___
- ~취소선~
- 문장에서 `하이라이트` 대용 가능
```
- **볼드** <br>
- *이탈릭* or _이탈릭_ <br>
- ***볼드 & 이탈릭*** or ___볼드 & 이탈릭___<br>
- ~취소선~
- 문장에서 `하이라이트` 대용 가능

## 🐽 List
#### Ordered List
```
1. First item
2. Second item
3. Third item
4. Fourth item
```
1. First item
2. Second item
3. Third item
4. Fourth item
#### Unordered List
```
- item
- item
  - item
    - item
```
- item
- item
  - item
    - item

## 🐽 Table
```
| Syntax      | Description |
| ----------- | ----------- |
| Header      | Title       |
| Paragraph   | Text        |
```
| Syntax      | Description |
| ----------- | ----------- |
| Header      | Title       |
| Paragraph   | Text        |

> [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables) 에서 쉽고 빠르게 표를 만들 수 있음.

## 🐽 Fenced Code Block
``````
```python
def solution():
  return "hello"
```
``````
```python
def solution():
  return "hello"
```
## 🐽 Horizontal Rule
```
***
---
_________________
```
***
---
_________________

## 🐽 Link
#### URL 링크
```
<https://github.com/>
```
<https://github.com/>
#### URL 링크 숨기기
```
1. [Github](https://github.com/)로 이동합니다.
2. [Github][1]로 이동합니다.

[1]: <https://github.com/> "github link"
```
1. [Github](https://github.com/)로 이동합니다.
2. [Github][1]로 이동합니다.

[1]: <https://github.com/> "github link"

#### Link to Heading ID
```
[Contents](#Contents)
```
[Contents](#Contents)

## 🐽 Blockquote
```
> Dorothy followed her through many of the beautiful rooms in her castle.
>
>> The Witch bade her clean the pots and kettles and sweep the floor and keep the fire fed with wood.
```
> Dorothy followed her through many of the beautiful rooms in her castle.
>
>> The Witch bade her clean the pots and kettles and sweep the floor and keep the fire fed with wood.
