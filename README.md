Slidge 🛷
========

[Home](https://sr.ht/~nicoco/slidge) |
[Source](https://sr.ht/~nicoco/slidge/sources) |
[Issues](https://sr.ht/~nicoco/slidge/trackers) |
[Patches](https://lists.sr.ht/~nicoco/public-inbox) |
[Chat](xmpp:slidge@conference.nicoco.fr?join)

Turn any XMPP client into that fancy multiprotocol chat app that every cool kid want.

[![Documentation status](https://readthedocs.org/projects/slidge/badge/?version=latest)](https://slidge.readthedocs.io/)
[![builds.sr.ht status](https://builds.sr.ht/~nicoco/slidge/commits/master/.build.yml.svg)](https://builds.sr.ht/~nicoco/slidge/commits/master/.build.yml?)
[![pypi](https://badge.fury.io/py/slidge.svg)](https://pypi.org/project/slidge/)

Slidge is a general purpose XMPP (puppeteer) gateway framework in python.
It's a work in progress, but it should make
[writing gateways to other chat networks](https://slidge.readthedocs.io/en/latest/dev/tutorial.html)
(*plugins*) as frictionless as possible.

It comes with a few plugins included.

|            | Direct messages | Presences | Typing | Marks | Upload | Correction |
|------------|-----------------|-----------|--------|-------|--------|------------|
| Signal     | ✓               | N/A       | ✓      | ✓     | ✓      | N/A        |
| Telegram   | ✓               | ~         | ✓      | ✓     | ✓      | ✓          |
| Mattermost | ✓               | ✓         | ✗      | ✗     | ✗      | ✗          |
| Facebook   | ✓               | ✗         | ✓      | ✓     | ✓      | ✓          |
| Skype      | ✓               | ✗         | ✗      | ✗     | ~      | ✗          |
| Steam      | ✗               | ✗         | ✗      | ✗     | ✗      | ✗          |

(this table may not be entirely accurate, but **in theory**, stuff marked ✓ works)


Status
------

Slidge is alpha-grade software.
Right now, only direct messages are implemented, no group chat stuff at all.
Direct messaging does (more or less) work though.
Any contribution whatsoever (testing, patches, suggestions, beer, …) is more than welcome.
Don't be shy!

Testing locally should be fairly easy, so please go ahead and give me some
feedback, through the [MUC](xmpp:slidge@conference.nicoco.fr?join), the
[issue tracker](https://todo.sr.ht/~nicoco/slidge) or in my
[public inbox](https://lists.sr.ht/~nicoco/public-inbox).

Installation
------------

#### docker-compose

Docker-compose spins up a local XMPP server preconfigured for you. 

```
docker-compose up # or poetry install && poetry run `python -m slidge`
```

For the other options, you need a
[configured](https://slidge.readthedocs.io/en/latest/admin/general.html#configure-the-xmpp-server)
XMPP server.

#### poetry

```
poetry install
poetry run python -m slidge
```

#### pip

```bash
pip install slidge[signal]  # you can replace signal with any network listed in the table above
python -m slidge --legacy-module=slidge.plugins.signal
```

### XMPP client

Open [gajim](https://gajim.org) (or another XMPP client),
and add your account (``test@localhost`` / ``password`` if you use the server provided with docker-compose).
Go to "Accounts"→"Discover services" (or equivalent).
You should see the slidge gateways as server components.

About privacy
-------------

Slidge (and most if not all XMPP gateway that I know of) will break
end-to-end encryption, or more precisely one of the 'ends' become the
gateway itself. If privacy is a major concern for you, my advice would
be to:

-   use XMPP + OMEMO
-   self-host your gateways
-   have your gateways hosted by someone you know AFK and trust

Related projects
----------------

-   [Spectrum](https://www.spectrum.im/)
-   [Bitfrost](https://github.com/matrix-org/matrix-bifrost)
-   [Mautrix](https://github.com/mautrix)
-   [matterbridge](https://github.com/42wim/matterbridge)
-   [XMPP-discord-bridge](https://git.polynom.me/PapaTutuWawa/xmpp-discord-bridge)
