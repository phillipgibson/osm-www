![osm-website](https://user-images.githubusercontent.com/686194/88725480-03e85c00-d0e1-11ea-8e3e-92eaf971b918.png)

Welcome to the source file repository for the [Open Service Mesh website](https://openservicemesh.io). The website is a simple static site, built with [Hugo](https://gohugo.io/) and hosted on [Netlify](https://app.netlify.com/sites/openservicemesh/settings/general).

---

## Structure

There are various parts to a hugo site, these are the key bits:

```
/public        // 'dist' generated website - do not edit
/resources     // compiled css assets - do not edit
/themes        // source files for the website - edits go here
config.yaml
```

Looking for logos? Latest brand assets for OSM can be found over at [/community/logos](https://github.com/openservicemesh/osm/tree/master/community/logos).


## Development

```
// run hugo to have the pipes rebuild and recompile
# hugo

// make sure to commit the generated results to git
# git add resources/*
```

#### Editing the Content

The website is broken up into html partials per section (e.g. navbar, footer, about, community). To edit the content, you need to modify [these source html files](https://github.com/openservicemesh/osm-www/tree/master/themes/clean-landing/layouts/partials) in the site theme.

*Do not make edits** to the code in the `/public` directory, this is overwritten each time the site is rebuilt!

In addition, certain pieces of content are set globally via the [config.yaml](https://github.com/openservicemesh/osm-www/blob/master/config.yaml#L10) file:

* site descrition
* site webfonts
* navbar: links
* about section: feature points
* _etc_


#### Editing the Theme

The site uses a custom Hugo theme called [clean-landing], which is a boilerplate based off of the [hugo-fresh](https://themes.gohugo.io/hugo-fresh/) theme by Luc Perkins. The theme uses the Bulma css framework, which provides a mobile-friendly reponsive grid (using flexbox), icon sets and easily configurable site parameters.

* [Theme parameters](https://github.com/openservicemesh/osm-website/blob/master/config.yaml#L10)
* [Bulma CSS docs](https://bulma.io/)

Any design changes should be to the source SASS files here, which are will generate new CSS files each time Hugo recompiles, via [hugo pipes](https://gohugo.io/hugo-pipes/). Remember to commit any changes to the generated css/js files afterwards (the `/resources` folder)!


## Deployment

The site is automatically rebuilt on Netlify when changes are merged into `master` branch. You view build logs by clicking on the badge below:

[![Netlify Status](https://api.netlify.com/api/v1/badges/20d9e614-d807-496f-ade7-99510b5fd12c/deploy-status)](https://app.netlify.com/sites/openservicemesh/deploys)

## Contributing

If you would like to contribute to the OSM website, see [CONTRIBUTING.md](CONTRIBUTING.md).

## Code of Conduct

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/). See [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) for further details.
