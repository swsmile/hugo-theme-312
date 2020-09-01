# 312 Theme for Hugo

312 is a super awesome theme for Hugo.

# Main Features

- Perfect workflow with [Typora](https://typora.io/)
- Awesome built-in banners 
- Customize Image URL
- Well designed Table of Content
- Support full-text search

## Installation

Navigate to your themes folder in your Hugo site and use the following commands:

```
git submodule add https://github.com/swsmile/hugo-theme-312.git themes/hugo-theme-312
hugo server
```

Run Hugo Build-in Server Locally

```
hugo server -t hugo-theme-312
```

Now enter [`localhost:1313`](http://localhost:1313/) in the address bar of your browser.

For more information read the official [setup guide](https://gohugo.io/overview/installing/) of Hugo

## Site Search with Algolia

Follow this [tutorial](https://forestry.io/blog/search-with-algolia-in-hugo/#3-create-your-index-in-algolia) to create your index in Algolia. The index is just the storage of the indexing data of your site in the the cloud . The search page of 312 theme will utilize this indexing data to do the search.

Go to the directory where you have your Hugo site and run the following commands:

```
$ npm init
$ npm install atomic-algolia --save
```

Next, open up the newly created package.json, where we’ll add an NPM script to update your index at Algolia. Find "scripts", and add the following:

```
"algolia": "atomic-algolia"
```

Algolia index output format has already been supported by the 312 theme, so you can just build your site, then you’ll find a file called algolia.json in the root, which we can use to update your index in Algolia. Generate index file:

```
$ hugo
```

Now you can push your index to Algolia by running:

```
$ ALGOLIA_APP_ID={{ YOUR_APP_ID }} ALGOLIA_ADMIN_KEY={{ YOUR_ADMIN_KEY }} ALGOLIA_INDEX_NAME={{ YOUR_INDEX_NAME }} ALGOLIA_INDEX_FILE=public/algolia.json npm run algolia
```

Add the following variables to your hugo site config so the search page can get access to algolia index data in the cloud:

```
algolia_search = true
algolia_appId = {{ YOUR_APP_ID }}
algolia_indexName = {{ YOUR_INDEX_NAME }}
algolia_apiKey = {{ YOUR_ADMIN_KEY }}
```

Open search page in your browser: http://localhost:1313/search

# Acknowledgements
- [Clean White Theme](https://github.com/zhaohuabing/hugo-theme-cleanwhite)
- [huxblog Jekyll Theme](https://github.com/Huxpro/huxpro.github.io)
- [Clean Blog Jekyll Theme](https://github.com/BlackrockDigital/startbootstrap-clean-blog-jekyll)

