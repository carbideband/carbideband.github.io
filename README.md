# carbideband.github.io
#### The repository for Carbide's website

www.carbi.de.com is made possible by the following awesome projects & services:
- [Github](https://github.com/)
- [FullPage.js](https://alvarotrigo.com/fullPage/)
- [Jekyll](https://jekyllrb.com/)'s [Minima Theme](https://github.com/jekyll/minima)

Using Github as a host, requires only a domain name to be registered (if you even want a custom domain).
CNAME must be set within repo & domain provider DNS settings, if you do.
Caveat being that gh-pages only allows the use of static pages.
Fullpage.js allows the use of JavaScript to make Github's static pages a bit more versatile.
In our usecase, what we wanted was for users to be able to browse the webpage, without interrupting the music player.

Reference the [README for FullPage.js](https://github.com/alvarotrigo/fullPage.js/blob/master/README.md) to modify and understand how slides are set up for your usecase.
Once a [license](https://github.com/alvarotrigo/fullPage.js#license) is acquired, it is possible to use the current 'licenseKey' implementation using [Google Tag Manager](https://marketingplatform.google.com/about/tag-manager/) by changing the 'GTM-xxxxxxx' string to your own and setting an html variable in 'Tags' based on the [link here](https://github.com/carbideband/carbideband.github.io/commit/52853ff42aba47ad8fb56e7e1663e46a376730f8). This way, you protect your license, while still remaining open source.

Sidenote about Jekyll: It is a great way to make an exceptional static blog with little to no programming background
and their Minima theme is amazing.
It is great for just about any website (so long as you do some modifying).

Hope this helps out anyone else looking to create a website similar to ours.
