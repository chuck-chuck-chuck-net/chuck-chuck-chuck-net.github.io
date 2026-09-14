# chuck-chuck-chuck-net.github.io

The index page at `chuck-chuck-chuck-net.github.io`, linking out to the project
sites. Each project publishes its own site from a `gh-pages` branch in its own
repository, under its own subdomain — slaptain at `slaptain.chuck-chuck-chuck.net`,
so the page travels with the repo.

**This repo holds published bytes only.** Everything in it is on the internet:
the landing page, and — after the talk — the built slide deck. Nothing else
belongs here; the operator lives in `chuck-chuck-chuck-net/slaptain`.

## Publishing the deck

The deck's internal master (speaker notes, background material) lives in its own
repository and must not be published. Build the **scrubbed** copy:

    npm run shareable                 # strips every HTML comment into share/
    cd share && SLIDEV_PORTABLE=1 npx slidev build slides.md --base ./ --out dist-single
    cp dist-single/index.html <here>/slaptain/ldapcon/index.html

Speaker notes are compiled into the JavaScript bundle, so publishing a build of
the master copy would publish them. Always build from `share/`.
