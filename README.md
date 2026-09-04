# Luaujs
A Open-Source Framework that transforms Luau's code in HTML code.
## Look at this Documentation if you want to use LuauJs **Outside** of Roblox Studio, or else visit https://github.com/cutehamster290-tech/LuauJS-Roblox-Studio

# Install
To install it use `npm install luaujs` if you installed NodeJs in your Computer!

## Note
Luaujs comes with some commands and the framework, anything you will type will be similiar to this: `luaujs command_name arguments`

# Commands
Remember to write `luaujs ` followed by these commands:
- status: returns a sucess message if the framework is Installed Correctly, i suggest use `luaujs status` before using any other command, so you'll be sure the Framework is Available.
- help: shows the available comamnds.
- read: asks for 1 argument, the file you want to read or the path to it, if you write `luaujs read index.html` it will read the `index.html` file in your current folder you are in the terminal, if you write instead `luaujs read main/client.js` it will search for the client.js file in main Directory and then read it. Be careful with reverse paths, so like if you are searching for the Parent path of the current path you are in right now, use `cd ..` first and then use `luaujs read file_name/path`, because my Framework is not able to read the Parent Directory's Parent etc.
- create: here comes the actual power of my Framework, this command asks 1 argument (optional) which is the name so it will be `luaujs create dir_name`, this command will import a Framework Directory inside the current file the Terminal is pointing at, once downloaded you will see 3 files inside the folder: main.lua, index.html and modules, you will be working most of the time in main.lua, since that Script will let you can write the HTML for your web page, it will be only frontend for now.
- run: this command will transform the Lua code into HTML code.

# Framework
Once you wrote `luaujs create dir_name (oprional)` you will see a new Directory named `dir_name` or Template in the folder where you called the command from the Terminal, there will be : index.html,  main.lua and a directory with some Modules you can require in the main script using `Get(module_name)`, you can also create your own module that returns something and require it! at the beginning, you'll see that the main.lua script contains some code very similiar to Luau's code, such as `require()`, `Instance.new()`, and also you can see that we use Methods like `mdText()` which i will explain more deeply later.

- `setMultiple/setSettings`: These 2 methods modify way the result appears (from Luau to HTML), if you remove them, youll see the HTML code that is 'sticky', thats because we removed the indent, the autospace and the autoformat. setMultiple asks for 2 arguments, the values you want to set and the value you want give them, we use those 2 lines only for the readbility of the result.

- `Instance.new(element: string)`: here is where we get more into Luau, we are going to use this command to create a new Instance, which is actually a HTML Element (h1, h2, div, label, ...), and generate a basic structure of it: openTag, text, closeTag, Parent, Childs and much more

- `element.mdText(text: string)`: this Method modifies the text of the HTML Element, i suggest you to use this instead of element.text = ... since mdText also adds indent and autoformat to the element's text!

- `element.appendChild(element: table)`: adds another HTML element into the element, updating some proprierties of each other parent, childs and also closetag

- `Instance.Result(element: table, Fullhtml: string?)`: prints every single item inside that element and the element itself, so you will see the div with inside the h1 with inside the label with inside the h2. write anything with a Thruthy value in the arg2 to show the entire html code (which i suggest).
- `element.setStyle(table: table)`: asks for a table and sets the element.attributes.style to that table, you can do it manually too if you prefer!

## More commands
there are also more commands, these are just some commands you can use to generate HTML using Luau, you can explore by yourself, like `element.innerHTML` or `element.mdAttributes` (to modify the attributes of an element)!

# Future Updates
- read will be able to read files backwords, so youll be able to write `../main/...`, `..` stands for 'search in the directory where i am inside' or the Parent of the current Directory.
- run will be able to transform the Lua code into HTML code.
