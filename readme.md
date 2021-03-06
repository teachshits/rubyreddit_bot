This is the stupidly simple reddit moderation bot. Its designed to be no-frills, but just work. It has very few dependencies (the snoo gem, and highline for the `reddit_auth.rb` scriptlet), doesn't use SQL or any web UI, and is run out of a config file.

# Background
This bot started out largely as a proof of concept of usage of the [snoo](/paradox460/snoo) gem, and then grew from there. It has grown organically to suit my needs across a few large subreddits, but the goal was always simplicity. I wanted something I could run with CRON, edit with vim, and check on via modlogs. This satisfies all three requirements

# Setup
This assumes you have a cursory knowledge of how ruby works, how the terminal works, and how cron works. If not, I would read up on all three until you are comfortable with them. You do not have to know ruby to make the bot run. You do have to know how to run a ruby script.

1. Clone the repo to your server. You can run this on a desktop machine, but it wont work as a bot very well
2. Install dependencies by running the `bundle` command.
3. Configure the `rubyreddit.yml` file to your liking. It is well commented, and controls the entire function of the bot
  + To get your modhash/cookie pair, use the `reddit_auth.rb` script included. Run this via `ruby reddit_auth.rb`, and follow the prompts
4. Run the bot once to make sure it works right. `ruby rubyreddit.rb`. You will get an interactive log, regardless of how you configured yaml.
5. Add the bot to your cron tab, running say, once every 5 minutes
6. Sit back and enjoy

# License
```
Copyright (c) 2013 Jeff Sandberg

MIT License

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies
of the Software, and to permit persons to whom the Software is furnished to do
so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE
```
