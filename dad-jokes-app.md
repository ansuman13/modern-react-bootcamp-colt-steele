# Section 19: Building the dad jokes app
## Conceptual things during coding

### upvoting and downvoting jokes
- `this.setState()` ~takes function~ takes function that return object also.
```js
this.setState( st => {
{jokesArray: st.jokesArray.map( (j) => j.id===id ? {...j, votes:j.votes += delta}: j )}
})

```
- second argument to `this.setState()` is a arrow function that runs after the state is set.  

- how to pass function with args from JokesList(parent) to Joke(child) component
 
 ```js
 ...
 handleVotes(id, delta){
  // does something
 }
 
 
 return (
 <Joke 
  id = {j.id},
  text = {j.text},
  upvote = { ()=> this.handleVotes(j.id, 1) }
  downvote = { () => this.handleVotes(j.id,-1) } />
 )
 
 ```
