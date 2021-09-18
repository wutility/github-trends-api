# Github trends api  
Unofficial Github Trending API  

[![npm version](https://badge.fury.io/js/github-trends-api.svg)](https://badge.fury.io/js/github-trends-api)  ![](https://badgen.net/npm/dt/github-trends-api) ![](https://badgen.net/bundlephobia/min/github-trends-api)  

```
npm i github-trends-api
// or
yarn add github-trends-api
```

## Usage
```js
const githubTrends = require('github-trends-api')
// or
import githubTrends from 'github-trends-api';
```

## Methods
```js
const options = {
  section?: '', // default: empty (repositories) - or 'developers'
  language?: '' // default: empty (all) - or 'javascript', 'java' etc..
  since?: '' // default: empty (daily) - or 'weekly', 'monthly'
  spoken_language_code?: '' // default: empty (all) - or en - fs - zh ...
}

githubTrends(options: Object): Promise
```

## Examples

### Repositories
```js
githubTrends()
  .then(result => { console.log(result) })
  .catch(error => { console.log(error) })
```
- **Response**
```json
[
  {
    "author": "CSSEGISandData",
    "reponame": "COVID-19",
    "repourl": "https://github.com//CSSEGISandData/COVID-19",
    "repodesc": "Novel Coronavirus (COVID-19) Cases, provided by JHU CSSE",
    "language": "",
    "langcolor": "",
    "stars": 3,
    "forks": 303,
    "laststars": 1,
    "builtby": [
      {
        "username": "CSSEGISandData",
        "url": "https://github.com/CSSEGISandData",
        "avatar": "https://avatars3.githubusercontent.com/u/60674295?s=40&v=4"
      }
    ]
  }
]
```

### Developers
```js
githubTrends({ section: 'developers', since: 'weekly' })
  .then(result => { console.log(result) })
  .catch(error => { console.log(error) })
```
- **Response**
```json
[
  {
    "author": "James Montemagno",
    "username": "jamesmontemagno",
    "avatar": "https://avatars3.githubusercontent.com/u/1676321?s=96&v=4",
    "url": "https://github.com/jamesmontemagno",
    "reponame": "Xamarin.Plugins",
    "repourl": "https://github.com/jamesmontemagno/Xamarin.Plugins",
    "description": "Cross platform xamarin and windows plugins for PCLs"
  }
..]
```

## Tests 
```
https://npm.runkit.com/github-trends-api
```

## License
MIT
