# XG-modell-Nevralt-Nettverk
Innhenting av eventdata fra StatSbomb sitt gratis dataset. Deretter filtrering, feature-bygging og trening av nevralt nettverk. Også implementert metrikker og plotting for verifisering av resultatene.

Selve expected goals modellen er et nevralt nettverk med tre skjulte lag, hvor hvert lag har 128 nevroner. Det nevrale nettverket henter inn 45 forskjellige inputs eller features, alt fra om skudde var en heading, x-posisjonen på skuddet, y-posisjonen på skuddet osv. I motsetning til andre modeller som kun tar inn hvor mange motstandere som er mellom skuddet og målet, velger jeg også å ta med avstanden fra spilleren som skyter til nærmeste motspiller i tillegg til medspillere som også er mellom skudd og mål.

Datasett og modell som er ferdig generert og trent, finnes i zip-filen. Det er mulig å endre på hvilke ligaer og år man vil ha skudd fra i config-filen og deretter trene modellen på dem. 
Man kan også endre relevante hyperparametre i config-filen f.eks. batch size, learning-rate osv. men hvis man ønsker å endre på arkitekturen til nettverket må man gå inn i model-filen. 
Hver gang man endrer config må man kjøre de relevante filene. Pass på at man har lastet ned bibliotekene man trenger før man kjører python-koden, bruk f.eks. pip install:
numpy, pandas, pickle, sklearn, torch, statsbomb, matplotlib, joblib

Kjør alle filene i samme mappe, hvis man endrer på ting i config: config -> hent_data -> preprossessering -> model -> xg_nevralt_nettverk
Bruk xg_nevralt_nettverk filen til å se hvor godt modellen gjør det, bruk xg_plot til å se hvordan modellen gjorde det for en gitt kamp, sammenliknet med statsbomb sin innebygde xg-modell.
