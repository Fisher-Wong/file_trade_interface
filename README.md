����ȯ��PBϵͳ��˵���ļ���ʵ���˲���ϵͳ�ġ��ļ������Խӳ���



**ע��˵���ļ�Ҳ������ʵϵͳ��һ�¡�����ļ���û��ʹ����ʵ������ԣ�������֤�ļ�����ȫ�����ԡ����������������޸Ĵ��롣**



**�ļ�**

- interface_CATS������CATS
- interface_DTS���㷢DTS
- interface_TS������TS
- interface_XT��ѸͶPB
- interface_ZS�����̽��״�ʦ



**ʾ��**

```python
from interface_DTS import *

# ʾ��
interface = DTSInterface(order_list_file="Order.csv", 
                         order_report_file="OrderReport.csv",
                         query_order_file="QueryOrder.csv",
                         fund_report_file="FundReport.csv",
                         position_report_file="PositionReport.csv")
# �µ�
order_id = interface.order(security="600660.XSHG", amount=100, style=DTSInterface.LimitOrder(price=23.33), side='long')

# �����µ���һ����д���ļ�
with interface.bucket():
    for i in range(0,10):
        order_id = interface.order(security="600660.XSHG", amount=100, style=DTSInterface.LimitOrder(price=23.33), side='long')

# ��ȡ�˻���Ϣ
interface.portfolio

# ��ȡ�ֲ���Ϣ
interface.position

```



