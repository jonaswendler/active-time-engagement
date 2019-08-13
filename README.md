# active-time-engagement
GTM/GA active time content engagement utilizing session storage

This script is based on the work by Simo Ahava:
https://www.simoahava.com/analytics/track-content-engagement-via-gtm/
https://www.simoahava.com/analytics/track-content-engagement-part-2/

I needed to adapt it, since I was working on a high traffic website where people can spend a long time. Hence, the 500 hits per session limit was reached for more users than usual. While still under 1% of users, I wanted to see if it can work without having so many hits. Hence, I tried utilizing the session storage.

Browser support for that is pretty ok:
https://developer.mozilla.org/en-US/docs/Web/API/Window/sessionStorage
https://developer.mozilla.org/en-US/docs/Web/API/Window/beforeunload_event

Changes:
- Changed report to push to session storage, except for beforeunload
- Changed key-value pair namings

Beforeunload now doesn't send the time as well, though users that only spent a shouldn't be counted anyway imho.
