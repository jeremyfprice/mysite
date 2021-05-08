---
title: "CV"
date: 2021-05-08
draft: false
hideLastModified: false
showInMenu: true
---

<style>
.column {
    float: left;
    margin-bottom: 0.15em;
}

.left,
.middle {
    width: 39%;
    margin-right: 2%
}

.right {
    width: 14%;
    text-align: right;
}
.row {
    margin-bottom: 0.4em;
}
.item {
    margin-bottom: 0.1em;
    padding-left: 2em;
    text-indent: -2em;
    word-wrap: normal;
}
.row:after {
    content: "";
    display: table;
    clear: both;
}
.straightTable {
    padding-left: 1.75em;
}
.straightTable td {
    padding: 0.25em;
    font-family: Spectral;
    vertical-align: top;
}
h2.cv {
    color: #990000;
    font-size: 1em;
    font-family: Rubik;
    font-weight: 500;
    text-align: left;
}
h3.cv {
    font-size: 1em;
    font-family: Spectral;
    font-style: italic;
    font-weight: 400;
    padding: 0;
    margin: 1em 0 0.5em 0;
    color: #191919
}
h3.top {
    font-size: 1em;
    font-family: Spectral;
    font-style: italic;
    font-weight: 400;
    padding: 0;
    margin: 0 0 0.5em 0;
    color: #191919
}
.content {
    width: 100%;
    margin: 1em auto;
    padding-top: 0.25em;
    overflow: auto;
}
.content .leftcol {
    float: left;
    width: 16%;
    margin-right: 3%;
}
.content .rightcol {
    float: right;
    width: 81%;
    padding-top: 0.55em;
}
.heading {
    width: 300px;
    margin: 0 auto;
    padding-top: 0.25em;
    overflow: auto;
    font-size: 10pt;
    border-bottom: solid 2px #990000;
}
h1.myname {
    font-size: 2em;
    font-family: Spectral;
    text-align: right;
    font-weight: 500;
    color: #191919;
    margin: 0;
    border-bottom: solid 0px;
}
.leftcol {
    float: left;
    width: 65%;
    text-align: right;
}
.rightcol {
    float: left;
    width: 35%;
    text-align: left;
}
a.headlink {
    color: #191919;
    font-family: "Fira Code";
    font-size: 9pt;
    text-decoration: none;
}
table.cv {
  width: 70%;
  margin-left: 15%;
}
table.cvHead {
  width: 70%;
  margin-left: 15%;
  border-bottom: solid 2px #990000;
  margin-bottom: 5em;
}
td.leftHead {
  width: 70%;
  text-align: right;
}
td.rightHead {
  width: 30%;
  text-align: right;
}
</style>

<table class="cvHead" style="margin-bottom: 4em;">
  <tr>
    <td colspan=2><h1 class="myname" style="border-bottom: 0px;">Jeremy Forest Price, PhD</h1></td>
  </tr>
  <tr>
    <td style="width: 65%; text-align: right; font-size: 9pt;">
      Department of Urban Teacher Education<br />
      IU School of Education-Indianapolis at IUPUI<br />
      902 West New York Street<br />
      Indianapolis, IN 46206
    </td>
    <td style="width: 35%; text-align: right; font-size: 9pt;>
      1.317.274.6808 <i class="fa fa-phone" style = "color: #990000;")></i><br />
      <a class="headlink" href="mailto:jfprice@iupui.edu">jfprice@iupui.edu</a> <i class="fa fa-envelope" style = "color: #990000;")></i><br />
      <a href="https://twitter.com/dr_jfprice">dr_jfprice</a> <i class="fa fa-twitter" style = "color: #990000;")></i><br />
      <a href="https://github.com/jeremyfprice">jfprice</a> <i class="fa fa-github-alt" style = "color: #990000;")></i>
    </td>
  </tr>
</table>

<table class="cv">
  <tr>
    <td width="15%"><h2 class="cv">education</h2></td>
    <td>
      <h3 class="top">Graduate</h3>
      {{< education level="graduate" >}}
      <h3 class="cv">Undergraduate</h3>
      {{% education level="undergraduate" %}}
  </tr>
</table>

<table class="cv">
<tr>
  <td width="15%"><h2 class="cv">appointments</h2></td>
  <td>
  <h3 class="top">Academic</h3>
  {{< appointments type="academic" >}}
  <h3 class="cv">Non-Academic</h3>
  {{% appointments type="non-academic" %}}
</td>
</tr>
</table>

<table class="cv">
<tr>
  <td width="15%"><h2 class="cv">awards and honors</h2></td>
  <td>
  {{% awards %}}
</td>
</tr>
</table>
