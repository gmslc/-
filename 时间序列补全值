from datetime import datetime
import pandas as pd
# 带有时间序列的原始df
result=pd.DataFrame(data={"statistic_date": [],"value1":[]})
temp_df=pd.DataFrame(data={"statistic_date": [],"value2":[])
# 创建一段完整的时间序列的df
data=list(pd.date_range(datetime.strftime("2019-01-01","%m/%d/%Y"),datetime.strftime("2019-06-13","%m/%d/%Y")))
data = [x.date() for x in data]
result_data = pd.DataFrame(data={"statistic_date": data})
#合并df，残缺的时间序列值填充
result_data = result_data.merge(temp_df, how='outer', on='statistic_date')
result_data = result_data.fillna(method="bfill")
result = result.merge(result_data, how='outer', on='statistic_date')
