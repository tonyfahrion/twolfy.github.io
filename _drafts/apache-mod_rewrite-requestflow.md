---
layout: post
title: Apache httpd requestflow | In welcher Reihenfolge die Optionen in Verbindung
  mit mod_rewrite wirken
tags:
  - webserver
---
Der Apache-Webserver ( httpd ) ist einer der leistungsfähigsten und mächtigsten Webservern, die ich kenne. Bisher habe ich es nicht geschaft, eine Anforderung mit ihm nicht abdecken zu können. Die hauseigene Dokumentation ist äußerst vorbildlich und lässt in vielen Fällen keine Fragen offen.


Jedoch gibt es immer wieder sehr spezielle Anforderungen, in denen die Dokumentation - verständlicher Weise - Fragen offen lässt. So wie die Frage: "In welcher Reihenfolge werden die Konfigurationsoptionen, in Verbindung mit mod_rewrite bei einem Request abgearbeitet?"


Genau diese Frage möchte ich Ihnen in diesem Artikel beantworten.


# vorhandene Informationen im Netz


<blockquote>
In welcher Reihenfolge Sektionen abgearbeitet werden: <a href="http://httpd.apache.org/docs/2.2/sections.html#mergin">http://httpd.apache.org/docs/2.2/sections.html#mergin</a>


</blockquote>
In dem oberhalb referenzierten Artikel werden Sie Informationen dazu finden, in welcher Reihenfolge der Apache die einzelnen Sektionen (&lt;Directory&gt;,&lt;Files&gt;,&lt;Location&gt;) bei einem Request durchgehen wird. Mit diesen Informationen können Sie sich bereits einige Standardfragen beantworten. Trickreich wird es erst, wenn Sie mod_rewrite verwenden.


# Sektionsreihenfolge in eigenen Worten


Wir befinden uns im vHost-Kontext befinden. Nun haben wir folgendes Konstrukt:


<blockquote>
  &lt;Directory /srv/www/htdocs/&gt;


    php_admin_flag engine on


  &lt;/Directory&gt;


  &lt;Location /&gt;


    php_admin_flag engine on


  &lt;/Location&gt;


  &lt;Files \.(php)$&gt;


    php_admin_flag engine off


  &lt;/Files&gt;


</blockquote>
# Nun fügen wir mod_rewrite hinzu


