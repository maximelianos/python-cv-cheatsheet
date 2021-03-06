# Python 3

```
"{:04d}".format(1543) # flag, width, type
"{:.2f}".format(0.1543) # flag, precision, type
"3".zfill(4) = "0003"
```

## glob

```
from pathlib import Path
from glob import glob
os.remove(path)
shutil.copy(src, dest)
file_list = sorted(glob('frames/*.png'))  # file_list = ['frames/1.png', ...]
file_list = sorted(Path('dir').rglob('*.png'))
```

## Paths

```
import os
path = "/universe/milkyway/earth.jpg"
os.path.basename(path) == "earth.jpg"
os.path.exists(path) == True
```

## Image I/O

```
import cv2
import skimage
from skimage import io
image = cv2.imread(path)[:, :, ::-1].astype(np.float64) # BGR, uint8, 0-255. (H, W, 3) in all cases
image = io.imread(path)
image = skimage.img_as_float(image) # uint8, 0-255. (H, W) in case of grayscale images
image = cv2.resize(image, (w//2, h//2))
cv2.imwrite(dest, image, [cv2.IMWRITE_JPEG_QUALITY, 100])
io.imsave(dest, image, quality=100)
image = image[:, :, np.newaxis] # Image is (H, W), we need (H, W, 3)
image = np.tile(image, 3)
```
