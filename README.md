# C-TIP widget Marrekrite

C-TIP is het platform voor het centraal beheer van zowel uw toeristisch aanbod als recreatieve routes uit uw regio. Met deze widget is het mogelijk om data uit C-TIP op uw eigen site te tonen. 

## Vereisten

Deze widget vereist het gebruik van C-TIP en de bijbehorende proxy. 

## Installatie

### Download

U kunt de laatste versie van de widget krijgen op deze github onder [releases]

## Voorbeelden

### Javascript

```js
				$( "#ctip-widget" ).ctipWidget( {
				    mapSelector: "#map",
				    layersSelector: "#layers",
				    proxyUrl: "http://proxy.ctip.rapide.software",
				    layers: [
				        {
				            name: "FKP Friesland",
				            url: "/friesland/fietsen"
				        }, 
				        {
				            name: "Marrekrite Steigers",
				            url: "/friesland/plus"
				        }
				    ],
				    layerTemplateSelector: "#layer-template", 
				    vectorStyleUrl: "http://91.208.60.51:8080/styles/marrekrite/style.json",
				    center: {
				        lat: 53.112003,
				        lng: 5.8169843,
				        zoom: 11
				    }
				});

```
### CSS

```css
			body, html {
			    height:100%;
			    margin: 0;
			    padding:0;
			}
			#ctip-widget {
			    height:100%;
			    font-family: arial, serif;
			    font-size:14px;
			}
			#ctip-widget #map {
			    height: 100%;
			    width:80%;
			    float:left;
			}
			#ctip-widget #map .ctip-icon {
			    width:16px;
			    height:16px;
			    background-color:red;
			    border-radius:100px;
			}
			#ctip-widget #map .ctip-line {
			    stroke: green;
			    fill: none;
			    stroke-dasharray: 10,10;
			    stroke-width: 5;
			}
			#ctip-widget #layers {
			    width: calc(20% - 40px);
			    height:100%;
			    float:left;
			    padding:20px;
			}
			#ctip-widget .leaflet-center {
			    width: 40%;
			    margin-left: auto;
			    margin-right: auto;
			    position: relative;
			}
			#ctip-widget .leaflet-container .leaflet-control-geosearch input {
			    width: 100%;
			    height: 28px;
			    padding: 0;
			    text-indent: 8px;
			    background: rgba(255, 255, 255, 0.75);			
			    border-radius: 4px;
			    border: none;
			}
```

## Opties

Bij het starten van de widget kunnen er een aantal opties worden meegegeven. Deze worden hieronder beschreven.

### mapSelector
Jquery selector voor het kaart-element. Deze selector is verplicht. Dit mag  alleen een id(#) zijn, geen class.

```js
    mapSelector: "#map",
```

### layersSelector
Jquery selector voor de kaartlaag-elementen. Deze selector is verplicht. Dit mag  alleen een id(#) zijn, geen class.

```js
      layersSelector: "#layers",
```

### layerTemplateSelector
Jquery selector voor het legenda-element. Deze selector is verplicht. Dit mag  alleen een id(#) zijn, geen class.

```js
    layerTemplateSelector: "#layer-template", 
```

### center
De kaart begint op een vaste locatie. Met de center-optie is deze locatie aan te passen. 

```js
    center: {
        lat: 53.112003,
        lng: 5.8169843,
        zoom: 11
    }
```

### vectorStyleUrl
De URL waar de tegels van de kaart van ingeladen moeten worden. De widget maakt gebruik van vector tiles en is op dit moment niet te gebruiken met PNG-tiles. 

```js
    vectorStyleUrl: "http://91.208.60.51:8080/styles/marrekrite/style.json",
```

### proxyUrl
De basis URL waar de data vandaan gehaald moet worden. 

```js
    proxyUrl: "http://proxy.ctip.rapide.software"
```

### layers
De lagen die geladen moeten worden. Per laag moet de naam van de laag en de extensie van de URL waar de data vandaan gehaald moet worden aangegeven.  

```js
    layers: [
        {
            name: "FKP Friesland",
            url: "/friesland/fietsen"
        }, 
        {
            name: "Marrekrite Steigers",
            url: "/friesland/plus"
        }
    ]
```



## Opdracht
Deze widget is in opdracht van Folkermsa Route & Sign uitgevoerd door RAPIDE Internet.

![Folkersma][folkersma]

[repo]: https://github.com/rapideinternet/ctip.widget.friesland
[ctip]: https://c-tip.com
[releases]: https://github.com/rapideinternet/ctip.widget.friesland/releases
[folkersma]: http://folkersma.nl/assets/img/folkersma-logo.svg
[ctip]: https://c-tip.com/assets/img/landing/ctip-logo-big-registred.svg
