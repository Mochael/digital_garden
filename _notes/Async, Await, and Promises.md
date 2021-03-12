---
title: Async, Await, and Promises
tree_state: 🌱
---

Let's say we wanted to query data from our database with the following:
```
let returned_value = db.collection(collection_name).doc(doc_id).get()`
```
`returned_value` in this situation will be a `Promise`, because we don't know that the data has been queried immediately. We have to wait for it to be returned before we use the actual value we query.

Essentially if we want to access the actual data that is returned by this code instead of the promise to return the data, then we have 2 approaches:

### Approach 1 (Using .then)
```
db.collection(collection_name).doc(doc_id).get().then((doc_ref)=> { console.log(doc_ref.data())})
```
Calling `.then()` on the Promise says wait until we actual fetch the value, and then once it has been retreived print it out with `console.log`. We must put the code that uses the data in the `.then()` function, because outside the function we don't know that the data has been fetched.

### Approach 2 (Using async and await)
```
async () => {
	let doc_ref = await db.collection(collection_name).doc(doc_id).get()
	console.log(doc_ref.data())
}
```
We can define an `async` function that can run separately from the rest of our code. Within this `async` function we say `await` until we fetch the data, and then once we fetch it set it's value to `doc_ref`. Now within this `async` function we can interact with `doc_ref` however we want, but like with `.then()` we cannot access it outside the `async` function.