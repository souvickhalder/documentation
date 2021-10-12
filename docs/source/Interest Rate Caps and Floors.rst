Interest Rate Caps and Floors
=============================

Overview
--------
Caps and floors are OTC interest rate products referring to interest rate index like LIBOR or national interest rates (e.g. USD LIBOR, Euribor etc.). Caps are a series of caplets or call options which mature periodically (quarterly, semi-annually or yearly). Similarly floors are a series of put options. Interest rate caps and floors are used for hedging against rising or declining rates. 

Pricing and valuation of each caplets / floorlets are determined using Black formula. 

.. note::

   This project is under active development. 

Version
-------
The current version for this API is **1.0.0**. 

Description about the API
-------------------------
Analytical function to calculate pricing and risk metrics is implemented in C++. 

This function takes ATM volatility surface, yield curves, Cap / Floor type, Notional, Strike, Times to maturity, payment frequency, currency as inputs. This generates PV, Delta (DV01), Gamma as outputs. 

.. note::

   Few *Assumptions* should be considered while using this API: Strikes are same for all payments. Development works is in progress to use different ``Strikes`` for different payment dates. Yield curves are interpolated using Bootstrapping methods. This API takes ATM volatility is used for the calculation. Linear interpolation is used to adjust for different tenors. Future development will enhance the adjustment for different Strikes. 

This C++ function is wrapped and can be used in **Python** using below code snippet: 

``>>> import MyAnalytics`` 

``>>> res = MyAnalytics.computeCapFloorMetrics(mkt, CapFloorType, Notional, Strike, TimesToMaturity, PaymentFrequency='3M', currency='USD', CalcType='PV')`` 

Below are the *mandatory* parameters for this function:

``mkt = [atm_vol_tenors, atm_vol_surface, yield_curves_tenors, yield_curves]`` this is a list of ``atm_vol_tenors`` (list with volatility surface tenors in number of days), ``atm_vol_surface`` (list of lists with volatility surfaces and the number of elements are of same size as ``atm_vol_tenors``), ``yield_curves_tenors`` (list with yield curve  tenors in number of days), ``yield_curves`` (list of lists with yield curves and the number of elements are of same size as ``yield_curves_tenors``). These parameters should be intuitive from the example below. 

``CapFloorType = 'Cap' or 'Floor'``, 

``Notional = Notional amount of the trade``, 

``Strike = Strike of Caps / Floors``, 

``TimesToMaturity = Times to matury in number of years``. E.g. 0.25 (3 month tenor), 1 (1 year tenor), 5 (5 year tenor) etc. 

Below are the *optional* parameters for this function:

``PaymentFrequency = Payment frequency`` which can be '3M', '6M'or '1Y'. If this is not provided, '3M' will be used as default. 

``currency = Currency of the trade`` If this is not provided, 'USD' will be used as default.

``CalcType = 'PV' (to calculate PV / MtM), 'DV01' (to calculate Delta / DV01) or 'Gamma' (to calculate Gamma)``.  If this is not provided, 'PV' will be used as default.

An example **Python** code is shown below: 

``>>> import MyAnalytics`` 

``>>> atm_vol_tenors = [30, 360, 720, 1800, 3600]`` 

``>>> atm_vol_surface = [[16.5, 17.5, 16.25, 16.5, 16.5], [16.25, 17.5, 16.25, 16.55, 16.35], [16.5, 17.35, 16.25, 16.75, 16.5], [16.5, 17.25, 16.25, 16.55, 16.95],[16.35, 17.45, 16.25, 16.85, 16.55]]`` 

``>>> yield_curves_tenors = [30, 360, 720, 1800, 3600]`` 

``>>> yield_curves = [0.01, 0.012, 0.0125, 0.0127, 0.013]`` 

``>>> mkt = [atm_vol_tenors, atm_vol_surface, yield_curves_tenors, yield_curves]`` 

``>>> res = MyAnalytics.computeCapFloorMetrics(mkt, CapFloorType, Notional, Strike, TimesToMaturity, PaymentFrequency='3M', currency='USD', CalcType='PV')``

