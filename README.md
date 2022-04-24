# hugo-easy-cite
Use citation in your hugo website in the easiest way possible while achiving a good result. 


## Introduction
The markdown formatter would use by defualt the \<sup> HTML element for citations. 

We will achive a better result replacing the \<sup> element with regular exppression to create a citation with this simbol: ```[1]```


## regular expression
Regular expression is used to replace the \<sup> element that would otherwise be generated from markdown.

In the single.html template file replace ```{{ .Content }}``` with:
  
```
{{ .Content | replaceRE "<sup(.*?\"doc-noteref\">)(.*?)</a>.*?</sup>" "<span$1[$2]</a></span>" | safeHTML }}
```

## Citing references
In your markwon files you can cite in the following way:
```
L’istituto di farmacologia e tossicologia dell’università di Zurigo ha dimostrato nel 2007 che determinati effetti negativi sulla fisiologia cerebrale sono dipendenti dalla dose di radiazioni elettromagnetiche a cui si è esposti [1].

[^1]: Regel SJ, Tinguely G, Schuderer J, Adam M, Kuster N, Landolt HP, Achermann P. Pulsed radio-frequency electromagnetic fields: dose-dependent effects on sleep, the sleep EEG and cognitive performance. J Sleep Res. 2007 Sep;16(3):253-8. doi: 10.1111/j.1365-2869.2007.00603.x. PMID: 17716273 [link](/doc/sleep.pdf).
```

Your document will have a clickable reference as follows:

![image](https://user-images.githubusercontent.com/96437099/164985905-a9c608ea-a3d4-46e6-9c06-8ee1046045d7.png)

At the bottom of the page you will se the list of cited references:
![image](https://user-images.githubusercontent.com/96437099/164985959-5f4e8216-17a1-4279-b3d2-66370964d0c0.png)

You can see the compleate implementation [here](https://impavidus.ch/2007-Zurich-human-sleep/).
