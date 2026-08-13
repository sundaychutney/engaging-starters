# Roadmap

Ideas for future development, roughly in order of effort.

## Monetization

Site is teacher-facing (not student accounts). Model: teacher accounts, free vs. Pro subscription.

- **Teacher accounts** — sign up / log in. Requires a backend (Firebase/Supabase) plus a privacy policy covering account data (email, payment) even without student data.
- **Free vs. Pro tier** — all games stay free for everyone (no login required to play). Pro subscription (Stripe or similar) unlocks:
  - Printable worksheets per game/topic
  - Curriculum link documentation (which Victorian/Australian Curriculum outcomes each game/worksheet supports) — useful for teachers writing lesson plans or reports
- **School/site licensing** — flat fee for a whole school covering unlimited teacher accounts, once individual subscriptions are working.

## Growth

- **SEO basics** — meta descriptions, sitemap.xml, descriptive page titles per game, so teachers searching for a topic find the site.
- **Newsletter / email capture** — low-cost way to bring teachers back without relying on ads.
- **More subjects and games** — keep expanding breadth, tagging each with the relevant Victorian/Australian Curriculum links (also feeds the Pro curriculum-link feature above).

## Gameplay features

- **Local high scores** — track each student's personal best per game using `localStorage`, no backend needed, works on the current static site as-is.
- **Real-time multiplayer** — let two students compete head-to-head live (e.g. Flag Guess, Element Hangman) via a shared "room" code, no accounts needed. Needs a backend (Firebase/Supabase) to sync state between browsers.
- **Shared leaderboards** — class-wide leaderboards showing scores, ranked, visible to the teacher. Needs the same backend as multiplayer, so pair this with that work rather than building it separately.
