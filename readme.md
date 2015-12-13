# DIY Trove Exhibition

## The quickstart version

1. Get yourself a GitHub account (the free version is fine).
2. Get yourself a Trove API key.
2. Come back to this page and click on the 'Fork' button. Follow the instructions to save a copy of this repository under your own account.
3. Go to your account and view the repository you've just created. It will look just like this one!
4. Click on the 'Settings' tab and change the repository name to suit your exhibition.
5. Click on the 'Code' tab and then on the `index.html` file to open it.
6. Click on the pencil icon to edit the file.
7. Look for the 'EDIT THIS SECTION TO INCLUDE YOUR EXHIBITION DETAILS' message in the `index.html` file and add the details of your exhibition as described in the customisation section below.
8. Click on the 'Commit changes' button to save your details.
9. That's it! Your hew exhibition will be available at the address -- http://[your Github user name].github.io/[your repository name]

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

## Customising your exhibition's style


