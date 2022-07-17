---
title: System introduction
permalink: /projs/gw/common/
position: 0
---

Automotive production has several automatic lines with various inspection systems. Some of systems should inspect serigraphy* on glass.

Serigraphy simplify future steps during automotive production (glass to vehicle gluing, computer vision guide-marking (for robotic gluing of sensor holder or  rear mirror holder)).

{: .note .info}
Serigraphy is a method of applying pigments on glass by silk screen printing with subsequent firing in the process of thermal hardening, which ensures a high degree of adhesion

{::nomarkdown}
<img src="/img/inspection.drawio.svg">
{:/}

We need to verify serigraphy quality, and this is a reason of usage printing inspection systems during this process.

Typical solution was provided by Pacific systems, Japan. It consists of couple of linescan cameras with high resolution, each camera is connected to framegrabber system (PCI card on dedicated computer which provides clk signal and handle camera signal). System has main computer with an operator application. It visualize data from framegrabber computers and calculate whether serigraphy status OK or NOK.

Then this status goes to Mitsubishi PLC via RS232,  then it translated to printing line PLC and in case of printing defect glass goes to "manual inspection conveyor", operator checks this print and serigraphy silkscreen mask, paint etc. Remote PC is showing a picture with defect of glass traveled to "manual inspection conveyor" (that could be far from inspection system) to simplify manual defect search.


* [Discussed options Options]({{ '/insp_proj/idea/options/' | relative_url }})
* [Solution]({{ '/insp_proj/solution/default/' | relative_url }})
* [Front Matter Defaults]({{ '/insp_proj/configuration/front-matter-defaults/' | relative_url }})
* [Environments]({{ '/insp_proj/configuration/environments/' | relative_url }})
* [Markdown Options]({{ '/insp_proj/configuration/markdown/' | relative_url }})
* [Liquid Options]({{ '/insp_proj/configuration/liquid/' | relative_url }})
* [Sass/SCSS Options]({{ '/insp_proj/configuration/sass/' | relative_url }})
* [Webrick Options]({{ '/insp_proj/configuration/webrick/' | relative_url }})
* [Incremental Regeneration]({{ '/insp_proj/configuration/incremental-regeneration/' | relative_url }})
