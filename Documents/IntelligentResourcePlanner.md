# Intelligent Resource Planner


##Requirements
* must list all resources by name
* could sort resources by *type*, *Location*, *Skill Set*, *Availability*

**Must** display Gantt chart with projects forecast
**Must** be able to add projects with *timescales*, *location*, *type*, *required skill set*

**Must** be a web app
**Must** be able to add/remove resources
`should` be able to procide MI reports
`should` be able to produce predicted + actual billing reports
*could* be a sharepoint application

---

# Return to EMMA

the EMMA project that i first worked on when joining (now) IDS has a lot of useful tricks and code that could be easily re-used to help make this project a reality. The project asks for a `gantt chart` to be used as the homepage of the application, as well the standard login page, employee details and other things like that. 
The EMMA code that was I worked on has some `JavaScript` code in it that populates the screen with what a database has been filled with. 

So... here is the code.

```javascript
function getSets() {
    var sets = getSource();
    var questionSets = JSON.parse(sets);
    var element = "";
    for (var i = 0; i < questionSets.QuestionSet.length; i++) {
      element = element + "<div class='container'> <a href='" + "loadQuestionnaire?ID=" + questionSets.QuestionSetID[i] +"'>" + "<h1>" + questionSets.QuestionSet[i] + "</h1></a></div>";
    }
  document.getElementById("selections").innerHTML = element;
}
```
```javascript
function getSource() {
  var sets;
  var xhttp = new XMLHttpRequest;
  xhttp.onreadystatechange = function() {
    if(this.readyState == 4 && this.status == 200) {
      sets = this.responseText;
    }
  }
  xhttp.open("GET", "/fetchQuestionSets", false);
  xhttp.send();
  return sets;    
}
```

Here are two blocks of Javascript. The first block formats the data that is requested and then formats the `html` around how much data there is, then pushed the returned product into the `html` document itself.
The second block is the code that requests the data, using a `GET` request, it calls for the data within the daatabase, and then stores the information ready for the `getSets()` funciton to inject onto the HTML page.


---

# [Kanban](https://intelligent-testing.visualstudio.com/Intelligent%20Resource%20Planner/_backlogs/board/Stories)

the [Kanban](<https://intelligent-testing.visualstudio.com/Intelligent%20Resource%20Planner/_backlogs/board/Stories>) is based on visual studio and will be set out exactly the same as EMMA.















---






















