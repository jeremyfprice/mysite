---
title: "CV"
date: 2021-04-29
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
    font-size: 1.5em;
    font-family: Rubik;
    font-weight: 500;
    text-align: left;
}
h3.cv {
    font-size: 1.2em;
    font-family: Spectral;
    font-style: italic;
    font-weight: 400;
    padding: 0;
    margin: 1em 0 0;
}
h3.top {
    font-size: 1.2em;
    font-family: Spectral;
    font-style: italic;
    font-weight: 400;
    padding: 0;
    margin: 0;
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
    font-size: 3em;
    text-align: left;
    font-weight: 500;
    margin: 0;
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
</style>

<div style="width: 100%; padding-bottom: 180px;">
<h1 class="myname">Jeremy Forest Price, PhD</h1>
<div class="leftcol">
Department of Urban Teacher Education<br />
IU School of Education-Indianapolis at IUPUI<br />
902 West New York Street<br />
Indianapolis, IN 46206
</div>
<div class="rightcol">
1.317.274.6808 <i class="fa fa-phone" style = "color: #990000;")></i><br />
<a class="headlink" href="mailto:jfprice@iupui.edu">jfprice@iupui.edu</a> <i class="fa fa-envelope" style = "color: #990000;")></i><br />
<a href="https://twitter.com/dr_jfprice">dr_jfprice</a> <i class="fa fa-twitter" style = "color: #990000;")></i><br />
<a href="https://github.com/jeremyfprice">jfprice</a> <i class="fa fa-github-alt" style = "color: #990000;")></i>
</div>
</div>

<div class="content">
<div class="leftcol">
<h2 class="cv">education</h2>
</div>
<div class="rightcol">
<h3 class="top">Graduate</h3>
{% for item in education | selectattr('level', '==', 'graduate') | sort(attribute = 'year', reverse = True) %}
<div class="item">
{{ item.degree }}, {{ item.institution }}, {{ item.year }}
</div>
{% endfor %}

<h3 class="cv">Undergraduate</h3>
{% for item in education | selectattr('level', '==', 'undergraduate') | sort(attribute = 'year', reverse = True) %}
<div class="item">
{{ item.degree }}, {{ item.institution }}, {{ item.year }}
</div>
{% endfor %}
</div>
</div>

<div class="content">
<div class="leftcol">
<h2>appointments</h2>
</div>
<div class="rightcol">
<h3 class="top">Academic</h3>

{{ $appointments := site.Data.appointments }}
{{ range $appointments }}
  {{ if eq .type "academic" }}
<p>{{ .institutions }}</p>
  {{ end }}
{{ end }}



{% for item in appointments | selectattr('type', '==', 'academic') | sort(attribute = 'end_year', reverse = True) %}
<div class="item">
{{ item.position }}, {{ item.institution }}, {{ item.start_year }}{%- if item.start_year != item.end_year -%}&nbsp;- {{ item.end_year }}{%- endif -%}
</div>
{% endfor %}

<h3>Non-Academic</h3>
{% for item in appointments | selectattr('type', '==', 'non-academic') | sort(attribute = 'end_year', reverse = True) %}
<div class="item">
{{ item.position }}, {{ item.institution }}, {{ item.start_year }}{%- if item.start_year != item.end_year -%}&nbsp;- {{ item.end_year }}{%- endif -%}
</div>
{% endfor %}
</div>
</div>

    <div class="content">
        <div class="leftcol">
        <h2>awards and honors</h2>
        </div>
        <div class="rightcol">
            {% for item in awards | sort(attribute = 'title') | sort(attribute = 'start_year', reverse = True) | sort(attribute = 'end_year', reverse = True) %}
            <div class="item">
                {{ item.title }}, {{ item.institution }}, {{ item.start_year }}{%- if item.start_year != item.end_year -%}&nbsp;- {{ item.end_year }}{%- endif -%}
            </div>
            {% endfor %}
        </div>
    </div>

    <div class="content">
        <div class="leftcol">
        <h2>grants</h2>
        </div>
        <div class="rightcol">
            {% for item in grants | sort(attribute = 'title') | sort(attribute = 'start_year', reverse = True) | sort(attribute = 'end_year', reverse = True) %}
            <div class="item">
                {{ item.institution }}, "{{ item.title }}," {{ item.role }},
                ${{- '{:,}'.format(item.amount) -}}, {{ item.start_year }}{%- if item.start_year != item.end_year -%}&nbsp;- {{ item.end_year }}{%- endif -%}
            </div>
            {% endfor %}
        </div>
    </div>

    <div class="content">
        <div class="leftcol">
        <h2>publications</h2>
        </div>
        <div class="rightcol">
            <h3 class="top">Book Chapters</h3>
            {% for item in bookchapters | sort(attribute = 'title') | sort(attribute = 'year', reverse = True) %}
            <div class="item">
                {%- if item.preauthor %}{{ item.preauthor }} {% endif %} <b>Price, J. F.</b>{%- if item.postauthor -%}, {{ item.postauthor }}{%- endif %} ({{ item.year }}). {{ item.title }}. In {% if item.editor -%}{{ item.editor }}, {% endif -%}<i>{{ item.booktitle }}</i>{%- if item.pages %} (pp. {{ item. pages }}){%- endif -%}. {{ item.publisher }}.
            </div>
            {% endfor %}

            <h3>Journal Articles</h3>
            {% for item in appointments | selectattr('type', '==', 'non-academic') | sort(attribute = 'end_year', reverse = True) %}
            <div class="item">
                {{ item.position }}, {{ item.institution }}, {{ item.start_year }}{%- if item.start_year != item.end_year -%}&nbsp;- {{ item.end_year }}{%- endif -%}
            </div>
            {% endfor %}

            <h3>White Papers and Policy Documents</h3>
            {% for item in appointments | selectattr('type', '==', 'non-academic') | sort(attribute = 'end_year', reverse = True) %}
            <div class="item">
                {{ item.position }}, {{ item.institution }}, {{ item.start_year }}{%- if item.start_year != item.end_year -%}&nbsp;- {{ item.end_year }}{%- endif -%}
            </div>
            {% endfor %}

            <h3>Op-Eds</h3>
            {% for item in appointments | selectattr('type', '==', 'non-academic') | sort(attribute = 'end_year', reverse = True) %}
            <div class="item">
                {{ item.position }}, {{ item.institution }}, {{ item.start_year }}{%- if item.start_year != item.end_year -%}&nbsp;- {{ item.end_year }}{%- endif -%}
            </div>
            {% endfor %}

            <h3>Digital Media</h3>
            {% for item in appointments | selectattr('type', '==', 'non-academic') | sort(attribute = 'end_year', reverse = True) %}
            <div class="item">
                {{ item.position }}, {{ item.institution }}, {{ item.start_year }}{%- if item.start_year != item.end_year -%}&nbsp;- {{ item.end_year }}{%- endif -%}
            </div>
            {% endfor %}
        </div>
    </div>

    <div class="content">
        <div class="leftcol">
        <h2>refereed presentations</h2>
        </div>
        <div class="rightcol">
            {% for item in grants | sort(attribute = 'title') | sort(attribute = 'start_year', reverse = True) | sort(attribute = 'end_year', reverse = True) %}
            <div class="item">
                {{ item.institution }}, "{{ item.title }}," {{ item.role }},
                ${{- '{:,}'.format(item.amount) -}}, {{ item.start_year }}{%- if item.start_year != item.end_year -%}&nbsp;- {{ item.end_year }}{%- endif -%}
            </div>
            {% endfor %}
        </div>
    </div>

    <div class="content">
        <div class="leftcol">
        <h2>select invited presentations</h2>
        </div>
        <div class="rightcol">
            {% for item in grants | sort(attribute = 'title') | sort(attribute = 'start_year', reverse = True) | sort(attribute = 'end_year', reverse = True) %}
            <div class="item">
                {{ item.institution }}, "{{ item.title }}," {{ item.role }},
                ${{- '{:,}'.format(item.amount) -}}, {{ item.start_year }}{%- if item.start_year != item.end_year -%}&nbsp;- {{ item.end_year }}{%- endif -%}
            </div>
            {% endfor %}
        </div>
    </div>

    <div class="content">
        <div class="leftcol">
        <h2>leadership and service</h2>
        </div>
        <div class="rightcol">
            <h3 class="top">Book Chapters</h3>
            {% for item in appointments | selectattr('type', '==', 'academic') | sort(attribute = 'end_year', reverse = True) %}
            <div class="item">
                {{ item.position }}, {{ item.institution }}, {{ item.start_year }}{%- if item.start_year != item.end_year -%}&nbsp;- {{ item.end_year }}{%- endif -%}
            </div>
            {% endfor %}

            <h3>Journal Articles</h3>
            {% for item in appointments | selectattr('type', '==', 'non-academic') | sort(attribute = 'end_year', reverse = True) %}
            <div class="item">
                {{ item.position }}, {{ item.institution }}, {{ item.start_year }}{%- if item.start_year != item.end_year -%}&nbsp;- {{ item.end_year }}{%- endif -%}
            </div>
            {% endfor %}

            <h3>White Papers and Policy Documents</h3>
            {% for item in appointments | selectattr('type', '==', 'non-academic') | sort(attribute = 'end_year', reverse = True) %}
            <div class="item">
                {{ item.position }}, {{ item.institution }}, {{ item.start_year }}{%- if item.start_year != item.end_year -%}&nbsp;- {{ item.end_year }}{%- endif -%}
            </div>
            {% endfor %}

            <h3>Op-Eds</h3>
            {% for item in appointments | selectattr('type', '==', 'non-academic') | sort(attribute = 'end_year', reverse = True) %}
            <div class="item">
                {{ item.position }}, {{ item.institution }}, {{ item.start_year }}{%- if item.start_year != item.end_year -%}&nbsp;- {{ item.end_year }}{%- endif -%}
            </div>
            {% endfor %}

            <h3>Digital Media</h3>
            {% for item in appointments | selectattr('type', '==', 'non-academic') | sort(attribute = 'end_year', reverse = True) %}
            <div class="item">
                {{ item.position }}, {{ item.institution }}, {{ item.start_year }}{%- if item.start_year != item.end_year -%}&nbsp;- {{ item.end_year }}{%- endif -%}
            </div>
            {% endfor %}
        </div>
    </div>

   <div class="content">
        <div class="leftcol">
        <h2>media coverage</h2>
        </div>
        <div class="rightcol">
            {% for item in grants | sort(attribute = 'title') | sort(attribute = 'start_year', reverse = True) | sort(attribute = 'end_year', reverse = True) %}
            <div class="item">
                {{ item.institution }}, "{{ item.title }}," {{ item.role }},
                ${{- '{:,}'.format(item.amount) -}}, {{ item.start_year }}{%- if item.start_year != item.end_year -%}&nbsp;- {{ item.end_year }}{%- endif -%}
            </div>
            {% endfor %}
        </div>
    </div>
