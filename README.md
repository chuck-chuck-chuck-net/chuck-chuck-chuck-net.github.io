# chuck-chuck-chuck-net.github.io

The published site for `slaptain.chuck-chuck-chuck.net` (and, until the custom
domain is attached, for `chuck-chuck-chuck-net.github.io`).

**This repo holds published bytes only.** Everything in it is on the internet:
the landing page, and — after the talk — the built slide deck. Nothing else
belongs here; the operator lives in `chuck-chuck-chuck-net/slaptain`.

## Layout

    index.html          the project index
    slaptain/           the slaptain page
    slaptain/ldapcon/   the talk deck (added after the talk)
    .nojekyll           serve files verbatim, no Jekyll processing

Per-project pages live under their own path, so a second project (littlered)
gets `/littlered` without disturbing the first.

## Publishing the deck

The deck's internal master (speaker notes, background material) lives in its own
repository and must not be published. Build the **scrubbed** copy:

    npm run shareable                 # strips every HTML comment into share/
    cd share && SLIDEV_PORTABLE=1 npx slidev build slides.md --base ./ --out dist-single
    cp dist-single/index.html <here>/slaptain/ldapcon/index.html

Speaker notes are compiled into the JavaScript bundle, so publishing a build of
the master copy would publish them. Always build from `share/`.
