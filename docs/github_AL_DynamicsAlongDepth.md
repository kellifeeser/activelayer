---
title: "**Active Layer survey: Exploring communities along depth profiles**"
subtitle: "Investigating landscape, regional, and local-scale diversity and dynamics of local-scale assembly / structuring along active layer depth profiles"
author: "Kelli Feeser"
date: '2023-11-06'
output:
  bookdown::html_document2:
    code_folding: hide
    css: styles.css
    number_sections: yes
    toc: yes
    toc_depth: 4
    fig.caption: yes
    keep_md: yes
  html_document: 
    code_folding: hide
    css: test.css
    fig_height: 4.5
    fig_width: 7
    number_sections: yes
    theme: cosmo
    toc: yes
    toc_depth: 3
  html_notebook: 
    code_folding: hide
    css: test.css
    fig_height: 4.5
    fig_width: 7
    number_sections: yes
    theme: cosmo
    toc: yes
    toc_depth: 3
---





\
\

\

#### **Terms:** {.unlisted .unnumbered}

-   **Landscape-scale** = all Taylor Valley samples

-   **Regional-scale** = within basin and/or reach

    -   n = 2 basins (LHSS and WHC)

    -   n=4 reaches (upslope and downslope within each basin)

-   **Local-scale** = within each pit

    -   n = 4 pits per reach (max)

    -   n = 16 total survey pits

-   **Depth profile** = discrete 5 cm soil samples from soil surface to permafrost interface (up to 30 cm)

    -   n = 7 depth samples per pit (max)

    -   metadata factor descriptions

        -   `Depth`

            -   7 levels: 0 cm, 5 cm, 10 cm, 15 cm, 20 cm, 25 cm, 30 cm

        -   `Depth2`

            -   Surface: 0 cm [0,5)

            -   Intermediate: 5 - 25 cm (depending on pit)

            -   Permafrost interface: 20 - 30 cm (depending on pit)

        -   `Depth3_combo0and5`

            -   Surface: 0 cm & 5 cm [0,10)

            -   Intermediate: 10 - 25 cm (depending on pit)

            -   Permafrost interface: 20 - 30 cm (depending on pit)

-   **Regional species pool** = γ-diversity of OTUs present within each basin and/or reach

    -   *note: with 4 spatial scales to contend with (whole valley, basin, reach, and pit) the 'landscape-regional-local scale' & α, β γ-diversity terminology gets a little messy...*

        -   options to deal with this include dropping the whole valley scale, then landscape = basin, regional = reach, and local = pit

        -   but I think it might be more interesting to keep landscape = whole valley and have regional = reach, this would let us do some analyses related to edaphic variable impacts on assembly / structure

\

------------------------------------------------------------------------

------------------------------------------------------------------------

# Survey Analysis Framework {.unnumbered}

\

**Big Picture:**\
\
*Investigating landscape, regional, and local-scale diversity and dynamics of local-scale assembly & structuring along active layer depth profiles*\

-   How does the larger regional species pool influence the assembly of microbial communities along the active layer depth profiles?\

**Goals:**

1.  Describe patterns in β-diversity along depth profiles (including taxonomy)

    1.1. by basin

    1.2. by reach

    1.3. individually

2.  Explore γ-diversity

    2.1. at landscape-scale (whole valley)

    2.2. within each basin

    2.3. within each reach

3.  Investigate assembly mechanisms / species sorting / environmental filtering along depth profiles by incorporating edaphic variables

\

------------------------------------------------------------------------

------------------------------------------------------------------------

\

# Import clean OTU tables {.unlisted .unnumbered .hidden}

\



# ⍺-diversity {.tabset .tabset-pills}

\

## full descriptions of metadata factors {.unnumbered}

\


```{=html}
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />

<style>
.earrows {color:silver;font-size:11px;}

fcap {
 font-family: Verdana;
 font-size: 12px;
 color: MidnightBlue
 }

smg {
 font-family: Verdana;
 font-size: 10px;
 color: &#808080;
}

hr.thinhr { margin-top: 0.15em; margin-bottom: 0.15em; }

span.xscript {
position: relative;
}
span.xscript sub {
position: absolute;
left: 0.1em;
bottom: -1ex;
}
</style>

<title>Survey: Alpha Diversity Measures with Metadata Descriptives</title>
<font color="MidnightBlue"><div align=center><span style="font-weight:bold">Survey: Alpha Diversity Measures with Metadata <br><br> 23  Variables   74  Observations</span></div></font>
<hr class="thinhr">
<span style="font-weight:bold">Experiment</span>
<style>
 .hmisctable652130 {
 border: none;
 font-size: 85%;
 }
 .hmisctable652130 td {
 text-align: center;
 padding: 0 1ex 0 1ex;
 }
 .hmisctable652130 th {
 color: MidnightBlue;
 text-align: center;
 padding: 0 1ex 0 1ex;
 font-weight: normal;
 }
 </style>
 <table data-quarto-disable-processing="true" class="hmisctable652130">
 <tr><th>n</th><th>missing</th><th>distinct</th><th>value</th></tr>
 <tr><td>74</td><td>0</td><td>1</td><td>ActiveLayer_S</td></tr>
 </table>

<pre style="font-size:85%;">
 Value      ActiveLayer_S
 Frequency             74
 Proportion             1 </pre>

<hr class="thinhr">
<span style="font-weight:bold">LocationAbbrev</span>
<style>
 .hmisctable228663 {
 border: none;
 font-size: 85%;
 }
 .hmisctable228663 td {
 text-align: center;
 padding: 0 1ex 0 1ex;
 }
 .hmisctable228663 th {
 color: MidnightBlue;
 text-align: center;
 padding: 0 1ex 0 1ex;
 font-weight: normal;
 }
 </style>
 <table data-quarto-disable-processing="true" class="hmisctable228663">
 <tr><th>n</th><th>missing</th><th>distinct</th></tr>
 <tr><td>74</td><td>0</td><td>2</td></tr>
 </table>

<pre style="font-size:85%;">
 Value       LHSS   WHC
 Frequency     40    34
 Proportion 0.541 0.459 </pre>

<hr class="thinhr">
<span style="font-weight:bold">Location</span>
<style>
 .hmisctable936408 {
 border: none;
 font-size: 85%;
 }
 .hmisctable936408 td {
 text-align: center;
 padding: 0 1ex 0 1ex;
 }
 .hmisctable936408 th {
 color: MidnightBlue;
 text-align: center;
 padding: 0 1ex 0 1ex;
 font-weight: normal;
 }
 </style>
 <table data-quarto-disable-processing="true" class="hmisctable936408">
 <tr><th>n</th><th>missing</th><th>distinct</th></tr>
 <tr><td>74</td><td>0</td><td>2</td></tr>
 </table>

<pre style="font-size:85%;">
 Value      Lake Hoare South Shore      Worm Herder Creek
 Frequency                      40                     34
 Proportion                  0.541                  0.459 </pre>

<hr class="thinhr">
<span style="font-weight:bold">FullDescription</span><div style='float: right; text-align: right;'><img src="data:image/png;base64,
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" alt="image" /></div>
<style>
 .hmisctable358474 {
 border: none;
 font-size: 85%;
 }
 .hmisctable358474 td {
 text-align: center;
 padding: 0 1ex 0 1ex;
 }
 .hmisctable358474 th {
 color: MidnightBlue;
 text-align: center;
 padding: 0 1ex 0 1ex;
 font-weight: normal;
 }
 </style>
 <table data-quarto-disable-processing="true" class="hmisctable358474">
 <tr><th>n</th><th>missing</th><th>distinct</th></tr>
 <tr><td>74</td><td>0</td><td>74</td></tr>
 </table>

<style>
 .hmisctable366269 {
 border: none;
 font-size: 85%;
 }
 .hmisctable366269 td {
 text-align: right;
 padding: 0 1ex 0 1ex;
 }
 .hmisctable366269 th {
 color: Black;
 text-align: center;
 padding: 0 1ex 0 1ex;
 font-weight: bold;
 }
 </style>
 <table data-quarto-disable-processing="true" class="hmisctable366269">
 <tr><td><font color="MidnightBlue">lowest</font> :</td><td>LHSS_DownSlope_Pit1_00cm</td><td>LHSS_DownSlope_Pit1_05cm</td><td>LHSS_DownSlope_Pit1_10cm</td><td>LHSS_DownSlope_Pit1_15cm</td><td>LHSS_DownSlope_Pit1_30cm</td></tr>
 <tr><td><font color="MidnightBlue">highest</font>:</td><td>WHC_UpSlope_Pit4_05cm   </td><td>WHC_UpSlope_Pit4_10cm   </td><td>WHC_UpSlope_Pit4_15cm   </td><td>WHC_UpSlope_Pit4_20cm   </td><td>WHC_UpSlope_Pit4_25cm   </td></tr>
 </table>

<hr class="thinhr">
<span style="font-weight:bold">Basin</span>
<style>
 .hmisctable949003 {
 border: none;
 font-size: 85%;
 }
 .hmisctable949003 td {
 text-align: center;
 padding: 0 1ex 0 1ex;
 }
 .hmisctable949003 th {
 color: MidnightBlue;
 text-align: center;
 padding: 0 1ex 0 1ex;
 font-weight: normal;
 }
 </style>
 <table data-quarto-disable-processing="true" class="hmisctable949003">
 <tr><th>n</th><th>missing</th><th>distinct</th></tr>
 <tr><td>74</td><td>0</td><td>2</td></tr>
 </table>

<pre style="font-size:85%;">
 Value      Lake Bonney  Lake Hoare
 Frequency           34          40
 Proportion       0.459       0.541 </pre>

<hr class="thinhr">
<span style="font-weight:bold">Site</span>
<style>
 .hmisctable845588 {
 border: none;
 font-size: 85%;
 }
 .hmisctable845588 td {
 text-align: center;
 padding: 0 1ex 0 1ex;
 }
 .hmisctable845588 th {
 color: MidnightBlue;
 text-align: center;
 padding: 0 1ex 0 1ex;
 font-weight: normal;
 }
 </style>
 <table data-quarto-disable-processing="true" class="hmisctable845588">
 <tr><th>n</th><th>missing</th><th>distinct</th></tr>
 <tr><td>74</td><td>0</td><td>2</td></tr>
 </table>

<pre style="font-size:85%;">
 Value      DownSlope   UpSlope
 Frequency         35        39
 Proportion     0.473     0.527 </pre>

<hr class="thinhr">
<span style="font-weight:bold">BasinSite</span><div style='float: right; text-align: right;'><img src="data:image/png;base64,
iVBORw0KGgoAAAANSUhEUgAAAA0AAAANCAYAAABy6+R8AAAEDmlDQ1BrQ0dDb2xvclNwYWNlR2VuZXJpY1JHQgAAOI2NVV1oHFUUPpu5syskzoPUpqaSDv41lLRsUtGE2uj+ZbNt3CyTbLRBkMns3Z1pJjPj/KRpKT4UQRDBqOCT4P9bwSchaqvtiy2itFCiBIMo+ND6R6HSFwnruTOzu5O4a73L3PnmnO9+595z7t4LkLgsW5beJQIsGq4t5dPis8fmxMQ6dMF90A190C0rjpUqlSYBG+PCv9rt7yDG3tf2t/f/Z+uuUEcBiN2F2Kw4yiLiZQD+FcWyXYAEQfvICddi+AnEO2ycIOISw7UAVxieD/Cyz5mRMohfRSwoqoz+xNuIB+cj9loEB3Pw2448NaitKSLLRck2q5pOI9O9g/t/tkXda8Tbg0+PszB9FN8DuPaXKnKW4YcQn1Xk3HSIry5ps8UQ/2W5aQnxIwBdu7yFcgrxPsRjVXu8HOh0qao30cArp9SZZxDfg3h1wTzKxu5E/LUxX5wKdX5SnAzmDx4A4OIqLbB69yMesE1pKojLjVdoNsfyiPi45hZmAn3uLWdpOtfQOaVmikEs7ovj8hFWpz7EV6mel0L9Xy23FMYlPYZenAx0yDB1/PX6dledmQjikjkXCxqMJS9WtfFCyH9XtSekEF+2dH+P4tzITduTygGfv58a5VCTH5PtXD7EFZiNyUDBhHnsFTBgE0SQIA9pfFtgo6cKGuhooeilaKH41eDs38Ip+f4At1Rq/sjr6NEwQqb/I/DQqsLvaFUjvAx+eWirddAJZnAj1DFJL0mSg/gcIpPkMBkhoyCSJ8lTZIxk0TpKDjXHliJzZPO50dR5ASNSnzeLvIvod0HG/mdkmOC0z8VKnzcQ2M/Yz2vKldduXjp9bleLu0ZWn7vWc+l0JGcaai10yNrUnXLP/8Jf59ewX+c3Wgz+B34Df+vbVrc16zTMVgp9um9bxEfzPU5kPqUtVWxhs6OiWTVW+gIfywB9uXi7CGcGW/zk98k/kmvJ95IfJn/j3uQ+4c5zn3Kfcd+AyF3gLnJfcl9xH3OfR2rUee80a+6vo7EK5mmXUdyfQlrYLTwoZIU9wsPCZEtP6BWGhAlhL3p2N6sTjRdduwbHsG9kq32sgBepc+xurLPW4T9URpYGJ3ym4+8zA05u44QjST8ZIoVtu3qE7fWmdn5LPdqvgcZz8Ww8BWJ8X3w0PhQ/wnCDGd+LvlHs8dRy6bLLDuKMaZ20tZrqisPJ5ONiCq8yKhYM5cCgKOu66Lsc0aYOtZdo5QCwezI4wm9J/v0X23mlZXOfBjj8Jzv3WrY5D+CsA9D7aMs2gGfjve8ArD6mePZSeCfEYt8CONWDw8FXTxrPqx/r9Vt4biXeANh8vV7/+/16ffMD1N8AuKD/A/8leAvFY9bLAAAAOGVYSWZNTQAqAAAACAABh2kABAAAAAEAAAAaAAAAAAACoAIABAAAAAEAAAANoAMABAAAAAEAAAANAAAAAIoCOpQAAADlSURBVCgVzVI7CoRQDJyVPYDgCWysFCvv4wG8hyfwIJZ6BAVBsNJC7BT8gViI4FsTcEFxt9hqUyRvJpmQF/JwXVfYtg2yIAhA7zAMYRgGc5+c6PtekPm+L/YikSQJ46tblkVYliUk6rRt223DeZ7hOA7quub8NE2I4xgsulXsZFEU8DwPURSdSr6K9vFOxQf4KjqKrvFJRJZlkGUZZVlyPs9zSJIEimTEp2mKcRwZs0jXdSiKgqqqmNQ0DaZpvhekqirjrus4/9N4fy7iRTRNg3VdMQwDf7RtW74CimTE01Xs58b4BfuxgqFEdb8rAAAAAElFTkSuQmCC" alt="image" /></div>
<style>
 .hmisctable287644 {
 border: none;
 font-size: 85%;
 }
 .hmisctable287644 td {
 text-align: center;
 padding: 0 1ex 0 1ex;
 }
 .hmisctable287644 th {
 color: MidnightBlue;
 text-align: center;
 padding: 0 1ex 0 1ex;
 font-weight: normal;
 }
 </style>
 <table data-quarto-disable-processing="true" class="hmisctable287644">
 <tr><th>n</th><th>missing</th><th>distinct</th></tr>
 <tr><td>74</td><td>0</td><td>4</td></tr>
 </table>

<pre style="font-size:85%;">
 Value      LHSS_DownSlope   LHSS_UpSlope  WHC_DownSlope    WHC_UpSlope
 Frequency              19             21             16             18
 Proportion          0.257          0.284          0.216          0.243 </pre>

<hr class="thinhr">
<span style="font-weight:bold">Pit</span><div style='float: right; text-align: right;'><img src="data:image/png;base64,
iVBORw0KGgoAAAANSUhEUgAAAA0AAAANCAYAAABy6+R8AAAEDmlDQ1BrQ0dDb2xvclNwYWNlR2VuZXJpY1JHQgAAOI2NVV1oHFUUPpu5syskzoPUpqaSDv41lLRsUtGE2uj+ZbNt3CyTbLRBkMns3Z1pJjPj/KRpKT4UQRDBqOCT4P9bwSchaqvtiy2itFCiBIMo+ND6R6HSFwnruTOzu5O4a73L3PnmnO9+595z7t4LkLgsW5beJQIsGq4t5dPis8fmxMQ6dMF90A190C0rjpUqlSYBG+PCv9rt7yDG3tf2t/f/Z+uuUEcBiN2F2Kw4yiLiZQD+FcWyXYAEQfvICddi+AnEO2ycIOISw7UAVxieD/Cyz5mRMohfRSwoqoz+xNuIB+cj9loEB3Pw2448NaitKSLLRck2q5pOI9O9g/t/tkXda8Tbg0+PszB9FN8DuPaXKnKW4YcQn1Xk3HSIry5ps8UQ/2W5aQnxIwBdu7yFcgrxPsRjVXu8HOh0qao30cArp9SZZxDfg3h1wTzKxu5E/LUxX5wKdX5SnAzmDx4A4OIqLbB69yMesE1pKojLjVdoNsfyiPi45hZmAn3uLWdpOtfQOaVmikEs7ovj8hFWpz7EV6mel0L9Xy23FMYlPYZenAx0yDB1/PX6dledmQjikjkXCxqMJS9WtfFCyH9XtSekEF+2dH+P4tzITduTygGfv58a5VCTH5PtXD7EFZiNyUDBhHnsFTBgE0SQIA9pfFtgo6cKGuhooeilaKH41eDs38Ip+f4At1Rq/sjr6NEwQqb/I/DQqsLvaFUjvAx+eWirddAJZnAj1DFJL0mSg/gcIpPkMBkhoyCSJ8lTZIxk0TpKDjXHliJzZPO50dR5ASNSnzeLvIvod0HG/mdkmOC0z8VKnzcQ2M/Yz2vKldduXjp9bleLu0ZWn7vWc+l0JGcaai10yNrUnXLP/8Jf59ewX+c3Wgz+B34Df+vbVrc16zTMVgp9um9bxEfzPU5kPqUtVWxhs6OiWTVW+gIfywB9uXi7CGcGW/zk98k/kmvJ95IfJn/j3uQ+4c5zn3Kfcd+AyF3gLnJfcl9xH3OfR2rUee80a+6vo7EK5mmXUdyfQlrYLTwoZIU9wsPCZEtP6BWGhAlhL3p2N6sTjRdduwbHsG9kq32sgBepc+xurLPW4T9URpYGJ3ym4+8zA05u44QjST8ZIoVtu3qE7fWmdn5LPdqvgcZz8Ww8BWJ8X3w0PhQ/wnCDGd+LvlHs8dRy6bLLDuKMaZ20tZrqisPJ5ONiCq8yKhYM5cCgKOu66Lsc0aYOtZdo5QCwezI4wm9J/v0X23mlZXOfBjj8Jzv3WrY5D+CsA9D7aMs2gGfjve8ArD6mePZSeCfEYt8CONWDw8FXTxrPqx/r9Vt4biXeANh8vV7/+/16ffMD1N8AuKD/A/8leAvFY9bLAAAAOGVYSWZNTQAqAAAACAABh2kABAAAAAEAAAAaAAAAAAACoAIABAAAAAEAAAANoAMABAAAAAEAAAANAAAAAIoCOpQAAADNSURBVCgVvZI7CoRAEERrh000EjyBiZHiLTyHNxRDPYQgaCKCmCn4y0VnpwtMlmVDK2leDTU93czLsixd1zVs20ae50iSBEVRIAxD/FKaprT1PM9alGWZNo4uy5K8LIuO41h3XUfeto3n6tdttzcMA7s2TUPrPE/Wv6E7/F2fC72ltWzPcRz0fc+XtG0LpRSkisSvqgr7vpMZCoIArutCBhf5vo8oinBdF9nzPLLZJvm5mZ7rxEVM04TjOGC+CQc13wrjOEKqSHzhdV3JHyqKcq4d9XooAAAAAElFTkSuQmCC" alt="image" /></div>
<style>
 .hmisctable339595 {
 border: none;
 font-size: 85%;
 }
 .hmisctable339595 td {
 text-align: center;
 padding: 0 1ex 0 1ex;
 }
 .hmisctable339595 th {
 color: MidnightBlue;
 text-align: center;
 padding: 0 1ex 0 1ex;
 font-weight: normal;
 }
 </style>
 <table data-quarto-disable-processing="true" class="hmisctable339595">
 <tr><th>n</th><th>missing</th><th>distinct</th><th>Info</th><th>Mean</th><th>Gmd</th></tr>
 <tr><td>74</td><td>0</td><td>4</td><td>0.937</td><td>2.459</td><td>1.265</td></tr>
 </table>

<pre style="font-size:85%;">
 Value          1     2     3     4
 Frequency     19    20    17    18
 Proportion 0.257 0.270 0.230 0.243 </pre>


For the frequency table, variable is rounded to the nearest 0
<hr class="thinhr">
<span style="font-weight:bold">Depth</span><div style='float: right; text-align: right;'><img src="data:image/png;base64,
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" alt="image" /></div>
<style>
 .hmisctable535421 {
 border: none;
 font-size: 85%;
 }
 .hmisctable535421 td {
 text-align: center;
 padding: 0 1ex 0 1ex;
 }
 .hmisctable535421 th {
 color: MidnightBlue;
 text-align: center;
 padding: 0 1ex 0 1ex;
 font-weight: normal;
 }
 </style>
 <table data-quarto-disable-processing="true" class="hmisctable535421">
 <tr><th>n</th><th>missing</th><th>distinct</th></tr>
 <tr><td>74</td><td>0</td><td>7</td></tr>
 </table>

<pre style="font-size:85%;">
 Value      00 cm 05 cm 10 cm 15 cm 20 cm 25 cm 30 cm
 Frequency      9    14    14    12    12     8     5
 Proportion 0.122 0.189 0.189 0.162 0.162 0.108 0.068 </pre>

<hr class="thinhr">
<span style="font-weight:bold">Depth2</span><div style='float: right; text-align: right;'><img src="data:image/png;base64,
iVBORw0KGgoAAAANSUhEUgAAAAoAAAANCAYAAACQN/8FAAAEDmlDQ1BrQ0dDb2xvclNwYWNlR2VuZXJpY1JHQgAAOI2NVV1oHFUUPpu5syskzoPUpqaSDv41lLRsUtGE2uj+ZbNt3CyTbLRBkMns3Z1pJjPj/KRpKT4UQRDBqOCT4P9bwSchaqvtiy2itFCiBIMo+ND6R6HSFwnruTOzu5O4a73L3PnmnO9+595z7t4LkLgsW5beJQIsGq4t5dPis8fmxMQ6dMF90A190C0rjpUqlSYBG+PCv9rt7yDG3tf2t/f/Z+uuUEcBiN2F2Kw4yiLiZQD+FcWyXYAEQfvICddi+AnEO2ycIOISw7UAVxieD/Cyz5mRMohfRSwoqoz+xNuIB+cj9loEB3Pw2448NaitKSLLRck2q5pOI9O9g/t/tkXda8Tbg0+PszB9FN8DuPaXKnKW4YcQn1Xk3HSIry5ps8UQ/2W5aQnxIwBdu7yFcgrxPsRjVXu8HOh0qao30cArp9SZZxDfg3h1wTzKxu5E/LUxX5wKdX5SnAzmDx4A4OIqLbB69yMesE1pKojLjVdoNsfyiPi45hZmAn3uLWdpOtfQOaVmikEs7ovj8hFWpz7EV6mel0L9Xy23FMYlPYZenAx0yDB1/PX6dledmQjikjkXCxqMJS9WtfFCyH9XtSekEF+2dH+P4tzITduTygGfv58a5VCTH5PtXD7EFZiNyUDBhHnsFTBgE0SQIA9pfFtgo6cKGuhooeilaKH41eDs38Ip+f4At1Rq/sjr6NEwQqb/I/DQqsLvaFUjvAx+eWirddAJZnAj1DFJL0mSg/gcIpPkMBkhoyCSJ8lTZIxk0TpKDjXHliJzZPO50dR5ASNSnzeLvIvod0HG/mdkmOC0z8VKnzcQ2M/Yz2vKldduXjp9bleLu0ZWn7vWc+l0JGcaai10yNrUnXLP/8Jf59ewX+c3Wgz+B34Df+vbVrc16zTMVgp9um9bxEfzPU5kPqUtVWxhs6OiWTVW+gIfywB9uXi7CGcGW/zk98k/kmvJ95IfJn/j3uQ+4c5zn3Kfcd+AyF3gLnJfcl9xH3OfR2rUee80a+6vo7EK5mmXUdyfQlrYLTwoZIU9wsPCZEtP6BWGhAlhL3p2N6sTjRdduwbHsG9kq32sgBepc+xurLPW4T9URpYGJ3ym4+8zA05u44QjST8ZIoVtu3qE7fWmdn5LPdqvgcZz8Ww8BWJ8X3w0PhQ/wnCDGd+LvlHs8dRy6bLLDuKMaZ20tZrqisPJ5ONiCq8yKhYM5cCgKOu66Lsc0aYOtZdo5QCwezI4wm9J/v0X23mlZXOfBjj8Jzv3WrY5D+CsA9D7aMs2gGfjve8ArD6mePZSeCfEYt8CONWDw8FXTxrPqx/r9Vt4biXeANh8vV7/+/16ffMD1N8AuKD/A/8leAvFY9bLAAAAOGVYSWZNTQAqAAAACAABh2kABAAAAAEAAAAaAAAAAAACoAIABAAAAAEAAAAKoAMABAAAAAEAAAANAAAAAKqQRt8AAAB3SURBVCgVY3z+/Pl/BiQQFBQE5q1btw5JlIGBRUJCAkWAnZ0dzEcXZ0JRhYczgApZLl68iOKyL1++gPno4iz6+vooCnl4eMB8dHHqeqaoqIiBCd0KFHdAOf39/QxMly5dwiaHIcYCEnnx4gVc4ufPn2A2shhIAABjSB7ca3g/JwAAAABJRU5ErkJggg==" alt="image" /></div>
<style>
 .hmisctable765032 {
 border: none;
 font-size: 85%;
 }
 .hmisctable765032 td {
 text-align: center;
 padding: 0 1ex 0 1ex;
 }
 .hmisctable765032 th {
 color: MidnightBlue;
 text-align: center;
 padding: 0 1ex 0 1ex;
 font-weight: normal;
 }
 </style>
 <table data-quarto-disable-processing="true" class="hmisctable765032">
 <tr><th>n</th><th>missing</th><th>distinct</th></tr>
 <tr><td>74</td><td>0</td><td>3</td></tr>
 </table>

<pre style="font-size:85%;">
 Value                   Surface         Intermediate Permafrost Interface
 Frequency                     9                   53                   12
 Proportion                0.122                0.716                0.162 </pre>

<hr class="thinhr">
<span style="font-weight:bold">Depth3_combo0and5</span><div style='float: right; text-align: right;'><img src="data:image/png;base64,
iVBORw0KGgoAAAANSUhEUgAAAAoAAAANCAYAAACQN/8FAAAEDmlDQ1BrQ0dDb2xvclNwYWNlR2VuZXJpY1JHQgAAOI2NVV1oHFUUPpu5syskzoPUpqaSDv41lLRsUtGE2uj+ZbNt3CyTbLRBkMns3Z1pJjPj/KRpKT4UQRDBqOCT4P9bwSchaqvtiy2itFCiBIMo+ND6R6HSFwnruTOzu5O4a73L3PnmnO9+595z7t4LkLgsW5beJQIsGq4t5dPis8fmxMQ6dMF90A190C0rjpUqlSYBG+PCv9rt7yDG3tf2t/f/Z+uuUEcBiN2F2Kw4yiLiZQD+FcWyXYAEQfvICddi+AnEO2ycIOISw7UAVxieD/Cyz5mRMohfRSwoqoz+xNuIB+cj9loEB3Pw2448NaitKSLLRck2q5pOI9O9g/t/tkXda8Tbg0+PszB9FN8DuPaXKnKW4YcQn1Xk3HSIry5ps8UQ/2W5aQnxIwBdu7yFcgrxPsRjVXu8HOh0qao30cArp9SZZxDfg3h1wTzKxu5E/LUxX5wKdX5SnAzmDx4A4OIqLbB69yMesE1pKojLjVdoNsfyiPi45hZmAn3uLWdpOtfQOaVmikEs7ovj8hFWpz7EV6mel0L9Xy23FMYlPYZenAx0yDB1/PX6dledmQjikjkXCxqMJS9WtfFCyH9XtSekEF+2dH+P4tzITduTygGfv58a5VCTH5PtXD7EFZiNyUDBhHnsFTBgE0SQIA9pfFtgo6cKGuhooeilaKH41eDs38Ip+f4At1Rq/sjr6NEwQqb/I/DQqsLvaFUjvAx+eWirddAJZnAj1DFJL0mSg/gcIpPkMBkhoyCSJ8lTZIxk0TpKDjXHliJzZPO50dR5ASNSnzeLvIvod0HG/mdkmOC0z8VKnzcQ2M/Yz2vKldduXjp9bleLu0ZWn7vWc+l0JGcaai10yNrUnXLP/8Jf59ewX+c3Wgz+B34Df+vbVrc16zTMVgp9um9bxEfzPU5kPqUtVWxhs6OiWTVW+gIfywB9uXi7CGcGW/zk98k/kmvJ95IfJn/j3uQ+4c5zn3Kfcd+AyF3gLnJfcl9xH3OfR2rUee80a+6vo7EK5mmXUdyfQlrYLTwoZIU9wsPCZEtP6BWGhAlhL3p2N6sTjRdduwbHsG9kq32sgBepc+xurLPW4T9URpYGJ3ym4+8zA05u44QjST8ZIoVtu3qE7fWmdn5LPdqvgcZz8Ww8BWJ8X3w0PhQ/wnCDGd+LvlHs8dRy6bLLDuKMaZ20tZrqisPJ5ONiCq8yKhYM5cCgKOu66Lsc0aYOtZdo5QCwezI4wm9J/v0X23mlZXOfBjj8Jzv3WrY5D+CsA9D7aMs2gGfjve8ArD6mePZSeCfEYt8CONWDw8FXTxrPqx/r9Vt4biXeANh8vV7/+/16ffMD1N8AuKD/A/8leAvFY9bLAAAAOGVYSWZNTQAqAAAACAABh2kABAAAAAEAAAAaAAAAAAACoAIABAAAAAEAAAAKoAMABAAAAAEAAAANAAAAAKqQRt8AAACFSURBVCgVjY+xEQAREEXdjRmJAnShEokatKUFoT5UQQESibvZDc66wOwG/v/PH2avWusjyHjvMaWUCBVCGmM2oJTC/Of31joEfjHnfHhnXd3OuZUOTs45RSnlq/Te0VMGQMJhrQXB0VqjUgaAtUwIgVeMMfKK7K+hiMu01sDjjDFQKQPwAkonIdyI7o8tAAAAAElFTkSuQmCC" alt="image" /></div>
<style>
 .hmisctable482041 {
 border: none;
 font-size: 85%;
 }
 .hmisctable482041 td {
 text-align: center;
 padding: 0 1ex 0 1ex;
 }
 .hmisctable482041 th {
 color: MidnightBlue;
 text-align: center;
 padding: 0 1ex 0 1ex;
 font-weight: normal;
 }
 </style>
 <table data-quarto-disable-processing="true" class="hmisctable482041">
 <tr><th>n</th><th>missing</th><th>distinct</th></tr>
 <tr><td>74</td><td>0</td><td>3</td></tr>
 </table>

<pre style="font-size:85%;">
 Value                   Surface         Intermediate Permafrost Interface
 Frequency                    23                   39                   12
 Proportion                0.311                0.527                0.162 </pre>

<hr class="thinhr">
<span style="font-weight:bold">sample_sums.al.</span><div style='float: right; text-align: right;'><img src="data:image/png;base64,
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" alt="image" /></div>
<style>
 .hmisctable807365 {
 border: none;
 font-size: 85%;
 }
 .hmisctable807365 td {
 text-align: center;
 padding: 0 1ex 0 1ex;
 }
 .hmisctable807365 th {
 color: MidnightBlue;
 text-align: center;
 padding: 0 1ex 0 1ex;
 font-weight: normal;
 }
 </style>
 <table data-quarto-disable-processing="true" class="hmisctable807365">
 <tr><th>n</th><th>missing</th><th>distinct</th><th>Info</th><th>Mean</th><th>Gmd</th><th>.05</th><th>.10</th><th>.25</th><th>.50</th><th>.75</th><th>.90</th><th>.95</th></tr>
 <tr><td>74</td><td>0</td><td>74</td><td>1</td><td>6057</td><td>6018</td><td> 1257</td><td> 1432</td><td> 2124</td><td> 3808</td><td> 7312</td><td>13841</td><td>21239</td></tr>
 </table>

<span style="font-size: 85%;"><font color="MidnightBlue">lowest</font> :  1100  1189  1220  1239  1267 ,  <font color="MidnightBlue">highest</font>: 20288 23006 28137 29007 31171</span>
<hr class="thinhr">
<span style="font-weight:bold">Depthcm</span><div style='float: right; text-align: right;'><img src="data:image/png;base64,
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" alt="image" /></div>
<style>
 .hmisctable222437 {
 border: none;
 font-size: 85%;
 }
 .hmisctable222437 td {
 text-align: center;
 padding: 0 1ex 0 1ex;
 }
 .hmisctable222437 th {
 color: MidnightBlue;
 text-align: center;
 padding: 0 1ex 0 1ex;
 font-weight: normal;
 }
 </style>
 <table data-quarto-disable-processing="true" class="hmisctable222437">
 <tr><th>n</th><th>missing</th><th>distinct</th><th>Info</th><th>Mean</th><th>Gmd</th></tr>
 <tr><td>74</td><td>0</td><td>7</td><td>0.975</td><td>13.24</td><td>10.16</td></tr>
 </table>

<pre style="font-size:85%;">
 Value          0     5    10    15    20    25    30
 Frequency      9    14    14    12    12     8     5
 Proportion 0.122 0.189 0.189 0.162 0.162 0.108 0.068 </pre>


For the frequency table, variable is rounded to the nearest 0
<hr class="thinhr">
<span style="font-weight:bold">Observed</span><div style='float: right; text-align: right;'><img src="data:image/png;base64,
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" alt="image" /></div>
<style>
 .hmisctable696413 {
 border: none;
 font-size: 74%;
 }
 .hmisctable696413 td {
 text-align: center;
 padding: 0 1ex 0 1ex;
 }
 .hmisctable696413 th {
 color: MidnightBlue;
 text-align: center;
 padding: 0 1ex 0 1ex;
 font-weight: normal;
 }
 </style>
 <table data-quarto-disable-processing="true" class="hmisctable696413">
 <tr><th>n</th><th>missing</th><th>distinct</th><th>Info</th><th>Mean</th><th>Gmd</th><th>.05</th><th>.10</th><th>.25</th><th>.50</th><th>.75</th><th>.90</th><th>.95</th></tr>
 <tr><td>74</td><td>0</td><td>63</td><td>1</td><td>216.5</td><td>60.43</td><td> 97.45</td><td>131.50</td><td>194.75</td><td>222.00</td><td>252.75</td><td>276.90</td><td>288.70</td></tr>
 </table>

<span style="font-size: 85%;"><font color="MidnightBlue">lowest</font> :  58  66  76  89 102 ,  <font color="MidnightBlue">highest</font>: 288 290 291 309 324</span>
<hr class="thinhr">
<span style="font-weight:bold">Chao1</span><div style='float: right; text-align: right;'><img src="data:image/png;base64,
iVBORw0KGgoAAAANSUhEUgAAAJcAAAANCAYAAACkYvxcAAAEDmlDQ1BrQ0dDb2xvclNwYWNlR2VuZXJpY1JHQgAAOI2NVV1oHFUUPpu5syskzoPUpqaSDv41lLRsUtGE2uj+ZbNt3CyTbLRBkMns3Z1pJjPj/KRpKT4UQRDBqOCT4P9bwSchaqvtiy2itFCiBIMo+ND6R6HSFwnruTOzu5O4a73L3PnmnO9+595z7t4LkLgsW5beJQIsGq4t5dPis8fmxMQ6dMF90A190C0rjpUqlSYBG+PCv9rt7yDG3tf2t/f/Z+uuUEcBiN2F2Kw4yiLiZQD+FcWyXYAEQfvICddi+AnEO2ycIOISw7UAVxieD/Cyz5mRMohfRSwoqoz+xNuIB+cj9loEB3Pw2448NaitKSLLRck2q5pOI9O9g/t/tkXda8Tbg0+PszB9FN8DuPaXKnKW4YcQn1Xk3HSIry5ps8UQ/2W5aQnxIwBdu7yFcgrxPsRjVXu8HOh0qao30cArp9SZZxDfg3h1wTzKxu5E/LUxX5wKdX5SnAzmDx4A4OIqLbB69yMesE1pKojLjVdoNsfyiPi45hZmAn3uLWdpOtfQOaVmikEs7ovj8hFWpz7EV6mel0L9Xy23FMYlPYZenAx0yDB1/PX6dledmQjikjkXCxqMJS9WtfFCyH9XtSekEF+2dH+P4tzITduTygGfv58a5VCTH5PtXD7EFZiNyUDBhHnsFTBgE0SQIA9pfFtgo6cKGuhooeilaKH41eDs38Ip+f4At1Rq/sjr6NEwQqb/I/DQqsLvaFUjvAx+eWirddAJZnAj1DFJL0mSg/gcIpPkMBkhoyCSJ8lTZIxk0TpKDjXHliJzZPO50dR5ASNSnzeLvIvod0HG/mdkmOC0z8VKnzcQ2M/Yz2vKldduXjp9bleLu0ZWn7vWc+l0JGcaai10yNrUnXLP/8Jf59ewX+c3Wgz+B34Df+vbVrc16zTMVgp9um9bxEfzPU5kPqUtVWxhs6OiWTVW+gIfywB9uXi7CGcGW/zk98k/kmvJ95IfJn/j3uQ+4c5zn3Kfcd+AyF3gLnJfcl9xH3OfR2rUee80a+6vo7EK5mmXUdyfQlrYLTwoZIU9wsPCZEtP6BWGhAlhL3p2N6sTjRdduwbHsG9kq32sgBepc+xurLPW4T9URpYGJ3ym4+8zA05u44QjST8ZIoVtu3qE7fWmdn5LPdqvgcZz8Ww8BWJ8X3w0PhQ/wnCDGd+LvlHs8dRy6bLLDuKMaZ20tZrqisPJ5ONiCq8yKhYM5cCgKOu66Lsc0aYOtZdo5QCwezI4wm9J/v0X23mlZXOfBjj8Jzv3WrY5D+CsA9D7aMs2gGfjve8ArD6mePZSeCfEYt8CONWDw8FXTxrPqx/r9Vt4biXeANh8vV7/+/16ffMD1N8AuKD/A/8leAvFY9bLAAAAOGVYSWZNTQAqAAAACAABh2kABAAAAAEAAAAaAAAAAAACoAIABAAAAAEAAACXoAMABAAAAAEAAAANAAAAABXzt1gAAAQ9SURBVFgJ7Zg5SyZBEIZH/bzvA+8DxANBNDAUA02MjAxE8CdoZCz4D/wRpmJgYCD+CVEQz0Q88b7v3n5qt4ae+QZ3Fw274JuZ6nqruvrtlu13g+PjY6O/7OxsMzU1ZYIgMNPT0+G4xpPe4MBPTk6anJyctJyJiQmJV1ZWpsWS6v1trLm52bS0tJjGxsZIvcXFRZlnYWHB7O3tyffMzIyprq429LC8vCxj8/Pzkjc4OCj+5uZmpM7o6KgpKioy+fn5Es/IyJB1sUb3NzAwYBoaGmSsoKAgEgM3PDwsY6urq+bo6CiMk6ecra+vyzi8a+2qqirT1dUV6UlxQ0NDRueam5sTTF9fn+T29/eLPzY2Jn3B49LSksQ6OjrMyMiIyczMNFlZWWZlZUXG4bK9vT2ce3Z2Vmq4/Ol+1NXVmfHx8UhfGuPNuWEd7liqtrbWruu3WSIDS6w4vN2YYuJvF09+PMeSISl2YWmxeK1/8VOpVMA8mDuXPbwyVlFREY4XFxcHlsyAHuymReK5ubni19TUBOXl5fLNwx6qgF4/Pz/DMfy4kU8vmPbjYvLy8sRlXrdP8ugLY+64MZfdpEiOzq81ySktLRUMWMz+YYvPWlkzcyonYFgXffJTLsDpGqhRUlIieY+Pj7jSp/auPKovAOfBOaC2G09nzUnwn56B7zDgD9d32PO5XzLgD9eX9Pjgdxjwh+s77PncLxlIra2thQAusaenp+KfnJwEbiwExT7AYeSRH8+5uLiQ+Pv7e1pMAv/5eHl5kYvjx8dHpN7u7q5U4s3lFbMqLXh7ewvoYXt7W8b29/cl7+7uTvyNjQ25yIpjH1dXVwG13Qu9+6048l9fX8VNit/c3Ehsa2srMAZB9tvIU86YG3Pj8PT09BRZ2+XlpeBub2/Dvg4ODgTz8PAgsfv7e/HB0hf7sLOzIzHqXV9fh/MoF9q/gOzj8PBQ8sBj8Kf7CRYe1ReA80ja/1Rvb28IQZWoguHW78ZCUOxD1QF55MdzVLGgSuKxWKl/clFbqBI2wa2nm9nW1hb09PRIrfr6elFe9GDluIy1trZKniq27u7uiFpEOaKM3A1XteY2SD4KDUuKo+awzs7OsB988pQz5sZYjxo88cfhru3s7EzCqDmdq6mpSTCFhYUSQ62Rg1qmL7714FGvrKxM5mEu5QKcq0Dtf61InqpF+NM+wMKj+tqvvpP23/+zqOz4948z4A/Xj1PqCyoD/nApE/794wz4w/XjlPqCykBKlQsDXGJRHRhvNyaDCQ8XT348Ry+HKKp4LKHcX4e4yHMpRdG59VSVopZ0HGUGjh7Oz8+ltsZRnRgqR7/xUUr06l7ok9QgOfSCuVgZsI/n52f5ZF7thwHyVKmqMhfgnwdzoXDdHO1dawJFwIABi6Hm8FmrcqOcgGFd2qfWA6droAZqVGvgu8pWeXT7AqPGOYjv/y+Dui5fxlW9dAAAAABJRU5ErkJggg==" alt="image" /></div>
<style>
 .hmisctable826124 {
 border: none;
 font-size: 85%;
 }
 .hmisctable826124 td {
 text-align: center;
 padding: 0 1ex 0 1ex;
 }
 .hmisctable826124 th {
 color: MidnightBlue;
 text-align: center;
 padding: 0 1ex 0 1ex;
 font-weight: normal;
 }
 </style>
 <table data-quarto-disable-processing="true" class="hmisctable826124">
 <tr><th>n</th><th>missing</th><th>distinct</th><th>Info</th><th>Mean</th><th>Gmd</th><th>.05</th><th>.10</th><th>.25</th><th>.50</th><th>.75</th><th>.90</th><th>.95</th></tr>
 <tr><td>74</td><td>0</td><td>74</td><td>1</td><td>334.3</td><td>113.2</td><td>136.6</td><td>207.2</td><td>291.3</td><td>329.3</td><td>410.4</td><td>458.3</td><td>476.3</td></tr>
 </table>

<span style="font-size: 85%;"><font color="MidnightBlue">lowest</font> : 75.1    81.4    118     124.286 143.167 ,  <font color="MidnightBlue">highest</font>: 474.708 479.233 492.016 505.241 531.875</span>
<hr class="thinhr">
<span style="font-weight:bold">se.chao1</span><div style='float: right; text-align: right;'><img src="data:image/png;base64,
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" alt="image" /></div>
<style>
 .hmisctable781792 {
 border: none;
 font-size: 85%;
 }
 .hmisctable781792 td {
 text-align: center;
 padding: 0 1ex 0 1ex;
 }
 .hmisctable781792 th {
 color: MidnightBlue;
 text-align: center;
 padding: 0 1ex 0 1ex;
 font-weight: normal;
 }
 </style>
 <table data-quarto-disable-processing="true" class="hmisctable781792">
 <tr><th>n</th><th>missing</th><th>distinct</th><th>Info</th><th>Mean</th><th>Gmd</th><th>.05</th><th>.10</th><th>.25</th><th>.50</th><th>.75</th><th>.90</th><th>.95</th></tr>
 <tr><td>74</td><td>0</td><td>74</td><td>1</td><td>31.8</td><td>13.29</td><td>14.72</td><td>18.73</td><td>23.73</td><td>30.01</td><td>37.15</td><td>47.00</td><td>50.72</td></tr>
 </table>

<span style="font-size: 85%;"><font color="MidnightBlue">lowest</font> : 8.6785  10.4091 13.6612 14.3328 14.9258 ,  <font color="MidnightBlue">highest</font>: 49.7729 52.4765 53.2518 70.3463 72.2256</span>
<hr class="thinhr">
<span style="font-weight:bold">ACE</span><div style='float: right; text-align: right;'><img src="data:image/png;base64,
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" alt="image" /></div>
<style>
 .hmisctable605984 {
 border: none;
 font-size: 85%;
 }
 .hmisctable605984 td {
 text-align: center;
 padding: 0 1ex 0 1ex;
 }
 .hmisctable605984 th {
 color: MidnightBlue;
 text-align: center;
 padding: 0 1ex 0 1ex;
 font-weight: normal;
 }
 </style>
 <table data-quarto-disable-processing="true" class="hmisctable605984">
 <tr><th>n</th><th>missing</th><th>distinct</th><th>Info</th><th>Mean</th><th>Gmd</th><th>.05</th><th>.10</th><th>.25</th><th>.50</th><th>.75</th><th>.90</th><th>.95</th></tr>
 <tr><td>74</td><td>0</td><td>74</td><td>1</td><td>344.5</td><td>111</td><td>146.1</td><td>226.6</td><td>305.6</td><td>343.3</td><td>423.4</td><td>458.4</td><td>488.5</td></tr>
 </table>

<span style="font-size: 85%;"><font color="MidnightBlue">lowest</font> : 76.3742 88.469  126.824 145.93  146.231 ,  <font color="MidnightBlue">highest</font>: 487.444 490.363 491.951 505.705 510.129</span>
<hr class="thinhr">
<span style="font-weight:bold">se.ACE</span><div style='float: right; text-align: right;'><img src="data:image/png;base64,
iVBORw0KGgoAAAANSUhEUgAAAJcAAAANCAYAAACkYvxcAAAEDmlDQ1BrQ0dDb2xvclNwYWNlR2VuZXJpY1JHQgAAOI2NVV1oHFUUPpu5syskzoPUpqaSDv41lLRsUtGE2uj+ZbNt3CyTbLRBkMns3Z1pJjPj/KRpKT4UQRDBqOCT4P9bwSchaqvtiy2itFCiBIMo+ND6R6HSFwnruTOzu5O4a73L3PnmnO9+595z7t4LkLgsW5beJQIsGq4t5dPis8fmxMQ6dMF90A190C0rjpUqlSYBG+PCv9rt7yDG3tf2t/f/Z+uuUEcBiN2F2Kw4yiLiZQD+FcWyXYAEQfvICddi+AnEO2ycIOISw7UAVxieD/Cyz5mRMohfRSwoqoz+xNuIB+cj9loEB3Pw2448NaitKSLLRck2q5pOI9O9g/t/tkXda8Tbg0+PszB9FN8DuPaXKnKW4YcQn1Xk3HSIry5ps8UQ/2W5aQnxIwBdu7yFcgrxPsRjVXu8HOh0qao30cArp9SZZxDfg3h1wTzKxu5E/LUxX5wKdX5SnAzmDx4A4OIqLbB69yMesE1pKojLjVdoNsfyiPi45hZmAn3uLWdpOtfQOaVmikEs7ovj8hFWpz7EV6mel0L9Xy23FMYlPYZenAx0yDB1/PX6dledmQjikjkXCxqMJS9WtfFCyH9XtSekEF+2dH+P4tzITduTygGfv58a5VCTH5PtXD7EFZiNyUDBhHnsFTBgE0SQIA9pfFtgo6cKGuhooeilaKH41eDs38Ip+f4At1Rq/sjr6NEwQqb/I/DQqsLvaFUjvAx+eWirddAJZnAj1DFJL0mSg/gcIpPkMBkhoyCSJ8lTZIxk0TpKDjXHliJzZPO50dR5ASNSnzeLvIvod0HG/mdkmOC0z8VKnzcQ2M/Yz2vKldduXjp9bleLu0ZWn7vWc+l0JGcaai10yNrUnXLP/8Jf59ewX+c3Wgz+B34Df+vbVrc16zTMVgp9um9bxEfzPU5kPqUtVWxhs6OiWTVW+gIfywB9uXi7CGcGW/zk98k/kmvJ95IfJn/j3uQ+4c5zn3Kfcd+AyF3gLnJfcl9xH3OfR2rUee80a+6vo7EK5mmXUdyfQlrYLTwoZIU9wsPCZEtP6BWGhAlhL3p2N6sTjRdduwbHsG9kq32sgBepc+xurLPW4T9URpYGJ3ym4+8zA05u44QjST8ZIoVtu3qE7fWmdn5LPdqvgcZz8Ww8BWJ8X3w0PhQ/wnCDGd+LvlHs8dRy6bLLDuKMaZ20tZrqisPJ5ONiCq8yKhYM5cCgKOu66Lsc0aYOtZdo5QCwezI4wm9J/v0X23mlZXOfBjj8Jzv3WrY5D+CsA9D7aMs2gGfjve8ArD6mePZSeCfEYt8CONWDw8FXTxrPqx/r9Vt4biXeANh8vV7/+/16ffMD1N8AuKD/A/8leAvFY9bLAAAAOGVYSWZNTQAqAAAACAABh2kABAAAAAEAAAAaAAAAAAACoAIABAAAAAEAAACXoAMABAAAAAEAAAANAAAAABXzt1gAAARGSURBVFgJ7Vk5L21RFN645pmY51AghsRQ+geEqCT8BaVGq1AoJTqtKFR6LTUKYhbEPM/jfudb93377Xfu8bzilHsl5+6117T3+s6+sT9XHR8faz6JiYl6aGhIK6X01NSUsdP/P+P8/Lzkz87OBua3tbWJf25uLtDPNRYWFiRuenraxI2Ojoptb2/P2BjPsbOzU3d1dcX4e3t7dW5uruSjv7GxsZiYpaUl8U9OTuqRkRHRU1JSTM74+LjJ6ejoMPacnByjx8fHi97U1CRjaWmp7uvr0wMDAzohIUH39/frnp4enZaWpoHF4OCgzsvLM/nYGx7WiUQiuqKiQtZFfnV1ta6srJRa6LmxsVHi8/PzZZyYmDC1FhcXzX7b29vFjnqoX19fL2NDQ4OM6+vrJpZYcpyZmZGY7u5uwZB2exweHtY4P7YtUlxc7K0Vlbi4OOU1LRMPMGX7GPPT6DUpIR5ggflJSUn/9LP+2dmZqN6BMHUyMzPFhn0lJycz9K8R9eHz7z01NVV5L8zEZmVlxcQ8Pj6KH71fXV2JDkwo2dnZJod9wGfXZSz93oFQWBsPamGEDTpigHdQPusgzjsQZl3oX19fko8eMYegJgR7pBQUFJg84sV+mOcdCAkvKipS6DtI8C4h3hdN9urHFr6MjAyzJ8whf9COzt2nQyA0BNzhCg1KV8iPgDtcfkTcPDQE3OEKDUpXyI9AZHl52dhwUby8vJT5/v6+sn0m6Adlc3NTIra3t1VhYWFMNC/NW1tbihfFmCDPsLGxIebd3V2zD4+JiG1lZUUuw0F5qP/x8WFyGHN9fS12zo+OjmJiDg4OxI3eT05ORP/8/GSKOjw8NDnsA06s55enpycxvb29KayNudZa9Pf3d7mUowbwDspHLATj6+urWRc63hPseD8vLy8Sh5oQ9gB9bW1NcZ8cWZd5z8/PCFWrq6sKJCdIdnZ2xHxzcxOILZynp6eyL/vMRFpbW009sBayvaqqKmX7TNAPCpuora0NzE9PT5cKdXV1gX6WJ6upqakxcSUlJeJuaWn5li2iPhiZf+9gnWRIKFJWVhYTA8YDQe88VGRhsJeXl5sc9gG7XRdzCFk3GCHWJluEjgMHrFEDeAflo38cBIxgeuwHOtkibGBwELI+798WMseH928GBZwh3C9xZR72BWlubv6WLfKLBjaJvXIvkvj7A2wTPdk+92fRRsjpoSLgDleocLpiNgLucNloOD1UBNzhChVOV8xGIMLLGoy4QJLlgBnYPjvpXzrZJn4+CcrHZRbynZ+1Ly4uRAXTYp37+3uxYc6fMxjPkZdl5tAOVoSLMOXu7s7Upe38/FxU9P7w8CA62RUmt7e3Jod9wG7XxRxCP4gB1kYdPNDB7KAjBngH5UerRN8J2CT7gY545MNGpkkCgj1S0A9JClgmBHkQ5pFlgu2RQUqA9cGfwuDH2tyLFSJ4cU+0/wKRLBo0ucrGtQAAAABJRU5ErkJggg==" alt="image" /></div>
<style>
 .hmisctable470043 {
 border: none;
 font-size: 74%;
 }
 .hmisctable470043 td {
 text-align: center;
 padding: 0 1ex 0 1ex;
 }
 .hmisctable470043 th {
 color: MidnightBlue;
 text-align: center;
 padding: 0 1ex 0 1ex;
 font-weight: normal;
 }
 </style>
 <table data-quarto-disable-processing="true" class="hmisctable470043">
 <tr><th>n</th><th>missing</th><th>distinct</th><th>Info</th><th>Mean</th><th>Gmd</th><th>.05</th><th>.10</th><th>.25</th><th>.50</th><th>.75</th><th>.90</th><th>.95</th></tr>
 <tr><td>74</td><td>0</td><td>74</td><td>1</td><td>10.42</td><td>2.26</td><td> 6.205</td><td> 7.930</td><td> 9.578</td><td>10.620</td><td>11.930</td><td>12.691</td><td>12.901</td></tr>
 </table>

<span style="font-size: 85%;"><font color="MidnightBlue">lowest</font> : 4.47473 4.59813 5.67585 6.18504 6.21651 ,  <font color="MidnightBlue">highest</font>: 12.8633 12.9723 13.592  13.7073 14.1845</span>
<hr class="thinhr">
<span style="font-weight:bold">Shannon</span><div style='float: right; text-align: right;'><img src="data:image/png;base64,
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" alt="image" /></div>
<style>
 .hmisctable816931 {
 border: none;
 font-size: 85%;
 }
 .hmisctable816931 td {
 text-align: center;
 padding: 0 1ex 0 1ex;
 }
 .hmisctable816931 th {
 color: MidnightBlue;
 text-align: center;
 padding: 0 1ex 0 1ex;
 font-weight: normal;
 }
 </style>
 <table data-quarto-disable-processing="true" class="hmisctable816931">
 <tr><th>n</th><th>missing</th><th>distinct</th><th>Info</th><th>Mean</th><th>Gmd</th><th>.05</th><th>.10</th><th>.25</th><th>.50</th><th>.75</th><th>.90</th><th>.95</th></tr>
 <tr><td>74</td><td>0</td><td>74</td><td>1</td><td>4.312</td><td>0.6901</td><td>2.406</td><td>3.678</td><td>4.252</td><td>4.439</td><td>4.706</td><td>4.961</td><td>5.071</td></tr>
 </table>

<span style="font-size: 85%;"><font color="MidnightBlue">lowest</font> : 1.78214 2.0092  2.07157 2.08891 2.57598 ,  <font color="MidnightBlue">highest</font>: 5.07047 5.07115 5.11229 5.13396 5.24583</span>
<hr class="thinhr">
<span style="font-weight:bold">Simpson</span><div style='float: right; text-align: right;'><img src="data:image/png;base64,
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" alt="image" /></div>
<style>
 .hmisctable195558 {
 border: none;
 font-size: 74%;
 }
 .hmisctable195558 td {
 text-align: center;
 padding: 0 1ex 0 1ex;
 }
 .hmisctable195558 th {
 color: MidnightBlue;
 text-align: center;
 padding: 0 1ex 0 1ex;
 font-weight: normal;
 }
 </style>
 <table data-quarto-disable-processing="true" class="hmisctable195558">
 <tr><th>n</th><th>missing</th><th>distinct</th><th>Info</th><th>Mean</th><th>Gmd</th><th>.05</th><th>.10</th><th>.25</th><th>.50</th><th>.75</th><th>.90</th><th>.95</th></tr>
 <tr><td>74</td><td>0</td><td>74</td><td>1</td><td>0.9475</td><td>0.05862</td><td>0.7259</td><td>0.9363</td><td>0.9587</td><td>0.9728</td><td>0.9822</td><td>0.9877</td><td>0.9887</td></tr>
 </table>

<pre style="font-size:85%;">
 Value      0.590 0.645 0.680 0.695 0.740 0.755 0.845 0.935 0.945 0.950 0.955 0.960
 Frequency      1     1     1     1     1     1     1     2     2     5     4     5
 Proportion 0.014 0.014 0.014 0.014 0.014 0.014 0.014 0.027 0.027 0.068 0.054 0.068
                                               
 Value      0.965 0.970 0.975 0.980 0.985 0.990
 Frequency      6    13     7    10    10     3
 Proportion 0.081 0.176 0.095 0.135 0.135 0.041 </pre>


For the frequency table, variable is rounded to the nearest 0.005
<hr class="thinhr">
<span style="font-weight:bold">InvSimpson</span><div style='float: right; text-align: right;'><img src="data:image/png;base64,
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" alt="image" /></div>
<style>
 .hmisctable914065 {
 border: none;
 font-size: 85%;
 }
 .hmisctable914065 td {
 text-align: center;
 padding: 0 1ex 0 1ex;
 }
 .hmisctable914065 th {
 color: MidnightBlue;
 text-align: center;
 padding: 0 1ex 0 1ex;
 font-weight: normal;
 }
 </style>
 <table data-quarto-disable-processing="true" class="hmisctable914065">
 <tr><th>n</th><th>missing</th><th>distinct</th><th>Info</th><th>Mean</th><th>Gmd</th><th>.05</th><th>.10</th><th>.25</th><th>.50</th><th>.75</th><th>.90</th><th>.95</th></tr>
 <tr><td>74</td><td>0</td><td>74</td><td>1</td><td>42.05</td><td>28.85</td><td> 3.67</td><td>15.71</td><td>24.20</td><td>36.80</td><td>56.08</td><td>81.22</td><td>88.88</td></tr>
 </table>

<span style="font-size: 85%;"><font color="MidnightBlue">lowest</font> : 2.44842 2.82872 3.17169 3.29919 3.86957 ,  <font color="MidnightBlue">highest</font>: 88.8079 89.0185 100.858 105.685 116.307</span>
<hr class="thinhr">
<span style="font-weight:bold">Fisher</span><div style='float: right; text-align: right;'><img src="data:image/png;base64,
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" alt="image" /></div>
<style>
 .hmisctable412067 {
 border: none;
 font-size: 74%;
 }
 .hmisctable412067 td {
 text-align: center;
 padding: 0 1ex 0 1ex;
 }
 .hmisctable412067 th {
 color: MidnightBlue;
 text-align: center;
 padding: 0 1ex 0 1ex;
 font-weight: normal;
 }
 </style>
 <table data-quarto-disable-processing="true" class="hmisctable412067">
 <tr><th>n</th><th>missing</th><th>distinct</th><th>Info</th><th>Mean</th><th>Gmd</th><th>.05</th><th>.10</th><th>.25</th><th>.50</th><th>.75</th><th>.90</th><th>.95</th></tr>
 <tr><td>74</td><td>0</td><td>63</td><td>1</td><td>83.85</td><td>33.24</td><td> 25.88</td><td> 39.13</td><td> 68.86</td><td> 84.02</td><td>102.96</td><td>119.31</td><td>127.78</td></tr>
 </table>

<span style="font-size: 85%;"><font color="MidnightBlue">lowest</font> : 13.0575 15.4314 18.5577 22.8803 27.4907 ,  <font color="MidnightBlue">highest</font>: 127.264 128.732 129.469 143.182 155.262</span>
<hr class="thinhr">
<br><br>
Variables with all observations missing:
<br>
<br><br>
<code style="font-size:0.8em">Control</code>
```

\

## Observed species {.unnumbered} 

\




\

Did the surface samples (0 and 5 cm) have higher richness than the intermediate
and Permafrost Interface samples?\

-    Answer: yes\


```r
wilcox.test(Observed ~ Depth3_combo0and5, data = Survey_alpha_meta,
            paired = F,p.adjust.method = "BH",alternative="less",
            subset = Depth3_combo0and5 %in% c("Permafrost Interface","Surface"))
```

```
## 
## 	Wilcoxon rank sum test with continuity correction
## 
## data:  Observed by Depth3_combo0and5
## W = 205, p-value = 0.9905
## alternative hypothesis: true location shift is less than 0
```





# β-diversity along depth profiles

## Basin
