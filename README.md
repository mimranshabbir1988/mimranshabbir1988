- š Hi, Iām @mimranshabbir1988
- š Iām interested in ...
- š± Iām currently learning ...
- šļø Iām looking to collaborate on ...
- š« How to reach me ...

<!---
mimranshabbir1988/mimranshabbir1988 is a āØ special āØ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.

--->
/# Fetching Data using Fake / Rest API in React JS

import "./App.css";
import { useEffect, useState } from 'react';


function App() {
  
  const [todos, setTodos] = useState([]);

  useEffect(() => {
    fetch('https://jsonplaceholder.typicode.com/todos')
    .then(response => response.json())
    .then(json => {setTodos(json)})
    .catch(err => console.log("Error in Loading..."))
  }, [])

  if (!todos.length)
    return (
      <div class="spinner-grow text-danger" role="status">
        <span class="sr-only"></span>
      </div>
    )
  return (
    <>
      <ol>
          {
            todos.map(a => 
                  <li key={a.id} style={a.completed ? {color: 'red'} : {color: 'green'}}> Title = {a.title}</li>     
            )
          }
      </ol>
    </>
  );
}

export default App;

