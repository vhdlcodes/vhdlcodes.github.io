+++
author = "Prasad Pandit"
categories = ["VHDL","FPGA"]
date = 2018-09-18T02:24:43-07:00
description = "Simple 7-seg decoder in VHDL"
featured = ""
featuredalt = ""
featuredpath = ""
linktitle = ""
title = "7-seg decoder VHDL"
type = "post"

+++

Most of the FPGAs have 7-segment decoders. These 7-seg displays are of following type:

1. Common Anode
  * All the anode i.e. +ve pins of LEDs connected to '1' in digital design terms
  * Cathodes i.e. -ve pins are used to turn-on or turn-off LED segments by setting '0' or '1'
2. Common Cathode
  * All the cathode i.e. -ve pins of LEDs connected to '0' in digital design terms
  * Anodes i.e. +ve pins are used to turn-on or turn-off LED segments by setting '1' or '0'

Following is the code for 7-seg decoder. Depending on which board you are using, you will need to set value of seg_type parameter.

* '1' for common-anode
* '0' for common-cathode

Use a Applet below to play with the values that you can get when you click on individual segment.
You can select your 7-seg type by clicking on CMN Anode button. Compare these values with code below for better understanding.

<iframe src="https://editor.p5js.org/Tonystark4009/sketches/HkL3js_t7" style="width:410px; height:240px;"></iframe>

## Code:
<a class="github-button" href="https://github.com/vhdlcodes/seg7_decoder_vhdl/archive/master.zip" data-icon="octicon-cloud-download" data-size="large" aria-label="Download From GitHub" align="right">Download</a>
<script src="https://gist.github.com/prasadp4009/4a0d58cafa3739eb6f81e164188a05f4.js"></script>

<!-- Place this tag in your head or just before your close body tag. -->
<script async defer src="https://buttons.github.io/buttons.js"></script>
