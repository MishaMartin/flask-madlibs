# MadLibs
## Introduction
In this demo, we’ll create a simple Flask application that plays MadLibs. The Flask docs are about to become your bestest friend.

## Setup
### Make a Virtual Environment
1. In your project directory, create a virtual environment so we don’t have to install Flask (or other special libraries) system-wide:

```
% virtualenv env
New python executable in env/bin/python
Installing setuptools, pip...done.
```

2. Activate your virtual environment:

```
% source env/bin/activate
(env) %
```

(Notice what changes about your command-line prompt when you are in a virtual Python environment.)

3. Install Flask:

```
(env) $ pip3 install flask
...
Successfully installed flask Werkzeug Jinja2 itsdangerous markupsafe
Cleaning up...
```

## Running the Application
1. If you haven’t done so in this terminal window, activate your virtual environment:

```
% source env/bin/activate
(env) %
```

2. Run the application:

```
(env) % python3 madlibs.py
```

## Testing the Application
1. In your browser, visit http://localhost:5000/.

This URL is routed to the function start_here() and returns a simple string: “Hi! This is the home page.”

2. Visit http://localhost:5000/hello.

This is routed to the function say_hello() and shows a simple form that asks your name. It is rendering a template called templates/hello.html.

3. Submit the form. This will send you to http://localhost:5000/greet?person={your name here}.

## Your Task
Now that we’ve got a solid foundation for our first webapp, let’s have some fun.

1. Modify the template compliment.html to ask the person if they’d like to play a game (hint: try radio buttons). Have this form submit to the URL path /game. This form won’t work until we make the endpoint on flask, so now…

2. Make a function called show_madlib_form() and have the URL /game route to it. In this function, get the user’s response to the yes-or-no question on the “would you like to play a game?” form.

If they said no, return a rendered template, goodbye.html, that tells them goodbye and that they’ll be missed (or something else appropriate).

If they said yes, render a different template, game.html. The template game.html should have a simple form that asks for a person, a color, a noun, and an adjective. How you choose to implement those inputs is up to you, but you should feel free to mix and match. (Hint: it might be fun to try one as a drop-down menu of choices). This new form should have the action of /madlib.

3. Write a new function, show_madlib(), which is routed to by the URL path /madlib. It should render the template madlib.html, which should fill the person, color, noun, and adjective provided by the user into a MadLibs-style story.

### Some MadLibs text to get you started:
```
There once was a {{ color }} {{ noun }} sitting in the Computer Lab.
When {{ person }} went to pick it up, it burst into flames in a totally
{{ adjective }} way.
```