# python
# -*- coding:utf-8 -*-

from WindPy import w
import pandas as pd
import datetime
w.start()

# 取数据的命令如何写可以用命令生成器来辅助完成

% datetime.time
HS = pd.read_excel(u'沪深A股交易所编码.xls',header=None)
HS.head()
Hs = HS.ix[:2,0]
wsd_data=w.wsd("000001.SZ", "open,high,low,close", "2016-04-19", "2016-07-14")
data = []
for i in range(len(Hs)):
    # print Hs.ix[i, 0]  # data[Hs.ix[i, 0]]
    data.append(w.wsd( Hs.ix[i, 0] , "open,high,low,close", "2016-04-19", "2016-07-14"))
    open=pd.Series(data[i].Data[0])        #open=pd.Series(wsd_data.Data[0])
    high=pd.Series(data[i].Data[1])
    low=pd.Series(data[i].Data[2])
    close=pd.Series(data[i].Data[3])

    data_panel = pd.Panel(    dict( j  (Hs.ix[i, 0],pd.DataFrame(data[i].Data,index=data[i].Fields,columns=data[i].Times))  for j in )    )
    fm = fm.T #将矩阵转置  #data_panel



#演示如何将api返回的数据装入Pandas的Series
open=pd.Series(wsd_data.Data[0])        #open=pd.Series(wsd_data.Data[0])
high=pd.Series(wsd_data.Data[1])
low=pd.Series(wsd_data.Data[2])
close=pd.Series(wsd_data.Data[3])

print('open:/n',open)
print('high:/n',high)
print('low:/n',low)
print('close:/n',close)

#演示如何将api返回的数据装入Pandas的DataFrame
fm=pd.DataFrame(wsd_data.Data,index=wsd_data.Fields,columns=wsd_data.Times)
fm=fm.T #将矩阵转置
print('fm:/n',fm)



w.wset("SectorConstituent","date=20160715;sectorId=a001010100000000")

IF_1608.head()



dd = {}
for i in range(1, 3):
    name = 'X' + str(i)
    dd[name] = DataFrame(np.random.randn(3,3))

dd = pd.Panel(dd)

data_panel=pd.Panel(dict([ (i,data) for i in range(2000)]))
