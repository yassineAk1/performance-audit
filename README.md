# Performance Audit 

Doe een Performance audit op een bestaande website uit je eigen omgeving en rapporteer daarover.

De instructies van deze opdracht staan in [INSTRUCTIONS](https://github.com/fdnd-task/performance-audit/blob/main/docs/INSTRUCTIONS.md).


## Performance Snappthis

De app is getest met **Lighthouse**, **PageSpeed Insights** en **WebPageTest**. De volledige analyse staat in de [Performance Audit wiki](https://github.com/yassineAk1/user-experience-enhanced-website/wiki/performance-audit-snappthis).
<img width="863" height="575" alt="image" src="https://github.com/user-attachments/assets/cfa0e794-1ab1-4471-a29f-2521a115b487" />

- **Score:** de site haalt een prestatiescore van **99** met sterke Core Web Vitals (FCP 0,8 s, LCP 0,8 s, TBT 0 ms, CLS 0,043).
- **Valse meldingen:** veel waarschuwingen in de browsertest (Minify/Reduce unused JavaScript) kwamen van `chrome-extension://`-bestanden, dus van browser-extensies en niet van de site zelf. In een incognito-test verdwenen die.
- **Echte aandachtspunten:**
  - `/assets/placeholder.jpeg` is bijna 2,9 MB en veroorzaakt vrijwel de hele netwerkpayload (~3 MB). Oplossing: comprimeren, verkleinen en als WebP aanbieden.
  - `/assets/camera-alt.svg` mist `width` en `height`, wat kleine layout shifts geeft (CLS). Oplossing: afmetingen meegeven.
- **WebPageTest waterfall:** trage serverreactie op het hoofddocument (505 ms), render-blokkerende CSS/JS, de grote afbeelding als langste verzoek (663 ms), veel externe verzoeken naar `directus.app`, en een overbodig bestand dat een 404-fout geeft.
## Licentie

This project is licensed under the terms of the [MIT license](./LICENSE).
