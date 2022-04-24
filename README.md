# hugo-ligth-cite
Use citation in your hugo website in the simplest way. RegEx to replace the &lt;sup> element to [1]


## regEx
Regular expression is used to replace the <sup> element that would otherwise be generated from markdown.

In the single.html template file replace {{ .Content }} with:
  
```
{{ .Content | replaceRE "<sup(.*?\"doc-noteref\">)(.*?)</a>.*?</sup>" "<span$1[$2]</a></span>" | safeHTML }}
```

## Citing references
In your markwon files you can cite in the following way:
```
Facendo una semplice elaborazione dei dati ho quantificato e categorizzato le antenne sul territorio svizzero. Premettendo che la data di aggiornamento dei dati varia tra 2018 e 2019 e che probabilmente i dati presenti sulla cartina interattiva sono più recenti dei dati forniti in formato _.json_, in Svizzera abbiamo 34'264 antenne totali di cui, 6'801 antenne 5G <cite>[^2]</cite>, 12'415 antenne 4G <cite>[^3]</cite>, 11'936 antenne 3G <cite>[^4]</cite> e 2'112 antenne 2G <cite>[^5]</cite>.

[^2]: https://data.geo.admin.ch/ch.bakom.mobil-antennenstandorte-5g/
[^3]: https://data.geo.admin.ch/ch.bakom.mobil-antennenstandorte-lte/
[^4]: https://data.geo.admin.ch/ch.bakom.mobil-antennenstandorte-gsm/
[^5]: https://data.geo.admin.ch/ch.bakom.mobil-antennenstandorte-umts/
```
