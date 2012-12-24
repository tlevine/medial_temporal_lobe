Medial Temporal Lobe
==========
The Medial Temporal Lobe remembers websites for you.

    mtl [action] [url] [-ht] [--mtl-dir directory]

    -h  Help
    -t  Tags, comma-separated, allowed characters: [0-9_]

For now, the only `action` is `add`. I might implement `remove` and `show`
eventually. So you might do something like this.

    mtl add thomaslevine.com -h superheroes,pink,letterpress

## Technical stuff
Medial Temporal Lobe depends on

* uuidgen

Websites are saved to the `~/.medial_temporal_lobe` directory, which is a git
repository. You must initialize it and set and upstream remote.

    mkdir ~/.medial_temporal_lobe
    cd ~/.medial_temporal_lobe
    git init
    git remote add origin [address]
    echo Memories > README
    git add README
    git commit README -m create\ repository
    git push -u origin master

Medial Temporal Lobe makes that directory looks like this.

    .medial_temporal_lobe/
        memories/
            7949356f-df36-4938-9dc2-424cf1d127e9/
                source
                info
        tags/
            cats/
                9e3b9b9e-2316-4bf5-bd11-7571af95d713/ -> ../../memories/9e3b9b9e-2316-4bf5-bd11-7571af95d713
            data/
                7949356f-df36-4938-9dc2-424cf1d127e9/ -> ../../memories/7949356f-df36-4938-9dc2-424cf1d127e9
            pizza/
                7949356f-df36-4938-9dc2-424cf1d127e9/ -> ../../memories/7949356f-df36-4938-9dc2-424cf1d127e9

The `source` of each memory is the source of whatever url was specified
(an ordinary GET request), and the `info` looks like this.

    url=http://thomaslevine.com/!/new-york-pizza

It might have other lines eventually.
