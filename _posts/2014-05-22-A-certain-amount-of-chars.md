---
layout: post
title: Display n characters by line (for svg)
---


I needed to write down some legends on a graph. My client wanted to be able to choose the number of characters by line.


```javascript
	var maxChar = 30; //the number of chars by line you want
	var words = new Array();
                  
              if(OriginalString.length>maxChar)
              {
                OriginalString.split(" ");
                var nbLine = 0;
                words[nbLine]="";
                for(var i = 0; i < OriginalString.split(' ').length;i++)
                {
                  if(words[nbLine].length + OriginalString.split(' ')[i].length <= maxChar)
                  {
                    words[nbLine] += OriginalString.split(' ')[i];
                    words[nbLine] += " ";
                  }
                  else
                  {
                    nbLine ++;
                    words[nbLine] = OriginalString.split(' ')[i];
                  }
                }
                
              }
              else
              {
                d.words[0] = d.OriginalString
              }

```