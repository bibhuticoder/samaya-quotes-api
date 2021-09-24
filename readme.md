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

1. Call metadata endpoint to get info regarding the API
```
https://bibhuticoder.github.io/samaya-quotes-api/quotes/metadata.json
```

```
// sample response
{
    "totalPages": 5,
    "featured": [
        4,
        5
    ]
}
```

2. Get quotes from specific page (eg: 2)
```
https://bibhuticoder.github.io/samaya-quotes-api/quotes/2.json
```

```
// sample response
[
    {
        "text": "सुरू गर्ने तरीका भनेको कुरा गर्न छोड्नु र गर्न थाल्नु हो",
        "author": "Walt Disney"
    },
    {
        "text": "पैसाको अभाव भन्नु केवल बाहना मात्र हो, तिमीसंग स्पष्ट लक्ष्यको अभाव भएको हो ।",
        "author": null
    },
    {
        "text": "परिश्रम त्यो साँचो हो जसले भाग्यको ढोका खोल्दछ ।",
        "author": null
    }
]
```

### Example(JavaScript)
```
    function getRandomQuote() {
        fetch('https://bibhuticoder.github.io/samaya-quotes-api/quotes/metadata.json').then(r => r.json()).then(metadata => {
            let randomPage = random(1, metadata.totalPages);
            fetch('https://bibhuticoder.github.io/samaya-quotes-api/quotes/2.json' + randomPage + '.json').then(r => r.json()).then(quotesData => {
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
