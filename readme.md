# Samaya-Quotes-API

This repository contains the quotes used by Samaya Chrome Extension. 
[Install Chrome Extension](https://chrome.google.com/webstore/detail/samaya/jmpipanemahgfelokjjpdilfcfboinni)

## API Structure
The `metadata.json` file contains all the required information for the API. The quotes are seperated into pages to minimize network data usage. Featured array in metadata contains page No of featured quotes.
```
{
    "totalPages": 3,
    "featured": [
        1,
        3
    ]
}
```

## Usage
```
    function getRandomQuote() {
        fetch('./quotes/metadata.json').then(r => r.json()).then(metadata => {
            let randomPage = random(1, metadata.totalPages);
            fetch('./quotes/' + randomPage + '.json').then(r => r.json()).then(quotesData => {
                let randomQuote = quotesData[random(0, quotesData.length - 1)];
                // you got the quote 😀
            })
        })
    }

    function random(min, max) {
        return Math.floor(Math.random() * (max - min + 1)) + min;
    }
```

## View Quotes
https://bibhuticoder.github.io/samaya-quotes-api