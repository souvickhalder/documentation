Interest Rate Caps and Floors
=============================

Overview
--------
Caps and floors are OTC interest rate products referring to interest rate index like LIBOR or national interest rates (e.g. USD LIBOR, Euribor etc.). Caps are a series of caplets or call options which mature periodically (quarterly, semi-annually or yearly). Similarly floors are a series of put options. Interest rate caps and floors are used for hedging against rising or declining rates. 

.. note::

   This project is under active development. 

Version
-------
The current version for this API is 1.0.0. 

Description about the API
-------------------------
Analytical function to calculate pricing and risk metrics is implemented in C++: ``computeCapFloorMetrics(Market market, ArgType1 x1, ArgType2 x2, …)``. 

This C++ function is wrapped and can be used in *Python* in this way: 
>>> import MyAnalytics
>>> res = MyAnalytics.computeCapFloorMetrics(mkt, x, y, z, …)``

