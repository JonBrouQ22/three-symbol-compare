> // This source code is subject to the terms of the Mozilla Public License 2.0 at https://mozilla.org/MPL/2.0/
> // © Dez_Algo
> 
> //@version=4
> study("3 Symbol Comparison", "3SymComp", overlay=false)
> 
> // INPUTS
> // input 3 symbols
> i_sym1 = input(title="Symbol1", type=input.symbol, defval="QQQ")
> i_sym2 = input(title="Symbol2", type=input.symbol, defval="SPY")
> i_sym3 = input(title="Symbol3", type=input.symbol, defval="IWM")
> // input the resolution - same for all symbols
> i_res = input(title="Resolution", type=input.resolution, defval="D")
> // input line colors
> i_c_line1 = input(title="Line1", type=input.color, defval=color.blue)
> i_c_line2 = input(title="Line2", type=input.color, defval=color.orange)
> i_c_line3 = input(title="Line3", type=input.color, defval=color.fuchsia)
> 
> // get symbol info
> // symbol 1 OHLC data
> s1Close = security(i_sym1, i_res, close)
> s1Open = security(i_sym1, i_res, open)
> s1High = security(i_sym1, i_res, high)
> s1Low = security(i_sym1, i_res, low)
> // symbol 2
> s2Close = security(i_sym2, i_res, close)
> s2Open = security(i_sym2, i_res, open)
> s2High = security(i_sym2, i_res, high)
> s2Low = security(i_sym2, i_res, low)
> // symbol 3
> s3Close = security(i_sym3, i_res, close)
> s3Open = security(i_sym3, i_res, open)
> s3High = security(i_sym3, i_res, high)
> s3Low = security(i_sym3, i_res, low)
> 
> // plot candles
> plotcandle(s1Open,s1High,s1Low,s1Close, "Symbol 1 Candles", i_c_line1)
> plotcandle(s2Open,s2High,s2Low,s2Close, "Symbol 2 Candles", i_c_line2)
> plotcandle(s3Open,s3High,s3Low,s3Close, "Symbol 3 Candles", i_c_line3)
> 
> // plot lines
> plot(s1Close, "Symbol 1 Line",i_c_line1)
> plot(s2Close, "Symbol 2 Line", i_c_line2)
> plot(s3Close, "Symbol 3 Line", i_c_line3)