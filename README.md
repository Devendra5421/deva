# regression

Linear Regession
# use the code
```py


import pandas as pd
import numpy as np
from matplotlib import pyplot as plt

class LinearRegression():
    def __init__(self, X ,Y):
        self.X = X
        self.Y = Y
        f_data = pd.DataFrame()
        f_data['X'] = self.X
        f_data['Y'] = self.Y
        sum_x = f_data['X'].sum()
        sum_y = f_data['Y'].sum()
        sum_xy = (f_data['X']*f_data['Y']).sum()
        sum_x2 = (f_data['X']*f_data['X']).sum()
        n = len(f_data)
        print(sum_x, sum_y ,sum_xy, sum_x2 ,n)
        pass
    def m(self):
        f_data = pd.DataFrame()
        f_data['X'] = self.X
        f_data['Y'] = self.Y
        sum_x = f_data['X'].sum()
        sum_y = f_data['Y'].sum()
        sum_xy = (f_data['X']*f_data['Y']).sum()
        sum_x2 = (f_data['X']*f_data['X']).sum()
        n = len(f_data)
        
        m = ((n * sum_xy) - (sum_x * sum_y))/((n * sum_x2) - (sum_x) ** 2)
        
        
        print(m)
        
    def coef(self):
        f_data = pd.DataFrame()
        f_data['X'] = self.X
        f_data['Y'] = self.Y
        sum_x = f_data['X'].sum()
        sum_y = f_data['Y'].sum()
        sum_xy = (f_data['X']*f_data['Y']).sum()
        sum_x2 = (f_data['X']*f_data['X']).sum()
        n = len(f_data)
        m = ((n * sum_xy) - (sum_x * sum_y))/((n * sum_x2) - (sum_x) ** 2)
        coef = ((sum_y) - (m*sum_x))/n
        print(coef)
        pass
    def y(self):
        f_data = pd.DataFrame()
        f_data['X'] = self.X
        f_data['Y'] = self.Y
        sum_x = f_data['X'].sum()
        sum_y = f_data['Y'].sum()
        sum_xy = (f_data['X']*f_data['Y']).sum()
        sum_x2 = (f_data['X']*f_data['X']).sum()
        n = len(f_data)
        m = ((n * sum_xy) - (sum_x * sum_y))/((n * sum_x2) - (sum_x) ** 2)
        coef = ((sum_y) - (m*sum_x))/n
        y = [m * x + coef for x in f_data['X']]
        
        print(y)
        
        pass
   

    def visualize(self):
        f_data = pd.DataFrame()
        f_data['X'] = self.X
        f_data['Y'] = self.Y
        plt.scatter(f_data['X'], f_data['Y'])
        plt.xlabel("values")
        plt.ylabel("Frequency")
        plt.grid()
        plt.title("LinearRegression")
        plt.show()
        pass
obj = LinearRegression([1, 2, 3, 4, 5, 6, 7], [1.5, 3.8, 6.7, 9.0, 11.2, 13.6, 16])
obj.m()
obj.coef()
obj.y()

obj.visualize()
    

```