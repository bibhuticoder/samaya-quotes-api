# Contributing

Excited to hear that you are interested in contributing to this project! Thanks!

## Setup

This is a simple HTML based project.

Clone this repo to your local machine and open the `index.html` file on browser.

## Adding/Editing/Removing Quotes 

All of the quotes can be found inside "quotes" folder.

Please make sure you understand the quotes file structure before manipualting it.
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

To add new quote(s), make a new file with a page no in increasing order. Paste your quotes there with appropriate format and increase "totalPages" at `metadata.json`.
```
// format of quote file
[
    {
        "text": "Quote text goex here",
        "author": "Name of author"
    },
]
```

## Quote language/format

We encourage you to add Nepali quotes. Some Nepali words, name of authors can be hard to read in Nepali. In that case English words can be used. Our main goal is to make quotes easlily understandable & readabale.

## Thanks

Thank you again for being interested in this project! You are awesome!
