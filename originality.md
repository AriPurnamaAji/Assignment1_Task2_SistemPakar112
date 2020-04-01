
# Assignment 1 
## Task 2 (3D Rotation)
### Ari Purnama Aji_1313617008_Sistem Pakar 112

#### Berikut merupakan kodingan yang saya ambil dari dokumentasi matplotlib (mplot3d tutorial) yang saya gunakan untuk memplot gambar 3D.
referensi link : https://matplotlib.org/mpl_toolkits/mplot3d/tutorial.html

```python
%matplotlib notebook
import numpy as np
from PIL import Image
import matplotlib.pyplot as plt
from mpl_toolkits.mplot3d import Axes3D
from matplotlib import cm
from matplotlib.ticker import LinearLocator
```


```python
# Menampilkan Visualisasi
fig = plt.figure()
ax = fig.gca(projection='3d')
```


```python
# Membuat semua koordinat x yang ingin dipakai
X = np.arange(-200, 200, 1)
# Membuat semua koordinat y yang ingin dipakai
Y = np.arange(-200, 200, 1)

# Membuat kombinasi semua titik
X, Y = np.meshgrid(X, Y)
# Membuat semua koordinat z yang ingin dipakai
Z = np.zeros(X.shape)

# Membuat matriks yang parameter koordinatnya disesuaikan format matriks pada diagram kartesian 
# dan nilai setiap element matriksnya dibatasi dari range 0-1
colors = G.copy().transpose((1, 0, 2))/255
```


```python

# Plot permukaan dengan face color yang diambil dari matriks array yang telah dibuat
surf1 = ax.plot_surface(Xn, Yn, Zn, facecolors=colors, linewidth=0)
```

==================================================================================================