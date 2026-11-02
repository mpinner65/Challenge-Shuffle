# Challenge Shuffle — all five uploaded decks

## Open and run
Extract the complete folder, open ChallengeShuffle.xcodeproj, select the ChallengeShuffle scheme and an installed iPhone simulator, then press Command-R. Requires Xcode 16+ and iOS 17+. For a physical iPhone, choose your development team under Signing & Capabilities and use a unique bundle identifier.

## Five decks · 250 cards from your photos
| Deck | Cards | Question photo filenames |
| --- | --- | --- |
| Icebreakers | 50 questions | IMG_2022–IMG_2071 |
| Get Real | 50 questions | IMG_2073–IMG_2122 |
| Deep Stuff | 50 questions | IMG_1970–IMG_1999 and IMG_2001–IMG_2020 |
| Together | 49 questions, one activity | IMG_1918–IMG_1967 |
| Reflections Edition | 48 questions, two guided activities | IMG_1843–IMG_1892 |

All five collections now use the wording transcribed from your photographs. Each deck has a photo-to-card transcription list in Content/. Printed line breaks are joined into paragraphs, with typographic quote normalisation. Printed grammatical quirks are retained and noted where relevant. The original photographs are not bundled.

Get Real's generated prompts have been replaced with the 50 question fronts. IMG_2072 supplies its dark-green-and-gold back reference: double border, split-mask symbol, GET REAL title and SPARK wordmark. The other four decks retain their previous designs and content. Card-back geometry, font and colours are recreated from photographs; exact printed fonts and ink colours cannot be established from those photos.

## Playing
Opening a deck shuffles its cards. Tap to reveal, then answer, try the activity or pass. Next card becomes available after revealing; Skip is always available. Cards appear once per round, including skipped cards. At the end, shuffle again. Closing a deck ends its current round. Everything works offline.

The life-story card in Together is labelled CHALLENGE because it asks you to try a two-minute story. The two guided activities in Reflections are also labelled CHALLENGE. These labels are app classifications, not additional generated content.

## Included
- Five reference-based card backs and plain white revealed faces with dark text
- Contrasting Next card and Shuffle again controls in light and dark appearance
- 1024×1024 AppIcon and native launch-screen storyboard
- How to Play via the home screen’s question-mark button
- Five deck descriptions, suggested player counts and optional house rules
- Tap-to-flip animation, Reduce Motion support, larger-text layout and VoiceOver labels

The How to Play view lives inside HomeView.swift to avoid a separate target-membership dependency. iOS controls the launch-screen duration; no artificial delay is added. Favourites, completion tracking, saved progress and appearance settings remain future work.

## Edit and verify
The production catalog is compiled into ChallengeShuffle/Models/CardDeck.swift. Editable sources are in Content/*.txt. Q| means question; C| means activity. Run `python3 Content/update_catalog.py` to rebuild the catalog. Keep line order to preserve prompt IDs. Run `python3 Content/validate_catalog.py` on a Mac with Xcode command-line tools to check the actual Swift catalog and no-repeat logic. Scripts are not needed to run the app.

## Validation
Checked 250 cards for unique IDs and text, 50 cards per deck, 500 no-repeat rounds, completion, restart and empty input. Confirmed the other four collections and gameplay are unchanged. Simulator visuals have not been verified for this update.

Unsigned iPhone Debug build passed with Xcode 27.0.
