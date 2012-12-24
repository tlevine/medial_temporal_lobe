Medial Temporal Lobe
==========
The Medial Temporal Lobe remembers websites for you.

    ./mtl [action] [-ht] [url]

    -h  Help
    -t  Tags, comma-separated

For now, the only `action` is `add`. I might implement `remove` and `show`
eventually.

## Technical stuff
Medial Temporal Lobe depends on

* uuidgen

Websites are saved to the `~/.medial_temporal_lobe` directory, which is a git
repository. It gets created if it doesn't exist. That directory looks like this.

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
