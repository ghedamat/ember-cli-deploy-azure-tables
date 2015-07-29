# Ember-cli-deploy-azure-tables

Deploy the bootstrap index.html of your Ember App to Azure Tables using [ember-cli-deploy](https://github.com/ember-cli/ember-cli-deploy). This plugin is for `ember-cli-deploy` >= 0.5.0.
See [ember-cli-deploy-azure](https://github.com/duizendnegen/ember-cli-deploy-azure) for a plugin pack for Azure Tables, Azure Blob & the default build and hashing included.

## Installation

* `npm install ember-cli-deploy-azure-tables`
* `npm install ember-cli-deploy-build` (or another ember-cli-deploy build tool)
* `npm install ember-cli-deploy-revision-key` (or another ember-cli-deploy hashing tool)

## Configuration

In your `config/deploy.js` file:
```javascript
module.exports = function(environment) {
  var ENV = {};

  if (environment === 'production') {
    ENV["azure-tables"] = {
      storageAccount: "my-storage-account",
      storageAccessKey: "my-access-key"
    };
  }

  return ENV;
}
```

You can also connect using your connection string, set it as `connectionString: "my-connection-string"`.

## Usage

* `ember deploy <environment>` to build and upload index.html to Azure Tables
* `ember deploy:activate --revision <key> <environment>` to activate an uploaded revision
