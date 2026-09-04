# Luaujs
An Open-Source Framework that transforms Luau code into HTML code.
## Look at this Documentation if you want to use LuauJs **Outside** of Roblox Studio, or else visit https://github.com/cutehamster290-tech/LuauJS-Roblox-Studio

# Install
To install it use `npm install luaujs` if you have NodeJs installed on your computer!

## Note
Luaujs comes with some commands and the framework itself; anything you type will look similar to this: `luaujs command_name arguments`

# Commands
Remember to write `luaujs ` followed by these commands:
- status: returns a success message if the framework is installed correctly. I suggest using `luaujs status` before using any other command, so you'll be sure the framework is available.
- help: shows the available commands.
- read: asks for 1 argument, the file you want to read or the path to it. If you write `luaujs read index.html` it will read the `index.html` file in the folder you're currently in, in the terminal. If you write instead `luaujs read main/client.js` it will search for the `client.js` file inside the `main` directory and then read it. Be careful with reverse paths: if you're trying to reach the parent of the current directory, use `cd ..` first and then `luaujs read file_name/path`, because the framework can't read the parent of the parent directory, and so on.
- create: here comes the actual power of the framework. This command asks for 1 optional argument, the name, so it will look like `luaujs create dir_name`. This command imports a framework directory inside the folder the terminal is currently pointing at. Once downloaded, you'll see 3 files inside the folder: `main.lua`, `index.html`, and `modules`. You'll be working mostly in `main.lua`, since that script is where you write the HTML for your web page — for now, it's frontend only.

# Framework
Once you've written `luaujs create dir_name` (the name is optional), you'll see a new directory named `dir_name`, or `Template` if you didn't name it, in the folder where you called the command from the terminal. Inside it there will be: `index.html`, `main.lua`, and a directory with some modules you can require in the main script using `Get(module_name)` — you can also create your own module that returns something and require it that way! At the beginning, you'll see that `main.lua` contains some code very similar to regular Luau code, such as `require()` and `Instance.new()`, and you'll also notice methods like `mdText()`, which I'll explain more deeply later.

As soon as you run `main.lua`, the framework converts that Luau code into HTML — there's no separate command for it, running the file is enough.

- `setMultiple/setSettings`: these 2 methods change the way the result appears (from Luau to HTML). If you remove them, you'll see HTML code that's all "stuck together," because we removed the indentation, spacing, and formatting. `setMultiple` asks for 2 arguments — the values you want to set, and the value you want to give them — we use these 2 lines purely for the readability of the result.

- `Instance.new(element: string)`: here we get more into Luau. We use this to create a new Instance, which is actually an HTML element (h1, h2, div, label, ...), generating a basic structure for it: opening tag, text, closing tag, parent, children, and much more.

- `element.mdText(text: string)`: this method sets the text of the HTML element. I suggest using this instead of `element.text = ...`, since `mdText` also adds indentation and formatting to the element's text!

- `element.appendChild(element: table)`: adds another HTML element as a child of this element, updating some properties on both — parent, children, and also the closing tag.

- `Instance.Result(element: table, Fullhtml: string?)`: prints every single item inside that element, and the element itself, so you'll see the div with the h1 inside it, with the label inside that, with the h2 inside that. Pass a truthy value as the second argument to show the entire HTML code (which I recommend).

- `element.setStyle(table: table)`: takes a table and sets `element.attributes.style` to that table — you can also do this manually if you prefer!

## More commands
There are also more commands — these are just a few you can use to generate HTML using Luau. Feel free to explore on your own, like `element.innerHTML` or `element.mdAttributes` (to modify an element's attributes)!

# Future Updates
- JavaScript code inside the Framework
