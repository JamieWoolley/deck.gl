# @deck.gl/carto

Deck.gl is the prefered and official solution to create modern Location Intelligence Webapps with [CARTO platform](https://carto.com/)

<img src="https://raw.githubusercontent.com/CartoDB/viz-doc/master/deck.gl/img/osm_buildings.jpg" />


It integrates with [CARTO Maps API](https://carto.com/developers/maps-api/reference/) to:

* Provide a geospatial backend storage for your geospatial data.
* Visualize large datasets which don't fit in browser memory.
* SQL spatial interface to work with your data.


## Install package

```bash
npm install deck.gl
# or
npm install @deck.gl/core @deck.gl/layers @deck.gl/carto
```

## Usage

```js
import DeckGL from '@deck.gl/react';
import {CartoSQLLayer, setDefaultCredentials} from '@deck.gl/carto';

setDefaultCredentials({
  username: 'public',
  apiKey: 'default_public'
});

function App({viewState}) {
  const layer = new CartoSQLLayer({
    data: 'SELECT * FROM world_population_2015',
    pointRadiusMinPixels: 2,
    getLineColor: [0, 0, 0, 0.75],
    getFillColor: [238, 77, 90],
    lineWidthMinPixels: 1
  })

  return <DeckGL viewState={viewState} layers={[layer]} />;
}
```

### Examples

You can see real examples at:

* [Scripting](https://github.com/CartoDB/viz-doc/tree/master/deck.gl/examples/scripting): Quick scripting examples to play with the module without NPM or Webpack. If you're not a web developer this is probably what you're looking for.

* [React](https://github.com/CartoDB/viz-doc/tree/master/deck.gl/examples/react): integrate in a React application.

* [Pure JS](https://github.com/CartoDB/viz-doc/tree/master/deck.gl/examples/pure-js): integrate in a pure js application using webpack.
