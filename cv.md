# Darya Karpovich
---
**City:** Minsk, Belarus 
**Age:** 30 y.o. 

> **Phone**: +375 (44) 713-16-21 | **Mail**: dashka230@yamdex.ru | **Skype**: malina.malinina20

## About me
---
Strengths: 
  - I learn quickly;
  - organization;
  - ability to work in a team.

Weaknesses: Lack of experience.

## English Language
---
**Level english:** A1 + (Basic Medium)

_Now I'm taking English courses to improve my level_

## Education
---
#### 2012-2015

**Minsk Higher Radio Engineering College**, professional education** (hight education);

_Minsk, Belarus_
        
#### 2008-2012 

**Minsk Higher Radio Engineering College**, information technology software** (secondary special education);

_Minsk, Belarus_

## Expirience
---
- 2017-2021 - **Biglion Company**: **content manager** (remote), Moscow, Russia;
- 2015-2021 - **Minsk Radio Engineering College**: **programming teacher**, Minsk, Belarus.

## Technical Experience
---
- HTML, CSS;
- JavaScript;
- Data Base (MySQL, MSSQL);
- PHP (basic lavel);
- Git;
- NPM.

> **Example code**

```sh

export default class PokemonClient {
  constructor(intialUrl) {
    this.intialUrl = intialUrl;
  }

  async getList(isNext = true) {
    this.isAlreadySorted = false;
    const link = isNext ? this.next : this.back;
    const response = await fetch(link || this.intialUrl);
    const data = await response.json();
    this.pokeData = data.results;

    this.next = data.next;
    this.back = data.previous;

    this.mas = data.results.map((k) => k.name);
    return this.mas;
  }

  getDetails(name) {
    const findItem = this.pokeData.find((item) => item.name === name);
    return fetch(findItem.url)
      .then((response) => response.json())
      .then((pokemon) => {
        this.idPokemon = pokemon.id;
        return pokemon;
      });
  }

  loadComments(comments) {
    const commentsPokemon = [];

    comments.forEach((item) => {
      if (this.idPokemon === item.idPokemons) commentsPokemon.push(item);
    });
    return commentsPokemon;
  }

  sort() {
    if (this.isAlreadySorted) {
      this.mas.reverse();
    } else {
      this.mas.sort();
      this.isAlreadySorted = true;
    }
    return this.mas;
  }

  search(inputValue) {
    const resultsSearch = this.mas.filter((i) => i.includes(inputValue));
    return resultsSearch;
  }
}
```
### Studying React
> **Example code**

```sh

class App extends React.Component {
  constructor() {
    super();
    this.state = {selected: 0};
  }
  
  handleChange = (e) => {
    this.setState({ selected: e.target.value });
  }

  render() {
    const index = this.state.selected;
    return (
      <div>
        <div class="App">
          <h3>React Simple Wether App</h3>
          <div class="form-group">
            <label for="citySelect">City Select</label><br></br>
            <select class="col-md-5" id="citySelect" value={this.state.selected} onChange={this.handleChange}>
            {places.map((place,index) => (
              <option value={index}> {place.name} </option>     
            ))}
            </select>
          </div>
        </div>
        <br></br>
        <div class="container">
          <div class="row">
            <div class="col-md-8">
              <div class="App">
                <WeatherDisplay key={index} zip={places[index].zip} />
              </div>
            </div>
            <div class="col-md-4">
                  <WeatherDisplayMini zip={places[13].zip} />
                  <WeatherDisplayMini zip={places[0].zip} />
                  <WeatherDisplayMini zip={places[4].zip} />
                  <WeatherDisplayMini zip={places[8].zip} />
                  <WeatherDisplayMini zip={places[11].zip} />
                  <WeatherDisplayMini zip={places[19].zip} />
            </div>
          </div>
        </div>
      </div>
    );
  }
}

export default App;

```


