# Websites and what you need to know

## Web Workers

### what is it?

Whilst a website is running a script (like starting an animation, requesting the information you've asked for etc.) there is a separate and *independent* `JavaScript ` that allows you to continue to use the website, so you can proceed to click, scroll, change page,etc.

there are API's and different version numbers for different browsers, this list tells you what they are:
* chrome - 4.0
* IE - 10.0
* FireFox - 3.5
* Safari - 4.0
* Opera 11.5

you can check if a browser supports a web worker with the following code

```javascript
if (typeof(Worker) !== "undefined") {
    // Yes! Web worker support!
    // Some code.....
} else {
    // Sorry! No Web Worker support..
}
```

### creating a web worker

web workers are written in `JavaScript` and are relitively easy to understand. You usually save it in it's own `JS File` so nothing can interfere with it, here is a script that counts:

```javascript
var i = 0;

function timedCount() {
    i = i + 1;
    postMessage(i);
    setTimeout("timedCount()",500);
}

timedCount();
```

the **`postMessage()`** method shows you that whilst you are on the website, the script is still running in the background. `WebWorkers` are used for more CPU intensive tasks, but this illustrates the point.

#### web worker objects

You call the script from the `HTML` page with `JavaScript`. The following code you place into the `HTML` file and it will check if a `web worker` already exists, and if it doesn't then it will call the one you created in the other file:

```javascript
if (typeof(w) == "undefined") {
    w = new Worker("demo_workers.js");
}
```

now you can receive and send messages from the `web worker`. add an `event listener` to the `web worker` that let's the `event listener` execute whenever it hears the `web worker` post a message:

```javascript
w.onmessage = function(event){
    document.getElementById("result").innerHTML = event.data;
};
```

the data saved from the web worker is stored in `event.data`

#### Terminate and Reuse web workers

`Event Listeners` will listen for `events` even after the `sctipt` has finished, so be sure to terminate your scripts:

```javascript
w.terminate();
```

However, if you set the variable `w` to `undefined`, then you can reuse the same `web worker` :

```javascript
w = undefined;
```

**Here's a full web worker example for you to analyze:**

```html
<!DOCTYPE html>
<html>
<body>

<p>Count numbers: <output id="result"></output></p>
<button onclick="startWorker()">Start Worker</button> 
<button onclick="stopWorker()">Stop Worker</button>

<script>
var w;

function startWorker() {
    if(typeof(Worker) !== "undefined") {
        if(typeof(w) == "undefined") {
            w = new Worker("demo_workers.js");
        }
        w.onmessage = function(event) {
            document.getElementById("result").innerHTML = event.data;
        };
    } else {
        document.getElementById("result").innerHTML = "Sorry! No Web Worker support.";
    }
}

function stopWorker() { 
    w.terminate();
    w = undefined;
}
</script>

</body>
</html>
```

