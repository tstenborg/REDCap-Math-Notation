# REDCap-Math-Notation

Rendering LaTeX math notation as images in REDCap online surveys.

This repository holds digital assets associated with the article "Mathematical notation in REDCap online data collection instruments" [[1](#references)]. That article discusses LaTeX-style markup of mathematical notation, rendered as images for use in REDCap [[2](#references), [3](#references)] online data collection instruments. Example survey questions were drawn from a study of students' perceptions of physico-mathematical concepts [[4](#references)].

---

<figure style="height:893px;">
  <img src="Images/survey_screenshot.png" alt="REDCap survey with LaTeX-derived mathematical notation." width="532" height="893">
  <figcaption>Figure 1. REDCap survey with LaTeX-derived mathematical notation.<br/>Equations are SVG images generated via LuaLaTeX and pdftocairo.<br/>Adapted from Stenborg [<a href="#references">1</a>].</figcaption>
</figure>

---

## Table of Contents

* [Key Files](#key-files)
* [Software Requirements](#software-requirements)
* [Testing](#testing)
* [Getting Started](#getting-started)
* [Acknowledgments](#acknowledgments)
* [References](#references)

## Key Files

| File | Notes |
| :--- | :--- |
| LaTeX/Equation[dd].ltx | LaTeX equation generation files. |
| Images/Equation[dd].svg | Vector graphics rendering of LaTeX equations. |
| PhysicoMathematicalConcepts.zip | REDCap instrument. |

## Software Requirements

| Software | Notes |
| :--- | :--- |
| LuaLaTeX | Free in major TeX distributions. Available [here](https://www.latex-project.org). |
| REDCap<br>&nbsp;<br>&nbsp; | Details [here](https://project-redcap.org/).<br>&nbsp;&nbsp;&nbsp;Free for non-profit, institutional use.<br>&nbsp;&nbsp;&nbsp;Fee-based cloud or other hosted service otherwise. |
| pdftocairo<br>&nbsp;<br>&nbsp; | Free.<br>&nbsp;&nbsp;&nbsp;Linux, macOS: available in poppler-utils.<br>&nbsp;&nbsp;&nbsp;Windows: available in MiKTeX or poppler-utils. |

### LuaLaTeX Configuration

Please ensure the LuaLaTeX environment has the following packages installed:

- standalone.
- unicode-math.

## Testing

Testing OS: Windows 11 (version 25H2, OS build 26200.8037).

### 1. LaTeX/Equation[dd].ltx

Typesetting the LaTeX files was tested with LuaLaTeX, in TeXworks (version 0.6.11), bundled with MiKTeX (version 26.2).

### 2. Images/Equation[dd].svg

Conversion of LuaLaTeX-output PDF files to SVG files was via pdftocairo (version 24.04.0) at a command line.

### 3. PhysicoMathematicalConcepts.zip

Import of the instrument file was tested with REDCap version 16.1.1. Note, the links to image resources pertain to a specific REDCap File Repository. They will need modification for your REDCap project, e.g., via the REDCap Online Designer.

Online display of the data collection instrument (a survey) was tested with Microsoft Edge (version 146.0.3856.62).

## Getting Started

### Mathematics-to-image Rendering

Vector graphics (SVG) files of example equations, for Web display, are available in the Images folder of this repo.

They were generated via a two-step process:

1. LuaLaTeX was used to produce PDF files from LaTeX mathematical markup. The *standalone* document class was used to crop PDF bounds to mathematics content. Example LaTeX files are available in the LaTeX folder of this repo.

2. pdftocairo was used to convert the PDF files to SVG format. Example command line usage of pdftocairo is given below.

```
pdftocairo -svg Equation01.pdf Equation01.svg
```

### Managing Images

REDCap instruments can be configured to display images online with the REDCap Online Designer. Images can be included in instrument field labels, for example, by specifying a relevant `src` attribute of a HTML `<img>` tag. Target images may be stored remotely, or locally to a REDCap environment via the REDCap File Repository.

### Example REDCap Survey

An example REDCap data collection instrument (PhysicoMathematicalConcepts.zip) is available in this repo. It demonstrates use of LaTeX to style and typeset mathematical notation online, albeit indirectly, via LaTeX rendered as images.

The instrument ZIP file may be uploaded into a REDCap project.

The associated images are the SVG files in this repo. They may also be uploaded into a REDCap project File Repository, or other remotely accessible location, and associated links updated in Online Designer. Note, the example survey used HTML/CSS for manually fine-tuning equation image sizes and positioning.

### Font Consistency

In testing the instrument in REDCap, the survey design options were set to use the Arial font. Text in field labels was explicitly set to use Arial via the Online Designer. LaTeX files were also configured to output Arial content.

Font choice is a matter for REDCap instrument designers. Consistency across design elements, such as that described here, is however recommended.

## Acknowledgments

This work used REDCap electronic data capture tools [[2](#references), [3](#references)]. REDCap (Research Electronic Data Capture) is a secure, web-based software platform designed to support data capture for research studies, providing:

- an intuitive interface for validated data capture,
- audit trails for tracking data manipulation and export procedures,
- automated export procedures for seamless data downloads to common statistical packages, and
- procedures for data integration and interoperability with external sources.

## References

1. Stenborg, T 2026, "Mathematical notation in REDCap online data collection instruments", TUGboat, vol. 47, no. 1, pp. 89&ndash;90, in press.<br>
[View at publisher](https://doi.org/10.47397/tb/47-1/tb145stenborg-redcap) &nbsp; [SciX](https://scixplorer.org/abs/2026TUGbt..47...89S/abstract)

2. Harris, PA, Taylor, R, Thielke, R, Payne, J, Gonzalez, N & Conde, JG 2009, "Research electronic data capture (REDCap)&mdash;A metadata-driven methodology and workflow process for providing translational research informatics support", J. Biomed. Inform., vol. 42, no. 2, pp. 377&ndash;381.<br>
[View PDF](https://www.sciencedirect.com/science/article/pii/S1532046408001226/pdfft?md5=e9591bfb19d67fb3bf82fd90e2e10cff&pid=1-s2.0-S1532046408001226-main.pdf) &nbsp; [View at publisher](https://doi.org/10.1016/j.jbi.2008.08.010) &nbsp; [SciX](https://scixplorer.org/abs/2009JBI....42..377H/abstract)

3. Harris, PA, Taylor, R, Minor, BL, Elliott, V, Fernandez, M, O'Neal, L, McLeod, L, Delacqua, G, Delacqua, F, Kirby, J & Duda, SN 2019, "The REDCap consortium: Building an international community of software platform partners", J. Biomed. Inform., vol. 95, article 103208.<br>
[View PDF](https://www.sciencedirect.com/science/article/pii/S1532046419301261/pdfft?md5=869ae08741efa5eb215d18fd291d9805&pid=1-s2.0-S1532046419301261-main.pdf) &nbsp; [View at publisher](https://doi.org/10.1016/j.jbi.2019.103208) &nbsp; [SciX](https://scixplorer.org/abs/2019JBioI..95j3208H/abstract)

4. Mwangala, KP & Shumba, O 2016, "Physico-mathematical Conceptual Difficulties among First Year Students Learning Introductory University Physics", Am. J. Educ. Res., vol. 4, no. 17, pp. 1238&ndash;1244.<br>
[View at publisher](https://www.sciepub.com/EDUCATION/abstract/6712) &nbsp; [SciX](https://scixplorer.org/abs/2016AJEdR...4.1238K/abstract)
