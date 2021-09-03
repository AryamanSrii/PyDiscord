# PyDiscord

[![Discord server invite](https://discord.com/api/guilds/336642139381301249/embed.png)](https://discord.gg/r3sSKJJ) [![PyPI version info](https://img.shields.io/pypi/v/discord.py.svg)](https://pypi.python.org/pypi/discord.py) [![PyPI supported Python versions](https://img.shields.io/pypi/pyversions/pydiscord.svg)](https://pypi.python.org/pypi/pydiscord)

A modern, easy to use, feature-rich, and async ready API wrapper for
Discord written in Python, based on `discord.py`.


## Key Features

-   Modern Pythonic API using `async` and `await`.
-   Proper rate limit handling.
-   Optimised in both speed and memory.

## Installing

**Python 3.8 or higher is required**

To install the library without full voice support, you can just run the
following command:

```sh
# Linux/macOS
python3 -m pip install -U pydiscord

# Windows
py -3 -m pip install -U pydiscord
```

Otherwise to get voice support you should run the following command:

```sh
# Linux/macOS
python3 -m pip install -U "pydiscord[voice]"

# Windows
py -3 -m pip install -U pydiscord[voice]
```

To install the development version, do the following:

```sh
$ git clone https://github.com/PyDiscord/PyDiscord
$ cd PyDiscord
$ python3 -m pip install -U .[voice]
```

## Optional Packages

-   [PyNaCl](https://pypi.org/project/PyNaCl/) (for voice support)

Please note that on Linux installing voice you must install the
following packages via your favourite package manager (e.g. `apt`,
`dnf`, etc) before running the above commands:

-   libffi-dev (or `libffi-devel` on some systems)
-   python-dev (e.g. `python3.6-dev` for Python 3.6)

## Quick Example

### Client Example

```py
import pydiscord

class MyClient(pydiscord.Client):
    async def on_ready(self):
        print('Logged on as', self.user)

    async def on_message(self, message):
        # don't respond to ourselves
        if message.author == self.user:
            return

        if message.content == 'ping':
            await message.channel.send('pong')

client = MyClient()
client.run('token')
```

### Bot Example

```py
import pydiscord
from pydiscord.ext import commands

bot = commands.Bot(command_prefix='>')

@bot.command()
async def ping(ctx):
    await ctx.send('pong')

bot.run('token')
```

You can find more examples in the examples directory.

## Links

-   [Documentation](https://pydiscord.readthedocs.io/en/latest/index.html)
-   [Official Discord Server](https://discord.gg/r3sSKJJ)

## License

Copyright (c) 2021 The PyDiscord Developers  
Copyright (c) 2015-2021 Rapptz



