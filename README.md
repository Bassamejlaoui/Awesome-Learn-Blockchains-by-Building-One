# The fastest way to learn how Blockchains work is to build one
You’re here because, like me, you’re psyched about the rise of Cryptocurrencies. And you want to know how Blockchains work—the fundamental technology behind them.

But understanding Blockchains isn’t easy—or at least wasn’t for me. I trudged through dense videos, followed porous tutorials, and dealt with the amplified frustration of too few examples.

I like learning by doing. It forces me to deal with the subject matter at a code level, which gets it sticking. If you do the same, at the end of this guide you’ll have a functioning Blockchain with a solid grasp of how they work.

![image](https://github.com/mejbass/Awesome-Learn-Blockchains-by-Building-One/assets/130122304/4949d748-2d81-4795-8ab3-5a4417c3ebdb)

## Before you get started…

Remember that a blockchain is an *immutable, sequential* chain of records called Blocks. They can contain transactions, files or any data you like, really. But the important thing is that they’re chained together using hashes.

If you aren’t sure what a hash is, [here’s an explanation](https://learncryptography.com/hash-functions/what-are-hash-functions).

***Who is this guide aimed at?*** You should be comfy reading and writing some basic Python, as well as have some understanding of how HTTP requests work, since we’ll be talking to our Blockchain over HTTP.

***What do I need?*** Make sure that [Python 3.6+](https://www.python.org/downloads) (along with pip) is installed. You’ll also need to install Flask and the wonderful Requests library:

```Python
pip install Flask==0.12.2 requests==2.18.4 
```
