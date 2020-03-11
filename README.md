# netlify-plugin-no-more-404 Demo

A demo for Netlify Plugin No More 404

Example site: https://netlify-plugin-no-more-404-demo.netlify.com

- initial deploy (registers manifest) - [Successful Deploy log](https://app.netlify.com/sites/netlify-plugin-no-more-404-demo/deploys/5e69432692ace90008f1ae07)
  ![image](https://user-images.githubusercontent.com/6764957/76458851-8fbb4f00-63b1-11ea-927f-e29f99371b9a.png)
- rename deploy (causes a 404 because no redirect) - [Failed Deploy log](https://app.netlify.com/sites/netlify-plugin-no-more-404-demo/deploys/5e6943a7c771e10009916ed4)
  ![image](https://user-images.githubusercontent.com/6764957/76458964-c09b8400-63b1-11ea-8c70-735002614f49.png)
- add a redirect (resolves 404) - [Successful Deploy log](https://app.netlify.com/sites/netlify-plugin-no-more-404-demo/deploys/5e68289d38d5ec000accb7ba)

![image](https://user-images.githubusercontent.com/6764957/76367978-1c5c0380-6305-11ea-8c75-31a9b1d0bcc5.png)

This demonstrates use of the following Netlify Plugins:

- [netlify-plugin-no-more-404](https://github.com/sw-yx/netlify-plugin-no-more-404)

## Usage

Instructions for running a version of this demo site for yourself.

```bash

# clone the repo
git clone https://github.com/sw-yx/netlify-plugin-no-more-404

# move into working directory and install dependencies
cd netlify-plugin-no-more-404
npm install

# ensure that you have the netlify build command available
# (in future this will be provided via the CLI)
npm install @netlify/build -g

# run the build as netlify would with the build bot
netlify-build
```

## The Netlify Config

This is how the config is set up.

```yaml
plugins:
  plugin-nomo404:
    type: netlify-plugin-no-more-404
    config:
      site: mycoolsite.netlify.com # your Netlify site url
      # https://github.com/dequelabs/axe-cli#running-specific-rules
      axeFlags: --rules color-contrast,html-has-lang
```

## Known issues

- `netlify api updateSite --data='{ "site_id": "418b94bc-...", "body": { "netlify_build_enabled": true  }}'`
- tbc