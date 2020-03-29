
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

#### Berikut kodingan yang saya buat sendiri:

```python
# Membuat nHat yang akan dinormalisasi sehingga besaran vektornya selalu 1
nHat = np.array([97,8,1])
nHat = nHat*1/np.linalg.norm(nHat)

# Membuat matriks ekspansi dari vektor nHat
nHatCross = np.array([
    [0, -nHat[2], nHat[1]],
    [nHat[2], 0, -nHat[0]],
    [-nHat[1], nHat[0], 0]
])

# Menentukan besaran derajat rotasi 3D
teta = np.pi*45/180

# Mendapatkan matriks transformasi rotasi 3D
R = np.identity(3)+np.sin(teta)*nHatCross+(1-np.cos(teta))*(nHatCross@nHatCross)

# Membuat matriks XYZ
XYZ = np.array([X.flatten(), Y.flatten(), Z.flatten()])

# Membuat matriks XYZnew untuk melakukan operasi perkalian dengan matriks transformasi rotasi 3D
XYZnew = R @ XYZ

# Mengembalikan bentuk matriks XYZ menjadi matriks untuk setiap masing-masing koordinat 
# agar bisa dipakai sebagai parameter pada method plot_surface 
Xn = XYZnew[0].reshape(400,400)
Yn = XYZnew[1].reshape(400,400)
Zn = XYZnew[2].reshape(400,400)
```