# Request
## if request.method == 'GET' 'POST'
判断request请求类型
## request.GET
获取url中，问号后面的数据(部分请求方式）：
        /JAL/products?user_id=aaa&pw=123
get到的数据类型为***QueryDict***对象
### url
        ?user_id=aaa&pw=123
### get: 
        <QueryDict: {'user_id': ['aaa'], 'pw': ['123']}>
### url: 
        ?user_id=aaa?pw=123
### get: 
        <QueryDict: {'user_id': ['aaa?pw=123']}>

## request.GET.get('user_id')
### url:
        ?user_id=aaa&pw=123
### get:
        aaa
### url:
        ?user_id=aaa?pw=123
### get:
        None
## request.POST.get('asin')
通过name获取post表单中的内容：<input type="text" name="asin" id="" value="{{ asin.asin }}" />
