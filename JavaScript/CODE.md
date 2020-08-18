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

