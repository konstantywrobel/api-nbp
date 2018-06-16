# Api JSON - Narodowy Bank Polski

```
const app = document.getElementById('root');
const container = document.createElement('div');
container.setAttribute('class', 'container');
app.appendChild(container);

fetch('http://api.nbp.pl/api/exchangerates/tables/a/last/1?format=json')
    .then(resp => resp.json())
    .then(resp => {
        console.log(resp);
        resp[0].rates.forEach(rates => {


            const card = document.createElement('div');
            card.setAttribute('class', 'card');
            const h1 = document.createElement('h1');
            h1.textContent = rates.currency;
            const p = document.createElement('p');
            p.textContent = rates.mid;
            container.appendChild(card);
            card.appendChild(h1);
            card.appendChild(p);
        })
    })
.catch(error => console.log('Błąd: ', error) + alert('Błąd podczas pobierania danych'));


```

## Example

[demo](https://konstnatyw.pl/api-nbp)
