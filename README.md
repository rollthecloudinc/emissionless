![](https://user-images.githubusercontent.com/73197190/196969015-5c967955-ea75-4a51-ae55-7dd47155d402.png)

Emissionless works alongside [Climate Warrior](https://github.com/apps/climate-warrior) to battle climate change on web. Emissionless provides a set of climate friendly APIs that can be used by Github users that install, authorize the Climate Warrior App for repositories which they would like to use the cross regional cloud hosted emissionless APIs.

# Shapshifter

Supercharge Github repos with RESTful APIs to easily commit JSON and bypass read cache.

| Method | Region: N. Virginia |
| ------------- | ------------- |
| GET  | https://us-east-1.emissionless.services/owner/repo/shapshifter/path/id  |
| POST  | https://us-east-1.emissionless.services/owner/repo/shapshifter/path/id  |

The POST body can be any valid JSON with an id property. The id property is used to distinguish unique json documents within the same provided path. The id of the parameter should match the id inside the json document body.

```javascript
{
  "id": "6f39a72a-6af3-4348-9158-7f111a6d0352"
  "title": "My first document"
}
```

JSON Documents comitted via the shapshifter API will have the user id added automatically of the authenticated user that made the change.


Example Response:
```javascript
{
  "id": "6f39a72a-6af3-4348-9158-7f111a6d0352"
  "title": "My first document",
  "userId": "cc149bd7-83ef-47c5-a397-eb0eb0068e0d"
}
```

View use cases for more specific examples.

Future Features:
* Validation
  * Repository owners will be able to provide [JSON schema](https://json-schema.org/) files that are used to validate entities before commiting. Entities that fail validation will not be comitted producing error messaging instead.
* Search
  * JSON documents become searchable using [Open Search](https://opensearch.org/) API and dashboards. Climate Warrior App installers will have access to both Open Search API and their own dashboards.
  * Index schemas will also be customizable including defining the schema documents will use for indexing.
* Notifications
  * Clients will be able to subscribe to various push notifications during the flow of saving data.
* Webhooks
  * Developers will be able to alter incoming and outgoing data using their own custom webhooks. Including implementing their own validation strategy when JSON Schema doesn't fit the bill.

> Shapeshifter original intent was efficient cost effective means of storing [NxRx Data](https://v8.ngrx.io/guide/data) Entities. The API is being used exclusively with [Druid](https://github.com/rollthecloudinc/druid) our nonprofits sustainaible web development platform built on Reactive Angular. Druid relies heavily on NxRx Data to streamline managing data between the server and browser. Druid entities are currently hard coded into emissionless. Shapshifters goal is to enable a free flow of JSON of all entity types without needing to reploy, modify emissionless.

# Media

Supercharge Github repos with API to upload media files.

# HEDGE

Bounce RESTful requests between data centers using renewable resources.
