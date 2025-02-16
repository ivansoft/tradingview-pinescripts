https://www.tradingview.com/pine-script-docs/
https://www.tradingview.com/pine-script-reference/


= = = =

Dec 30, 2023

https://www.tradingcode.net/ - "Pine Script" tutorials
https://www.tradingview.com/script/BICzyhq0-ta/ - Library "ta"
https://www.tradingview.com/script/cZnSLls2-RelativeValue/ - "RelativeValue"
https://www.tradingview.com/script/ZaliXFLV-Volume-Spike-Analysis-Trendoscope/ - "Volume Spike Analysis"


https://www.tradingview.com/pine-script-docs/en/v5/concepts/Timeframes.html#timeframe-string-specifications
  "S” for seconds, "D” for days, "W” for weeks and "M” for months
  "1S”, "30” (30 minutes), "1D” (one day), "3M” (three months)
  "1” is interpreted as "1min”, "S” is equivalent to "1S”, "D” to "1D, etc.

https://www.tradingview.com/pine-script-docs/en/v5/concepts/Repainting.html#future-leak-with-request-security
  lookahead_on - at higher timeframes without offsetting the expression (close -> close[1]) will introduce future leak in scripts
                 as the function will then return the close price before it is actually known in the current context
https://www.tradingview.com/pine-script-docs/en/v5/concepts/Repainting.html#pagerepainting-historicalvsrealtimecalculations-repaintingrequestsecuritycalls

https://www.tradingview.com/pine-script-docs/en/v5/concepts/Repainting.html?highlight=isnew#bar-state-built-ins
  barstate.isnew is true on the bar’s close, yet in realtime, it is true on the bar’s open

https://www.tradingview.com/pine-script-docs/en/v5/concepts/Bar_states.html#barstate-isnew

            history            history      history      realtime  #confirmed    #new     realtime  #confirmed
 |                          | confirmed | #uncompleted |   tick   |  update  |          |          |  update  | ... 
 | isnew 1                  |     1     |      1       |  1 -> 0  |    0     |  0 -> 1  |  1 -> 0  |    0     |     
 | isconfirmed 1            |     1     |    1 -> 0    |    0     |  0 -> 1  |  1 -> 0  |    0     |  0 -> 1  |     
 | isrealtime 0             |     0     |      0 !     |  0 -> 1  |    1     |    1     |    1     |    1     |     
 | isfirst 0                |     0     |      0       |    0     |    0     |    0     |    0     |    0     |     
 | islast 0                 |     0     |    0 -> 1    |    1     |    1     |    1     |    1     |    1     |     
 | islastconfirmedhistory 0 |   0 -> 1  |    1 -> 0    |    0     |    0     |    0     |    0     |    0     |     
 | ishistory 1              |     1     |      1 !     |  1 -> 0  |    0     |    0     |    0     |    0     |     


https://www.tradingview.com/pine-script-docs/en/v5/concepts/Libraries.html#library-functions
These are the constraints
- cannot use variables from the library’s global scope unless they are qualified as “const”
- you cannot use global variables initialized from script inputs, globally declared arrays


= = = =

May 31, 2022
https://www.tradingview.com/blog/en/request-more-data-from-your-scripts-31944/
Two new Pine Script™ functions, request.security_lower_tf() and request.economic()


https://www.tradingview.com/script/cZnSLls2-RelativeValue/
import TradingView/RelativeValue/2

https://www.tradingview.com/script/mCOgJC67-Strategy/
import TradingView/Strategy/3

https://www.tradingview.com/script/BICzyhq0-ta/
import TradingView/ta/7

https://www.tradingview.com/v/tyeeNU9I/
import PineCoders/Time/4

https://www.tradingview.com/script/UxiDkNg0-lower-tf/
import PineCoders/lower_tf/4

- - - - -

https://www.tradingview.com/script/rYX3lueB-Strings/
import PineCoders/Strings/1

https://www.tradingview.com/script/9l0ZpuQU-ConditionalAverages/
import PineCoders/ConditionalAverages/1

https://www.tradingview.com/script/Bn7QkdZR-getSeries/
import PineCoders/getSeries/1

