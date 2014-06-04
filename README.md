we-jam-econo
============

A Dockerfile for building an image for testing and debugging Fiona, Rasterio,
and Shapely. GEOS and GDAL are also built from source in debug mode to 
assist with testing.

To build and image and run a container based on it is two steps.

```
$ docker build --tag we_jam_econo .
$ docker run -t -i we_jam_econo /bin/bash
```

This drops you into bash, where you can run the Fiona, Rasterio, and Shapely
tests.

```
root@79ca1bf969d2:/home# cd /home/rasterio
root@79ca1bf969d2:/home/rasterio# py.test
============================= test session starts ==============================
platform linux2 -- Python 2.7.6 -- pytest-2.5.1
collected 62 items

rasterio/tests/test_band.py .
rasterio/tests/test_blocks.py ...........
rasterio/tests/test_colormap.py .
rasterio/tests/test_coords.py .....
rasterio/tests/test_copy.py .
rasterio/tests/test_driver_management.py ..
rasterio/tests/test_dtypes.py ...
rasterio/tests/test_features_rasterize.py ..
rasterio/tests/test_features_shapes.py ....
rasterio/tests/test_features_sieve.py .
rasterio/tests/test_pad.py .
rasterio/tests/test_read.py ............
rasterio/tests/test_revolvingdoor.py .
rasterio/tests/test_tags.py ..
rasterio/tests/test_transform.py .
rasterio/tests/test_update.py ...
rasterio/tests/test_warp.py ....
rasterio/tests/test_write.py .......

========================== 62 passed in 2.98 seconds ==========================
```

