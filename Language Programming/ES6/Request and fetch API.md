In JavaScript, you can use the XMLHttpRequest object for making HTTP requests or the more modern fetch API. Here, I'll provide examples for both.

Using fetch API (modern approach):

The fetch API is more modern and provides a simpler and more powerful interface for making HTTP requests. It returns a Promise that resolves to the Response object representing the completion or failure of the request.

GET Request:
```JS

fetch('https://api.example.com/data')
  .then(response => {
    if (!response.ok) {
      throw new Error('Network response was not ok');
    }
    return response.json();
  })
  .then(data => {
    console.log(data);
  })
  .catch(error => {
    console.error('Error during fetch operation:', error);
  });
```

POST Request:
```JS

fetch('https://api.example.com/data', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
    // Additional headers if needed
  },
  body: JSON.stringify({
    key1: 'value1',
    key2: 'value2',
  }),
})
  .then(response => {
    if (!response.ok) {
      throw new Error('Network response was not ok');
    }
    return response.json();
  })
  .then(data => {
    console.log(data);
  })
  .catch(error => {
    console.error('Error during fetch operation:', error);
  });

```
Using XMLHttpRequest (older approach):

GET Request:
```JS

  var xhr = new XMLHttpRequest();
  xhr.open('GET', '[https://api.example.com/data](https://api.example.com/data)', true);
  xhr.onreadystatechange = function () {
    if (xhr.readyState == 4 && xhr.status == 200) {
      var data = JSON.parse(xhr.responseText);
      console.log(data);
    }
  };
  xhr.send();
```

POST Request:

```JS
  var xhr = new XMLHttpRequest();
  xhr.open('POST', '[https://api.example.com/data](https://api.example.com/data)', true);
  xhr.setRequestHeader('Content-Type', 'application/json');
  xhr.onreadystatechange = function () {
    if (xhr.readyState == 4 && xhr.status == 200) {
      var data = JSON.parse(xhr.responseText);
      console.log(data);
    }
  };
  xhr.send(JSON.stringify({
    key1: 'value1',
    key2: 'value2',
  }));
```

The fetch API is generally recommended for modern applications due to its simplicity and support for promises. However, if you need to support older browsers or require more fine-grained control over the request, you might still use XMLHttpRequest.