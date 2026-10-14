Transcript (example, fictional product — Edumatica, an online-course app)
Meeting: weekly sync, 15 September 2026
Present: Anna (product), Boris (engineering), Vera (support)

Vera: Thirty-four tickets in two weeks, all the same thing. People don't see
that a new message from their teacher has arrived. They log in once a week and
find a reply that's three days old.

Anna: Would push notifications fix it?

Boris: They would, but not this quarter. We haven't stood up the iOS
notification service — that's about three weeks of work on its own. We won't
start before December.

Anna: What about an unread counter on the section icon?

Boris: That's two days. The data already reaches the client, we just have to
show the number.

Vera: That takes half the tickets away. At least people will see there's
something there.

Anna: Then we ship the counter now and defer push. My call, I'll write it down.

Boris: Just remember the number has to reset when the section opens, otherwise
it sits there forever. And it's not clear what to show above 99.

Anna: No idea about the 99. I'll ask design.
