# Тестовое задание младший аналитик 

# Задание:

1. Выполнить подключение к любому API из раздела Shopping https://github.com/public-apis/public-apis#shopping

2. Получить данные

3. Выполнить базовый анализ данных и сделать общие выводы 


# План работы

## Выполнить подключение к любому API из раздела Shopping https://github.com/public-apis/public-apis#shopping

 Мной была выбрана API Lazada, подключение выполнялось с помощью Lazada Open SDK. Были получены данные из GetCategoryTree (для получения списка всех категорий в системе) и GetCategoryAttributes (чтобы получить список атрибутов для категорий из списка GetCategoryTree). Анализ проводился по ДФ, полученной из данных атрибутов. 

## Загрузить данные и изучить общую информацию

df_categ - датасет, который хранит данные о категориях, которые есть в системе (GetCategoryTree).

df - датасет, который содержит атрибуты (GetCategoryAttributes).

## Выполнить базовый анализ данных и сделать общие выводы 

3.1. Изучить общую информацию о датасетах.

Провести предобработку - кол-во дубликатов, типы данных, пропуски, размерности.

3.2. Анализ данных. 

Узнать является ли категория конечной и возможно ли ее использовать для создания продуктов.

Посмотреть сколько приходится category_id на наименование категорий.

Посмотреть кол-во изменяемых атрибутов и соотношение изменяемые / неизменяемые, стандартные / нестандартные.

Вычислить соотношение типов атрибутов - normal / sku. 

Вычислить и визулизировать общее кол-во и кол-во уникальных id по типам значений, которые для него можно ввести (input_type).

Посмотреть сколько приходится имен атрибутов на лейбл, на id атрибутов; id атрибутов и label.

Посмотреть сколько приходится id атрибутов на id категорий, посмотреть стат. данные, бостроить боксплот.


## Вывод





# Описание данных

df_categ - GetCategoryTree

| Field Name  | Field Description| 
| :---    | :----    | 
| children    | List of subcategories of the current category ID |
| name    | Category Name |
| leaf    | Determine if the category is a leaf category, only leaf categories can be used to create products |
| category_id    | The ID of the current category, used when creating products or getting category attributes |


df - GetCategoryAttributes

| Field Name  | Field Description| 
| :---    | :----    | 
| is_sale_prop    | If it is 1, it indicates that this attribute is a standard sales/variant attribute |
| name    | Attribute name. As an attribute name, it must be in English. As an option name, it may respond to the local language depending on the "language_code" of the request. |
| input_type    | The type of value that can be entered for this attribute 1: singleselect: single selection does not support customization 2: multiselect: multiselect does not support customization 3: enuminput: single choice supports customization 4: multienuminput: multi selection supports customization 5: text: text can be customized 6: numeric: the value can be customized 7: date: date can be customized 8: richText: rich text can be customized 9: img: pictures can be customized |
| options    | Available options for enumerating attributes of type |
| is_mandatory    | If it is 1, it means that this attribute is required |
| attribute_type    | If the value is "normal", this attribute should be filled in the "Attribute" field when creating or updating the product. If the value is "sku", this attribute should be filled in the "Sku" field when creating or updating the product.|
| label    | Name of the field displayed in the seller center (this field cannot be used when creating or updating) |
| id    | attribute id |

# Использованные библиотеки

 pandas 
 
 numpy 
 
 lazop_sdk 
 
 numpy 
 
 matplotlib.pyplot 
 
 seaborn 


```python

```
