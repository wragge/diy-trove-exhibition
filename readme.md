# DIY Trove Exhibition

**With nothing more than [Trove](http://trove.nla.gov.au) and a GitHub account you can create your own online exhibition in minutes!**

See a live exhibition using this repository here:

http://wragge.github.io/forecasters-demo/

Before you get started you'll need to have some Trove lists ready to provide the content for your exhibition. [Trove lists](http://help.nla.gov.au/trove/using-trove/creating-contributing/lists) are just collections of items found on Trove -- they're easy to create, manage, and edit.

The demo above uses three lists:

* [A day in the life of Mr Mares, weatherman](http://trove.nla.gov.au/list?id=43805)
* [Clement Wragge](http://trove.nla.gov.au/list?id=83777)
* [Inigo Jones](http://trove.nla.gov.au/list?id=83774)

You could create an exhibition with just one list, but it's probably better to divide your content between a number of lists. Each list is displayed as a 'topic' in the exhibition.

Once you have your lists, just follow the [quickstart](#quickstart) instructions below!

## Quickstart

1. Get yourself a [GitHub](https://github.com) account (the free version is fine) and log in.
2. Get yourself a [Trove API key](http://help.nla.gov.au/trove/building-with-trove/api).
2. Come back to this page and click on the 'Fork' button (in the top right hand corner of the page) to save a copy of this repository under your own account. [More about forking](https://help.github.com/articles/fork-a-repo/).
3. Go to your account and view the repository you've just created. It will look just like this one!
4. Click on the 'Settings' tab and change the repository name to suit your exhibition.
5. Click on the 'Code' tab and then on the `index.html` file to open it.
6. Click on the pencil icon to edit the file.
7. Look for the **'EDIT THIS SECTION TO INCLUDE YOUR EXHIBITION DETAILS'** message in the `index.html` file and add the details of your exhibition as described in the [customisation section](#customisation-guide) below.
8. Click on the 'Commit changes' button to save your details.
9. That's it! Your hew exhibition will be available at the address -- http://**[your Github user name]**.github.io/**[your repository name]**. For example, my user account is 'wragge' and I created a version of this repository called 'forecasters-demo', so you can find it online at http://wragge.github.io/forecasters-demo/ .

## Customisation guide

There are six blocks of information you need to add or edit in the `index.html` file:

* Your exhibition's name
* Your exhibition's tagline 
* A description of your exhibition
* A brief 'About this exhibition' statement that lives in the site footer
* A list of the Trove lists that make up your exhibition
* Your Trove API key

There are samples of each of these (except the API key) in the `index.html` file. They all sit inside a block of HTML labelled 'EDIT THIS SECTION TO INCLUDE YOUR EXHIBITION DETAILS'.

This is the element that contains the exhibition name:

```html
<h1 ng-hide="listHide" class="ng-hide" id="exhibition-name" class="page-header">Forecasters</h1>
```

Obviously you should change 'Forecasters' to the name of your exhibition, but leave the rest of the tag and its attributes alone.

This is the element that contains the exhibition tagline:

```html
<h2 ng-hide="listHide" class="ng-hide" id="exhibition-tagline">An assortment of weather prophets</h2>
```

As above, just change the text but leave the rest of the tag and its attributes alone.

The exhibition description is a little different:

```html
<div ng-hide="listHide" class="ng-hide" id="exhibition-description">
    <p>This site displays content from Trove. It is a demonstration of how resources collected using <a href="http://help.nla.gov.au/trove/using-trove/creating-contributing/lists">Trove lists</a> can be reused through the <a href="http://help.nla.gov.au/trove/building-with-trove">Trove API</a> to create new interfaces and applications.</p>
</div>

```

Leave the `<div></div>` tags alone, but in between them you can include whatever HTML code you want.

The exhibition credit is similar:

```html
<div ng-hide="listHide" class="ng-hide" id="exhibition-credit">
    <p><small>This demonstration was created by <a href="http://discontents.com.au/about-me">Tim Sherratt</a> (<a href="http://twitter.com/wragge">@wragge</a>) to show how easy it is to create your own exhibition.</small></p>
</div>
```

You can change anything between the `<div></div>` tags, but to keep the formatting consistent it's best to enclose your text in `<p><small></small></p>` tags as demonstrated.

The list of lists is the most important thing you need to customise, without it your exhibition will have no content! Here's the example version:

```html
<ul ng-hide="listHide" class="ng-hide" id="lists">
    <!-- CHANGE THIS TO LIST THE TROVE LISTS THAT MAKE UP YOUR EXHIBITION -->
    <li><a class="list-link" href="http://trove.nla.gov.au/list?id=43805">A day in the life of Mr Mares, weatherman</a></li>
    <li><a class="list-link" href="http://trove.nla.gov.au/list?id=83777">Clement Wragge</a></li>
    <li><a class="list-link" href="http://trove.nla.gov.au/list?id=83774">Inigo Jones</a></li>
</ul>

```

You'll see there are three Trove lists linked here. Each one looks like this:

```html
<li><a class="list-link" href="http://trove.nla.gov.au/list?id=43805">A day in the life of Mr Mares, weatherman</a></li>

```

For each of your lists you need to add an `<li></li>` tag just like this. The `href` value should be the url of your list as it appears on Trove. Don't change the other attributes. Replace 'A day in the life of Mr Mares, weatherman' with the name of your list. Note, however, that this name is just a fallback -- the site will automatically grab the name of the list as it appears of Trove to use in the exhibition.

Finally, find the line that says:

```javascript
var troveAPIKey = "";
```

Simply insert your Trove API key between the quotes.

## Changing the look of your exhibition

By default your exhibition will be styled using [Bootstrap](http://getbootstrap.com) and a slightly modified version of the [Sandstone Bootswatch theme](https://bootswatch.com/sandstone/). The style information is contained within two files in the `styles` directory: 

* `theme.css` -- includes all the basic Bootstrap stuff
* `style.css` -- a few extra customisations for the exhibition

If you're feeling brave you can dive in and edit `theme.css` to change things like colours and fonts. However, it's probably easier to use a site like the [Bootstrap Live Customiser](http://bootstrap-live-customizer.com) to create your own theme. You can start with the basic Bootstrap style or build on one of the [Bootswatch](https://bootswatch.com/) themes. Once you've created your own custom theme, simply copy the CSS code into the `theme.css` file in your repository and commit the changes.

You'll probably also want to tweak `style.css` to match your custom theme.

The style is of course responsive by default, so it should look good on mobile devices. Try swiping one of the item pages!

## More advanced customisation

It's possible to [set up a custom domain](https://help.github.com/articles/setting-up-a-custom-domain-with-github-pages/) to use for your exhibition.

Of course you don't have to use GitHub to host your exhibition. You can just copy the contents of your repository to any old webserver and it will just work.

If you want to change the page layout or navigation then you'll need to grab the [full code repository](https://github.com/wragge/trove-lists-exhibition) and set up your local development environment using [Node](https://github.com/wragge/trove-lists-exhibition), [Grunt](http://gruntjs.com), and [AngularJS](https://angularjs.org). 

## Limitations

Because of the way forking works on GitHub, you can only fork a repository once into your own account. That means you can only create one exhibition.

The easiest, but kludgiest, way around this is to create a new GitHub organisation, and then fork your second exhibition into your new organisation's account. To create a new organisation just click on the '+' sign at the top of the screen and choose 'New organisation'.

If you're making lots of exhibitions you might want to install Git on your local computer. You'll then be able to make multiple exhibitions without fuss.
