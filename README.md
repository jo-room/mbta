# MBTA Timings

[https://jo-room.github.io/mbta](https://jo-room.github.io/mbta).

<img width="457" alt="image" src="https://github.com/user-attachments/assets/c76b7a31-0f1e-4982-8971-a95ae5f64ed5" />

This started out as an attempt to create an bus timings web page that runs on a Kindle experimental browser, to have as an in-home bus sign on my fridge door.
It is thus written in the plainest, most archaic JS possible, because turns out if Chrome v1 doesn't support it the Kindle browser doesn't either.

Unfortunately, the Kindle browser also just sucks, and would randomly pop a non-browser error after running smoothly for some random amount of time.
So that didn't end up working, but it does repurpose as a mobile-first website for consolidating timings for multiple possible stops at a given location.

Config options
```json
{
	"title": "Optional page title",
	"stop ID 1": {
		"name": "replaces the default MBTA stop name",
		"message": "any message to add in parentheses after the name",
		"filterRoutes": ["array of string route IDs to keep"],
		"minMinutesAway": 4,
		"maxNumPredictions": 5
	},
	"stop ID 2": {
		"message": "5min away"
	}
}
```

E.g.: [https://jo-room.github.io/mbta/?stops=178,70154&config=%7B%22178%22:%7B%22name%22:%22Near%20Copley%20Square%22,%22message%22:%225min%20away%22,%22filterRoutes%22:%5B%2239%22,%229%22%5D,%22minMinutesAway%22:4,%22maxNumPredictions%22:10%7D,%2270154%22:%7B%22maxNumPredictions%22:5%7D,%22title%22:%22Example%20Title%22%7D](https://jo-room.github.io/mbta/?stops=178,70154&config=%7B%22178%22:%7B%22name%22:%22Near%20Copley%20Square%22,%22message%22:%225min%20away%22,%22filterRoutes%22:%5B%2239%22,%229%22%5D,%22minMinutesAway%22:4,%22maxNumPredictions%22:10%7D,%2270154%22:%7B%22maxNumPredictions%22:5%7D,%22title%22:%22Example%20Title%22%7D)

`key=<MBTA API KEY>` is an optional query param, but the API allows 20 requests/min without a key. We are under that threshold at max 2 requests/min (1 initial set up request, then 1 prediction request/min).

With the deviations, the following might not be Kindle browser legal: `JSON.parse`, `String.prototype.trim()`, \``\` to denote multi-line strings.
