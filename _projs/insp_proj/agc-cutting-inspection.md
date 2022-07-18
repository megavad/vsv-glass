---
title: AGC cutting line inspection
permalink: /projs/insp_proj/
position: 0
#redirect_from:
#  - /
#  - /docs/quickstart/
#  - /docs/extras/
---

## Idea
This application is for scanning glass for white rounds 20mm+ in diameter, which represents small (<1mm in diameter) defects detected by precise laser measurement system during float process and marked with color.
{::nomarkdown}
<img src="/img/typical_float.jpg">
{:/}

{: .note .info}
Typical float glass factory

Continuous float glass ribbon from furnace dividing into rectangles with special size to minimize waste in next cutting operations (in accordance with planned model of the car), and we are detecting white rounds on that rectangles.



{::nomarkdown}
<tr><td>
<img alt="rectangle glass before VSM cutting" title="rectangle glass before VSM cutting" src="/img/conv_before_vsm.png"></td><td><img src="/img/glass_scrapped_ksm.png"></td>
</tr>
{:/}

{: .note .info}
On the left there is a rectangle glass before VSM cutting, on the right you could see a frame with scrapped piece of this rectangle with defect on the edge

These rectangles dividing into another smaller quadrangles, some of them could contain white rounds(as described above) and should not be processed but scrapped.
{::nomarkdown}
<img src="/img/rectangle.png">
{:/}

{: .note .info}
Rectangle with affected quadrangle: defect is represented by rectangle because of detection procedure, its resolution is 10mm, so we need to extend defected area to exclude error (Ex.: when front edge of round could be between IR detectors).

## Economics

This glass is cheaper, automation of scrapping and processing time saving is reasonable.
Picture below represents first variant of solution.

{::nomarkdown}
<img src="/img/schema_first.svg">
{:/}
{: .note .info}
This was the first variant of the system.
