---
title: Инспекционная система для линии резки
permalink: /projs_ru/insp_proj/
position: 0
#redirect_from:
#  - /
#  - /docs/quickstart/
#  - /docs/extras/
---

#  Аннотация
Иногда при выпуске листового стекла с помощью флоат-професса возникают мелкие дефекты. Область возникновения этих дефектов утилизируется и снова подаётся в печь. Дефективная область обладает достаточно большой площадью, если её разделить на части, которые бы могли быть переработаны или утилизированы по отдельности - это было бы разумно.

Производство автостекла на заводе в г. Бор расположено рядом с флоат-процессом, и это производство может принять дефективные листы, поделенные на нужного размера прямоугольники, и использовать их для производства бокового стекла. Один дефект может затронуть от 1 до 4 заготовок(будущих боковых стёкол) из прямоугльной заготовки. На одном прямоугольном листе могут быть от 2 до 30 заготовок боковых стёкол.

Automotive production in Bor is located near float process, and it could get this glass sheet divided to rectangle pieces for side window production process. One defect could affect from 1 to 4 side window raw quadrangles (each one should become side window if no defect on it) from sheet. From 2 to 30 quadrangles could be on one sheet.  

#  Идея
Основная идея заключается в обнаружении позиции и размера дефекта, вычисления заготовок, которые будут им затронуты, и автоматическая утилизация эатронутых заготовок.

#  Решение
This application is for scanning glass for white rounds 20mm+ in diameter, which represents small (<1mm in diameter) defects detected by precise laser measurement system during float process and marked with white color.
{::nomarkdown}
<img src="/img/typical_float.jpg">
{:/}

{: .note .info}
Typical float glass factory

Continuous float glass ribbon from furnace dividing into rectangles with special size to minimize waste in next cutting operations (in accordance with planned model of the car), and we are detecting white rounds on that rectangles.



These rectangles dividing into another smaller quadrangles, some of them could contain white rounds(as described above) and should not be processed but scrapped.


{: .note .info}
{::nomarkdown}
<img src="/img/rectangle.png">
{:/}
Rectangle with affected quadrangle: defect is represented by rectangle because of detection procedure, its resolution is 10mm, so we need to extend defected area to exclude error (Ex.: when front edge of round could be between IR detectors).

{::nomarkdown}
<tr><td>
<img alt="rectangle glass before VSM cutting" title="rectangle glass before VSM cutting" src="/img/conv_before_vsm.png"></td><td><img src="/img/glass_scrapped_ksm.png"></td>
</tr>
{:/}

{: .note .info}
On the left there is a rectangle glass before VSM cutting, on the right you could see a scrapped piece of this rectangle with white-painted defect on the edge

## Economics

This glass is cheaper, automation of scrapping and processing time saving is reasonable.
Picture below represents first variant of solution.

{::nomarkdown}
<img src="/img/schema_first.svg">
{:/}
{: .note .info}
This was the first variant of the system.
