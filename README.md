# arplot

An augmented reality plotting library for [iris](https://scitools-iris.readthedocs.io/en/stable/).

![](https://i.imgur.com/XBFZp7X.gifv)

## Usage

```python
# Start ngrok serving the `arplot/static` directory (https is required for camera perms on mobile)
#
# $ cd arplot/static
# $ python -m http.server
# $ ngrok http 8000

import iris
from arplot import arplot

#  Load some global data such as https://s3.eu-west-2.amazonaws.com/aws-earth-mo-examples/cafef7005477edb001aa7dc50eab78c5ef89d420.nc
data = iris.load_cube("path/to/data.nc")

#  Slice a single altitude layer.
data_slice = data[0, 12, :, :]

#  Plot and QR code should show
arplot.plot(data_slice)

#  Point phone at QR code and open URL

#  Point phone at Hiro anchor and view image
```
