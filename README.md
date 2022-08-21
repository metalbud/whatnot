# Whatnot API

Very early work-in-progress asynchronous API wrapper for and documentation of the [Whatnot](https://www.whatnot.com) API.

## Download

`poetry add whatnot` *or* `pip install whatnot`

## Roadmap

See [ROADMAP.md](ROADMAP.md)

## Example

```python
import asyncio
from whatnot import Whatnot

async def main():
    async with Whatnot() as whatnot:
        whatnot.login("bob@example.com", "secret_password")

        # Get the whatnot account
        whatnot_user = await whatnot.get_user("whatnot")
        # OR
        # whatnot_user = await whatnot.get_user_by_id("21123")

        # Get user's lives
        lives = await whatnot.get_user_lives(whatnot_user.id)

        # Print out all of the lives
        for l in [live.id for live in lives]:
            print(l)


asyncio.run(main())
```

## Disclaimer

This project is unofficial and is not affiliated with or endorsed by Whatnot.
