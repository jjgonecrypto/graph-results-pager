# graph-pager

Utility to get paged results from The Graph endpoints

## Usage

```javascript
graphResultsPager({
	api: 'https://api.thegraph.com/subgraphs/name/...',
	// Note: a single subgraph fetch can return 1000 results, any larger numbers will trigger multiple fetches
	max: 12, // leave empty for all results
	query: {
		entity: '...',
		selection: {
			orderBy: '...',
			orderDirection: 'desc',
			where: {
				// Note: the below filters are combined - like the AND operater in an SQL WHERE clause
				someStringField: `\\"${someValue}\\"`, // use double quotes for strings / bytes / addresses
				someNumber: 321, // numbers don't require escaping
				// ...
				willBeIgnored: undefined, // useful if you want to use the ternary operator for inline checks
			},
		},
		properties: [
			'id',
			...ss, // the list of the entity's fields you want returned
		],
	},
});
```

For an example in node, try running `node example.js`
