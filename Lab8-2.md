## Lab 8-2 零基礎Python快速入門與實作, 2/2, W14

### 實作1185 + Final Result

![image](https://user-images.githubusercontent.com/89329121/142749401-e5e543da-ab4f-4069-bdcf-27370eaf4107.png)

### 程式
````python
### 實作1185
ts3 = 'Chi' # Please input your English name
!python --version #  Python 版本確認

import numpy as np
import matplotlib.pyplot as plt

x = np.arange(0, 2 * np.pi, 0.01)
y_sin = np.sin(x)
y_cos = np.cos(x)

y_sin2 = np.sin(x+pi)
y_cos2 = np.cos(x+pi)

plt.subplots_adjust( left=0.1, right=1.5, top=1.5, bottom=0.1, wspace=0.2, hspace=0.2)

plt.subplot(221)
plt.plot(x, y_sin, color ='r') # red
plt.title('sin_red by CHI')

plt.subplot(222)
plt.plot(x, y_cos, color ='g') # green
plt.title('cos_green by CHI')

plt.subplot(223)
plt.plot(x, y_sin2, color ='y') # yellow
plt.title('sin_yellow by CHI')

plt.subplot(224)
plt.plot(x, y_cos2, color ='b') # blue
plt.title('cos_blue by CHI')

plt.show()

### Final Result
from datetime import datetime
today = datetime.now()
print('*** Done by %s at ' % ts3,today, type(today))
````
