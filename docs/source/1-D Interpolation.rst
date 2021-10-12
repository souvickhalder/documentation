1-D Interpolation
=================

Overview
--------
This function takes abscissae (X) and ordinate (Y) and known x value(s) is(are) provided as inputs. Based on the interpolation type (e.g. linear, quadratic, cubic) mentioned, it outputs the interpolated value(s). 

.. note::

   This project is under active development. 

Version
-------
The current version for this API is **1.0.0**. 

Description about the API
-------------------------
Analytical function for 1-D Interpolation is implemented in C++. 

This function takes abscissae (``X``) and ordinate (``Y``) and known ``x`` value(s) and interpolation type as inputs. If ``x`` is a scalar, the function returns a scalar output. If ``x`` is a vector, the output will be a vector of same size as ``x``. 

.. note::

   Few *Assumptions* should be considered while using this API: ``X`` and ``Y`` must be of the same length. Currently this is used for linear, quadratic and cubic interolation methods. This will be extended for other interpolation methods. 
   
This C++ function is wrapped and can be used in **Python** using below code snippet: 

``>>> import MyAnalytics`` 

``>>> y = MyAnalytics.compute1DInterpolation(X, Y, InterpolationType='linear', x)`` 

Below are the *mandatory* parameters for this function: 

``X = abscissae for the interpolation`` 

``Y = ordinate for the interpolation`` This is of same the same length as ``X``. 
