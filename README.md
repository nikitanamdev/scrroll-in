# Scrroll In

Never forget where you left a page.

<p float="left">

<a href="https://chrome.google.com/webstore/detail/scrroll-in/cjgjbjogfodppempgdlppgefojbcmjom?hl=en&gl=IN" target="_blank">
<img src="https://developer.chrome.com/webstore/images/ChromeWebStore_Badge_v2_496x150.png" alt="Scrroll In - An extension to save scroll position of any webpage | Product Hunt Embed" style="height:64px;margin-right:20px;" height="64px" /></a>
<a href="https://www.producthunt.com/posts/scrroll-in?utm_source=badge-featured&utm_medium=badge&utm_souce=badge-scrroll-in" target="_blank"><img src="https://api.producthunt.com/widgets/embed-image/v1/featured.svg?post_id=169127&theme=light" alt="Scrroll In - An extension to save scroll position of any webpage | Product Hunt Embed" style="width: 250px; height: 54px;" width="250px" height="54px" /></a>

</p>

> Contribute to this project during hacktoberfest and stand a chance to win exclusive limited edition Devfolio schwag. [Read more](https://devfolio.co/blog/hacktoberfest-2019-devfolio/)

## Motivation

You must have been in a situation wherein you are reading a long article, but you don't have enough time to finish it, so you close the tab, and the next time you open the article again, you have no idea where you left it.

So this extension lets you save the scroll position of the webpage, so you can continue from exactly where you left.

I know there are a few extensions that already serve this purpose, but most of them either didn't work correctly or lacked the features that I needed, so I ended up creating my own.

## How it works?

Under the hood, this extension uses the [chrome localStorage API](https://developer.mozilla.org/en/DOM/Storage#localStorage) to store the scroll positions for different webpages. I avoided using sync storage due to its storage limitations ([read more](https://developer.chrome.com/apps/storage)). This extension creates an object which stores the URL as keys and the scroll position as values.

The functions for adding or updating, reading and deleting are in the files `save.js`, `get.js` and `delete.js` respectively, which are executed as content scripts from `popup.js` whenever the respective button is clicked.

The `background.js` handles switching icon color part whenever a tab is changed, or the URL is updated.

The popup sheet is also handled by `popup.js` by dynamically changing the UI following the availability of the URL in the localStorage object.

## Development

To run the extension locally follow these steps

- Visit `chrome://extensions` and turn on devloper mode.
- Click on load upacked and select the extension root folder.
- Now you can go ahead and modify `popup.js` or `popup.html`, changes would directly be visible in the extension.
- If you change something in `background.js` or `manifest.json` then you will need to reload the extension.

## Contributing

All you need to know for contributing to this project is basic JavaScript, HTML, and CSS.

You can visit the issues page to find some relevant issues to contribute to or feel free to open a new issue for something that you think can be improved.

Also, if you have any doubts regarding any of the concepts or how to get started, feel free to drop me a message on [twitter](https://twitter.com/psuranas) or the [Devfolio community telegram group](https://t.me/devfolio).

Regards
