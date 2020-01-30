# graph-pager

Utility to get paged results from The Graph endpoints

## Example Usage

```javascript
graphResultsPager({
	api: 'https://api.thegraph.com/subgraphs/name/...',
	max: 12, // a single fetch can return 1000 results, any larger and mulitple requests will be required
	query: {
		entity: '...',
		selection: {
			orderBy: '...',
			orderDirection: 'desc',
			where: {
				someStringField: `\\"${someValue}\\"`, // use double quotes for strings / bytes / addresses
				someNumber: 321,
			},
		},
		properties: [
			// name of the entity's fields you want returned
		],
	},
});
```
