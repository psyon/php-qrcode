# qrcode.php

### Generate QR Codes. MIT license.

Use from a PHP script:

```
include 'qrcode.php';

$generator = new QRCode($data, $options);

/* Output directly to standard output. */
$generator->output_image();

/* Create bitmap image. */
$image = $generator->render_image();
imagepng($image);
imagedestroy($image);
```

Use with GET or POST:

```
qrcode.php?s={symbology}&d={data}&{options}
```

e.g.

```
qrcode.php?s=qr&d=HELLO%20WORLD&sf=8&ms=r&md=0.8
```

#### Options:
`s` - Symbology (type of barcode). One of:
```
    qr
    qr-l
    qr-m
    qr-q
    qr-h
```

`d` - Data. Encode in Shift-JIS for kanji mode.

`w` - Width of image. Overrides `sf` or `sx`.

`h` - Height of image. Overrides `sf` or `sy`.

`sf` - Scale factor. Default is 1 for linear barcodes or 4 for matrix barcodes.

`sx` - Horizontal scale factor. Overrides `sf`.

`sy` - Vertical scale factor. Overrides `sf`.

`p` - Padding. Default is 10 for linear barcodes or 0 for matrix barcodes.

`pv` - Top and bottom padding. Default is value of `p`.

`ph` - Left and right padding. Default is value of `p`.

`pt` - Top padding. Default is value of `pv`.

`pl` - Left padding. Default is value of `ph`.

`pr` - Right padding. Default is value of `ph`.

`pb` - Bottom padding. Default is value of `pv`.

`bc` - Background color in `#RRGGBB` format.

`fc` - Foreground color in `#RRGGBB` format.

`md` - Module density. A number between 0 and 1. Default is 1. Applies to matrix barcodes only.

`wq` - Width of quiet area units. Default is 1. Use 0 to suppress quiet area.

`wm` - Width of narrow modules and spaces. Default is 1.
