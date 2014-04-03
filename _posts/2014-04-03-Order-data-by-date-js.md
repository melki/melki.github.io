---
layout: post
title: Sort data by date in d3.js
---

How to sort data by date ?
==========================

I wanted to order data from a csv by date, and I didn't found a built-in function in d3.
So after importing the data from the csv (or json as you want), here is what you do :

```javascript
d3.csv('yourData.csv', function (error,data) {
	
    data.forEach(function (d) {
	
		d.Date = new Date(d["date"]);
		//I have a date column in my csv;
	    d.DateNumber = d.Date.getDate();
	    //I wanted to order them by day, but it's possible with month and year as well :
	     d.Date.getFullYear()+''+d.Date.getMonth() + '' +  d.Date.getDate() + '';
	    d.DateNumber = parseInt(d.DateNumber);
	});
	
	data.sort(function(a, b){
 		return a.DateNumber - b.DateNumber //order them by the number and that's done !
	});

});

```