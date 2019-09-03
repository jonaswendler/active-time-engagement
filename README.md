# GTM/GA Active Time Content Engagement
GTM/GA active time content engagement utilizing session storage

This script is based on the work by Simo Ahava:
- https://www.simoahava.com/analytics/track-content-engagement-via-gtm/
- https://www.simoahava.com/analytics/track-content-engagement-part-2/

I needed to adapt it, since I was working on a high traffic website where people can spend quite a long time. Hence, the 500 hits per session limit was reached for more users than usual. While still under 1% of users, I wanted to see if works without having to send so many hits. Hence, I tried utilizing the session storage.

Browser support is pretty ok:
- https://developer.mozilla.org/en-US/docs/Web/API/Window/sessionStorage
- https://developer.mozilla.org/en-US/docs/Web/API/Window/beforeunload_event

Changes:
- Changed report to push to session storage, except for beforeunload
- Changed key-value pair namings

Beforeunload now doesn't send the time as well, though users that only spent a second probably shouldn't be counted anyway imho.

Issues:
- SPA sites obviously do not work - and are generally a pain in the back (the new iframe?). I'd change the timer to 30sec or simply increase the Hits per Session Limit if the company/client has the premium version (360).
