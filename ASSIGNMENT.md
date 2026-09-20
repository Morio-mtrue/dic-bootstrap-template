# Bootstrap series assignment - Utilization of Bootstrap template

Changes made to `startbootstrap-clean-blog` (Bootstrap 5.2.3).

Both the built `dist/` pages and the `src/pug` and `src/scss` sources were
updated, so rebuilding the template reproduces the same result.

## CONTACT page (`dist/contact.html`, `src/pug/contact.pug`)

The floating-label form was replaced with Bootstrap's horizontal form layout,
so every label sits on one line with its input.

| Requirement | How |
| --- | --- |
| Label and input on one line each | `.row` with `.col-sm-2.col-form-label` and `.col-sm-10` |
| Same label and input form as the sample | Email, Password, Radios, Example checkbox |
| Select one of the radio buttons | Three `form-check` radios sharing `name="gridRadios"`, the first checked, the third disabled |
| "SIGN IN" button relabelled | `button#submitButton` now reads Send, rendered uppercase by `text-uppercase` |
| No other layout changes | Header, intro paragraph and footer untouched |

## HOME page (`dist/index.html`, `src/pug/index.pug`)

The four `post-preview` blocks became four Cards.

| Requirement | How |
| --- | --- |
| Uses the Card component | `a.card` with `card-img-top`, `card-body`, `card-title`, `card-text` |
| Image and text on the Card | Each card carries one of the template's own images |
| Text does not extend beyond the Card | `overflow: hidden` on the card plus line clamping on title and text |
| Card heights equal | Fixed 220px image and 180px body, `h-100` inside the column |
| Whole Card is a link | The card element itself is the `<a>` |
| Card link does not extend beyond the Card | The link is the card, so its box is exactly the card's box |
| 4 Cards in 2 rows of 2 | `.col-sm-6` inside one `.row` |
| Column centred | `.row.justify-content-center` inside the template's centred column |
| OLDER POSTS centred | `d-flex justify-content-center` replaces `justify-content-end` |
| Date lines removed | The `post-meta` paragraphs are gone |

New styles live in `src/scss/components/_post-card.scss`, imported from
`styles.scss`, and mirrored into `dist/css/styles.css`.

## Measured in the browser at 1280px

- 4 cards, 2 rows, 2 per row, each column exactly 50% of the row
- All four cards 402px tall (one distinct height)
- No child element extends past its card
- Every card is an `<a>` whose box matches the card exactly
- OLDER POSTS centred within its container
- Contact form: Email, Password and Radios each on one line, 3 radios with
  exactly one checked, button text Send rendered uppercase

## Note on the sample images

The gyazo screenshots in the assignment text were returning 502 while this was
built, so the CONTACT form follows the Bootstrap Forms horizontal layout
example the hint points to, which is the one with the radio group and the
"Sign in" button the requirement asks to relabel.
