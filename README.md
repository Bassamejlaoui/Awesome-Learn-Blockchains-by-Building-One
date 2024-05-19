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

Oh, you’ll also need an HTTP Client, like [Postman](https://www.getpostman.com/) or cURL. But anything will do.

***Where’s the final code?*** The source code is available [here](https://github.com/dvf/blockchain?).

# Step 1: Building a Blockchain

Open up your favourite text editor or IDE, personally I ❤️ [PyCharm](https://www.jetbrains.com/pycharm). Create a new file, called
```blockchain.py```

We’ll only use a single file, but if you get lost, you can always refer to [the source code](https://github.com/dvf/blockchain).

### Representing a Blockchain
We’ll create a ```Blockchain```

class whose constructor creates an initial empty list (to store our blockchain), and another to store transactions. Here’s the blueprint for our class:

```python
class Blockchain(object):
    def __init__(self):
        self.chain = []
        self.current_transactions = []
        
    def new_block(self):
        # Creates a new Block and adds it to the chain
        pass
    
    def new_transaction(self):
        # Adds a new transaction to the list of transactions
        pass
    
    @staticmethod
    def hash(block):
        # Hashes a Block
        pass

    @property
    def last_block(self):
        # Returns the last Block in the chain
        pass
```


*(Blueprint of our Blockchain Class)*

Our

```Blockchain```

class is responsible for managing the chain. It will store transactions and have some helper methods for adding new blocks to the chain. Let’s start fleshing out some methods.

### What does a Block look like?

Each Block has an index, a timestamp (in Unix time), a list of transactions, a proof (more on that later), and the hash of the previous Block.

Here’s an example of what a single Block looks like:

``` python
block = {
    'index': 1,
    'timestamp': 1506057125.900785,
    'transactions': [
        {
            'sender': "8527147fe1f5426f9dd545de4b27ee00",
            'recipient': "a77f5cdfa2934df3954a5c7c7da5df1f",
            'amount': 5,
        }
    ],
    'proof': 324984774000,
    'previous_hash': "2cf24dba5fb0a30e26e83b2ac5b9e29e1b161e5c1fa7425e73043362938b9824"
}
```
