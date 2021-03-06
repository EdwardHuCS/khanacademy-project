<h1>Code Editor and Tester</h1>
<br>Powered by Node.js
#Installation
Download and run npm install. After installation of dependencies, run 'node index.js' on the CLI.
By default, the server already has loaded whitelist, blacklist, and conditions running to demonstrate its
capability. To change these, go into index.js and look in the 'Post' routing code.
#Parse function
Processes and delivers results of code in a callback. Returns number of code structures in whitelist,
number of code structures in blacklist, and if code has structures identical to a given structure.
The code structure is based on the Mozilla Spider Monkey Parser api. If you want a while loop and a for loop, you would
write in the structure array [[{type:'WhileStatement', level:1}],[{type:'ForStatement' level :1}]].

1st argument: user data in a string
2nd argument: condition object that takes in a whitelist array, blacklist array, and a structure array.
3rd argument: callback to manipulate results

``` js
//takes in user input data as a string, an object that contains the properties, and a callback
//userinput: the string of user code
//conditions: {whitelist: ['ForStatement'], blacklist: ['WhileStatement'], structure:[[{type:'WhileStatement', level:1}]]
parse("while(1){if(1){}}",
{whitelist:['WhileStatement'],blacklist:['ForStatement'],structure:[[{type:'WhileStatement', level:1}]]},
function(results){
  console.log(results);
  });
//outputs 1,0,true
```
#Things to do in the future
<ul>
  <li>Bundle + minify js files and css files with webpack</li>
  <li>Make the front end look pretty</li>
  <li>Maybe a React component for displaying the Test Info</li>
  <li>Use ES6</li>
</ul>
