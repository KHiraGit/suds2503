# suds2503
埼玉大学産官学連携協議会データサイエンス研究会 (2026/3/18)

# データサイエンス研究会 第3回研究会　～ 経験則とデータ分析の組み合わせ方 ～

データ分析において最も重要なことは分析対象への深い理解です。分析の結果、現場の常識が再確認されることも少なくありません。本研究会では、多変量時系列データの分析を題材に、現場の経験則をいかに分析へ融合させ、実効性のある意思決定へとつなげるかを追求します。当日は、前半に対象データの概要と標準的な分析フローを解説します。後半のワークショップでは、事前に配布したサンプルデータの分析で「できたこと」と「やりたかったこと」を参加者間で共有し、現場の知恵を分析に活かすための成功の秘訣を導き出します。

# 利用するデータセット
London bike sharing dataset
(入手元 https://www.kaggle.com/datasets/hmavrodiev/london-bike-sharing-dataset)

## データセットのライセンス

### License
These licence terms and conditions apply to TfL's free transport data service and are based on version 2.0 of the Open Government Licence with specific amendments for Transport for London (the "Licence"). TfL may at any time revise this Licence without notice. It is up to you ("You") to regularly review the Licence, which will be available on this website, in case there are any changes. Your continued use of the transport data feeds You have opted to receive ("Information") after a change has been made to the Licence will be treated as Your acceptance of that change.

Using Information under this Licence
TfL grants You a worldwide, royalty-free, perpetual, non-exclusive Licence to use the Information subject to the conditions below (as varied from time to time).

This Licence does not affect Your freedom under fair dealing or fair use or any other copyright or database right exceptions and limitations.

This Licence shall apply from the date of registration and shall continue for the period the Information is provided to You or You breach the Licence.

Rights
You are free to:

Copy, publish, distribute and transmit the Information
Adapt the Information and
Exploit the Information commercially and non-commercially for example, by combining it with other Information, or by including it in Your own product or application
Requirements
You must, where You do any of the above:

Acknowledge TfL as the source of the Information by including the following attribution statement 'Powered by TfL Open Data'
Acknowledge that this Information contains Ordnance Survey derived data by including the following attribution statement: 'Contains OS data © Crown copyright and database rights 2016' and Geomni UK Map data © and database rights [2019]
Ensure our intellectual property rights, including all logos, design rights, patents and trademarks, are protected by following our design and branding guidelines
Limit traffic requests up to a maximum of 300 calls per minute per data feed. TfL reserves the right to throttle or limit access to feeds when it is believed the overall service is being degraded by excessive use and
Ensure the information You provide on registration is accurate
These are important conditions of this Licence and if You fail to comply with them the rights granted to You under this Licence, or any similar licence granted by TfL, will end automatically.

Exemptions
This Licence does not:

Transfer any intellectual property rights in the Information to You or any third party
Include personal data in the Information
Provide any rights to use the Information after this Licence has ended
Provide any rights to use any other intellectual property rights, including patents, trade marks, and design rights or permit You to:
Use data from the Oyster, Congestion Charging and Santander Cycles websites to populate or update any other software or database or
Use any automated system, software or process to extract content and/or data, including trawling, data mining and screen scraping
in relation to the Oyster, Congestion Charging and Santander Cycles websites, except where expressly permitted under a written licence agreement with TfL.
These are important conditions of this Licence and, if You fail to comply with them, the rights granted to You under this Licence, or any similar licence granted by TfL, will end automatically.

Non-endorsement
This Licence does not grant You any right to use the Information in a way that suggests any official status or that TfL endorses You or Your use of the Information.

### Context
The purpose is to try predict the future bike shares.

### Content
The data is acquired from 3 sources:

* Https://cycling.data.tfl.gov.uk/ 'Contains OS data © Crown copyright and database rights 2016' and Geomni UK Map data © and database rights [2019] 'Powered by TfL Open Data'
* freemeteo.com - weather data
* https://www.gov.uk/bank-holidays
From 1/1/2015 to 31/12/2016

The data from cycling dataset is grouped by "Start time", this represent the count of new bike shares grouped by hour. The long duration shares are not taken in the count.

### Metadata:
"timestamp" - timestamp field for grouping the data
"cnt" - the count of a new bike shares
"t1" - real temperature in C
"t2" - temperature in C "feels like"
"hum" - humidity in percentage
"wind_speed" - wind speed in km/h
"weather_code" - category of the weather
"is_holiday" - boolean field - 1 holiday / 0 non holiday
"is_weekend" - boolean field - 1 if the day is weekend
"season" - category field meteorological seasons: 0-spring ; 1-summer; 2-fall; 3-winter.

"weathe_code" category description:
1 = Clear ; mostly clear but have some values with haze/fog/patches of fog/ fog in vicinity 2 = scattered clouds / few clouds 3 = Broken clouds 4 = Cloudy 7 = Rain/ light Rain shower/ Light rain 10 = rain with thunderstorm 26 = snowfall 94 = Freezing Fog

