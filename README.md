```sh
yarn run start:server

# ou

npm run start:server
```


[localhost:3001/repositories](http://localhost:3001/repositories)
[`db.json`](./db.json) local.

```diff
# Search
-- const SEARCH = "https://api.github.com/search/repositories";
++ const SEARCH = "http://localhost:3001/repositories";

React.useEffect(() => {
    getRepositories(query)
      .then((res) => res.json())
--      .then((data) => setItems((data &&  data.items) || []));
++      .then((data) => setItems((data &&  data[0].items) || []));
  }, [getRepositories, query]);
