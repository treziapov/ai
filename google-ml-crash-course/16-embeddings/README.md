Collaborative filtering
- making predictions about the interests of a user based on interests of many other users
- example: movie recommendations
- need a method to determine which movies are similar to each other (achived by embedding)

Embedding
- mapping examples into d-dimensional space (embedding space)
- when learning embeddings, individiual dimensions are not learned with names
    - latent dimension: a feature that is not explicit in the data but inferred from it
- what's meaninful are the distancdes between the examples in the embedding space rather than inidividual values

Categorical data
- input features that represent one or more discrete items from a finite set of choices
    e.g. set of movies a user has watched
- most efficiently represented via sparse tensors

Movie recommendation example
- user movie-viewing history can be represented as a sparse tensor i.e. each user only watcdhes a small fraction of all possible movies
- words, sentences, and documents can also be represented as sparse vectors
- need a way to represent each sparce vector as a vector of numbers so that semantically similar items have similar distances in the vector space
- simple way: use a giant input layer with a node for every word in the vocabulary (or all words that appear in data)
- sparse representations can make it hard for a model to learn effectively

Size of network
- M - words in your vocabulary
- N - nodes in the first layer of the network above the input
- you have MxN weights to train that layer
- Large number of weights causes further problems:
    1) amount of data - the more weights, the more data you need to train effectively
    2) ammount of computation - the more weights, the more computation required to train and use the model (easy to exceed hardware capabilities)

Lack of meaningful relations between vectors
- with RGB cahnnels in an image classifier, it makes sense to talk about 'close' values i.e. reddish blue and pure blue, both semantically and geometrically
- but a vector with a 1 at index 1247 for "horse" is not any closer to a vector with a 1 at index 50430 for "antelope" than it is to a vector with a 1 at index 238 for "tv"

Solution: Embeddings
- translate large sparse vectors into a lower-dimensional space that preserves semantic relationships

