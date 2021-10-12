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

This C++ function is wrapped and can be used in *Python* using below code snippet: 

``>>> import MyAnalytics`` 

``>>> atm_vol_tenors = [30, 360, 720, 1800, 3600]`` 

``>>> atm_vol_surface = [[16.5, 16.5, 16.5, 16.5, 16.5], [16.5, 16.5, 16.5, 16.5, 16.5], [16.5, 16.5, 16.5, 16.5, 16.5, 16.5, 16.5, 16.5], [16.5, 16.5, 16.5, 16.5, 16.5, 16.5, 16.5, 16.5],[16.5, 16.5, 16.5, 16.5, 16.5, 16.5, 16.5, 16.5]]`` 

``>>> yield_curves_tenors = [30, 360, 720, 1800, 3600]`` 

``>>> yield_curves = [0.01, 0.012, 0.0125, 0.0127, 0.013]`` 

``>>> mkt = [atm_vol_tenors, atm_vol_surface, yield_curves_tenors, yield_curves]`` 

``>>> res = MyAnalytics.computeCapFloorMetrics(mkt, x, y, z, …)``

