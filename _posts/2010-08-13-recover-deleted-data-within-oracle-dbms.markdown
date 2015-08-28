---
layout: post
title: Recover deleted data within Oracle DBMS
tags:
- oracle
---


Puh! From now on, I'll love the oracle DBMS for their flashback function. :)


How it works...


Oracle is able to (if undo-log is enabled) let you do selects on specific timestamps. So if you know, oh damn i deleted data on 1pm an you are on 2pm it is possible to restore those data.


To get those data from the history do something like:


{% highlight sql %}
    SELECT * FROM blablub AS OF TIMESTAMP
      TO_TIMESTAMP('2010-08-13 12:40:00', 'YYYY-MM-DD HH:MI:SS')
      WHERE bla_id = 12345;
{% endhighlight %}

And this is the way to restore the requested data:

{% highlight sql %}
    INSERT INTO blablub (
        SELECT * FROM blablub AS OF TIMESTAMP
	  TO_TIMESTAMP('2010-08-13 12:40:00', 'YYYY-MM-DD HH:MI:SS')
	  WHERE bla_id = 12345
	);
{% endhighlight %}

Have fun with your restored data and a nice weekend!


Tony


PS.: here is my source <a href="http://www.comp.dit.ie/btierney/oracle11gdoc/appdev.111/b28424/adfns_flashback.htm#i1008579">http://www.comp.dit.ie/btierney/oracle11gdoc/appdev.111/b28424/adfns_flashback.htm#i1008579</a>


