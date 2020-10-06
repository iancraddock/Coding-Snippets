# JavaScript Snippets

#### API Snippets

##### XMLHttpRequest

```javascript
let request = new XMLHttpRequest();

request.open('GET', 'https://jsonplaceholder.typicode.com/users');
request.send();
request.onload = () => {
	console.log(request);
	if(request.status === 200) {
		console.log(JSON.parse(request.response));
	} else {
		console.log('error ${request.status} ${request.statusText}');
	}
}
```

##### Fetch Request

```javascript
fetch('https://jsonplaceholder.typicode.com/users')
	.then(response => {
		return response.json();
	})
	.then(users => {
		console.log(users);
	})
```

##### Fetch Request Async

```javascript
async function getUsers() {
    let response = await fetch('https://jsonplaceholder.typicode.com/users');
    let data = await response.json();
    return data;
}

getUsers().then(data => console.log(data));
```

##### RGBA to transparency adjusted HEX

```javascript
function hexify(color) {
  var values = color
    .replace(/rgba?\(/, '')
    .replace(/\)/, '')
    .replace(/[\s+]/g, '')
    .split(',');
  var a = parseFloat(values[3] || 1),
      r = Math.floor(a * parseInt(values[0]) + (1 - a) * 255),
      g = Math.floor(a * parseInt(values[1]) + (1 - a) * 255),
      b = Math.floor(a * parseInt(values[2]) + (1 - a) * 255);
  return "#" +
    ("0" + r.toString(16)).slice(-2) +
    ("0" + g.toString(16)).slice(-2) +
    ("0" + b.toString(16)).slice(-2);
}

var myHex = hexify('rgba(57,156,29,0.05)'); // "#f5faf3"

console.log(myHex);
```

