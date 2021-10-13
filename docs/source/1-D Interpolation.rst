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

``X = list containing abscissae for the interpolation`` 

``Y = list containing ordinate for the interpolation`` This is of same the same length as ``X``. 

``x = known value(s)`` This can be scalar or vector. 

Below is the *optional* parameters for this function: 

``InterpolationType = 'linear', 'quadratic' or 'cubic'``. If this is not provided, 'linear' will be used as default. 

Some examples **Python** code is shown below: 

*Example 1* 

``>>> import MyAnalytics`` 

``>>> X = [4.0, 6.0, 8.0, 10.0, 12.0, 14.0]`` 

``>>> Y = [8.5, 12.5, 16.5, 20.5, 24.5, 28.5]`` 

``>>> x = 4.5`` 

``>>> y = MyAnalytics.compute1DInterpolation(X, Y, InterpolationType='linear', x)`` 

``>>> print(y)`` 

Output will look similar to this: 

``>>> 8.5`` 

*Example 2* 

``>>> import MyAnalytics`` 

``>>> X = [4.0, 6.0, 8.0, 10.0, 12.0, 14.0]`` 

``>>> Y = [8.5, 12.5, 16.5, 20.5, 24.5, 28.5]`` 

``>>> x = [4.5, 5.0]`` 

``>>> y = MyAnalytics.compute1DInterpolation(X, Y, InterpolationType='linear', x)`` 

``>>> print(y)`` 

Output will look similar to this: 

``>>> [9.5, 10.5]`` 

The C++ function can also be called in **Excel** using below formula: 

``=mycompute1DInterpolation(X, Y, InterpolationType, x)`` 

Similar to the *Python* code snippet, ``X``, ``Y`` and ``x`` are *mandatory* parameters and ``InterpolationType`` is *optional* parameter. 

The description of the parameters and the default values of the *optional* parameter is similar to as explained in the *Python* code snippet. 

Below example shows how the function can be called in *Excel*: 

  .. image:: mycompute1DInterpolation.JPG
    :width: 1500
