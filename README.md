# MBTA Timings

This started out as an attempt to create an bus timings web page that runs on a Kindle experimental browser, to have as an in-home bus sign on my kitchen door.
It is thus written in the plainest, most archaic JS possible, because turns out if Chrome v1 doesn't support it the Kindle browser doesn't either.

Unfortunately, the Kindle browser also just sucks, and would randomly pop an error after running smoothly for some time.
So that didn't end up working, but it does repurpose as a mobile-first website for consolidating timings for multiple possible stops at a given location.

Usage: `https://jo-room.github.io/mbta/?stops=<comma-delimited list of MBTA stop IDs, with optional minutes distance from stop in parenthesis>&key=<MBTA API KEY>`

E.g.: `https://jo-room.github.io/mbta/?stops=191(3),70075&key=<MBTA API KEY>`

<img width="457" alt="image" src="https://github.com/user-attachments/assets/c76b7a31-0f1e-4982-8971-a95ae5f64ed5" />

