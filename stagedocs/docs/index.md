# algemeen

## probleem
<p>Machine learning modellen bouwen, trainen en gebruiken.
De data moet bruikbaar zijn op een simpele computer met mogelijk slecht internet. Er moet dus gezocht worden naar een manier om oftewel machine learning te doen in een browser oftewel op een server en de nodige data zo efficiënt mogelijk over te zetten.</p>

## flowchart

``` mermaid


graph TD
    A(Machine learning)
        A --> AB(Op PC)
            AB --> ABB(Executable)
                ABB -.-> ABBB[Alles moet op gebruikers PC kunnen gebeuren]
                ABB -.-> ABBC[Niet de directie waar we nu op gaan]
            AB --> ABC(In browser)
                ABC --> ABCB(ML.js #)
                    click ABCB "https://github.com/mljs/ml" "https://github.com/mljs/ml"
                    ABCB -.- ABCBA>Library waarmee modellen getraint en gebruikt kunnen worden in JavaScript.]
                        ABCBA -.-> ABCBAB[Makkelijk bruikbaar]
                        ABCBA -.-> ABCBAC[Ik ben al geslaagd er lineaire regressie mee te doen]
                        ABCBA -.-> ABCBAD[Geen gradient Boosting, hiervoor zal waarschijnlijk een andere library nodig zijn.]
                ABC --> ABCC(WASM)
                    ABCC -.- ABBCA>Webassembly <br> staat toe om o.a. Python te compileren en runnen in de browser]
                    ABCC --> ABCCB(Pyodide #)
                        click ABCCB "https://pyodide.org" "https://pyodide.org"
                        ABCCB -.- ABCCBA>Staat toe om python code te runnen in een JavaScript script]
                            ABCCBA -.-> ABCCBAB[Ik heb er al lineaire regressie mee kunnen doen<br>Bleek simpeler dan verwacht]
        A --> AC(Op server)
            AC --> ACB(REST API)
                ACB --> ACBB(enkel data)
                    ACBB -.- ACBBA>Gebruiker stuurt gewenste acties door<br>server voert uit en stuurt enkel data terug]
                        ACBBA -.-> ACBBAB[We willen ook de data kunnen zien per tussenstap<br>er zal dus veel data moeten worden verstuurd<br>probleem voor traag internet]
                    ACBB --> ACBBB(volledige Python backend)
                        ACBBB -.- ACBBBA>Maak volledige simulation backend en API in python]
                        ACBBB --> ACBBBB(flask #)
                            click ACBBBB "https://en.wikipedia.org/wiki/Flask_(web_framework)" "https://en.wikipedia.org/wiki/Flask_(web_framework)"
                            ACBBBB -.-> ACBBBBA[Snel en makkelijk op te zetten en gebruiken]
                    ACBB --> ACBBC(gedeeltelijke Python backend)
                        ACBBC -.- ACBBCA>Java/... backend <br>gebruikt Python enkel voor acties met modellen]
                ACB --> ACBC(ONNX #)
                    click ACBC "https://onnx.ai" "https://onnx.ai"
                    ACBC -.- ACBCA>ONNX staat toe een model in bv Python te bouwen en trainen <br> en het vervolgens als ONNX file door te sturen <br> wat door JavaScript kan gebruikt worden.]
                        ACBCA -.-> ACBCAB[Ik ben er al in geslaagd modellen in python te maken <br>Deze naar ONNX files om te zetten<br>en ze te gebruiken met JavaScript]
                        ACBCA -.-> ACBCAC[Ik ben een probleem tegengekomen met files die ik van het internet nam <br>Ik vond niet direct een oplossing en het maakt het model onbruikbaar<br>dus hopelijk komen we dit probleem niet tegen met onze eigen modellen.]
```
<p>Flowchart laat mogelijk niet toe om in te zoomen</p>

[Download meer gebruiksvindelijke flowchart](downloadables/mogelijkheden_flowchart_zoom.svg){:download="flowchart_machine_learning"}
