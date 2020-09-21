# Section 19: Building the dad jokes app
## Conceptual things during coding

### upvoting and downvoting jokes
- `this.setState()` takes function as well as object 
```js
this.setState( st => {
{jokesArray: st.jokesArray.map( (j) => j.id===id ? {...j, votes:j.votes += delta}: j )}
})

```

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
