##Peer evaluation tool

###What are we building?

`This is a peer-evaluation tool to allow students involved in VIP programs around the world to evaluate their team-members.  This feedback will allow administrators and mentors to find problems in their teams, assess students performance, and monitor growth for returning students.`

###Who uses this software?

`University VIP director (or their IT staff) must be able to install the program using one html file or one folder and follow a few simple instructions to set up their “server-side” (firebase)`

`A VIP team mentor (research faculty member) must be able to upload a roster of students from their team (csv, space separated, excel?) and view the results from their team.`

`A VIP team member must be able to quickly evaluate each of their teammates`

# Documentation

# controllerjs

## authCtrl

* **$scope.signIn**: sign in with Google

* **$scope.authObj.$onAuthStateChanged** : a watcher for auth state. Set the name as **$scope.displayName** and pic as **$scope.userPic**

* * * * *

## questionsGenerateCtrl

* **$scope.addOption**：get the length of current array and add one more option to it
* * $scope.saveQuiz
  * $scope.saveLinearScale
  * $scope.saveParagraph
  * $scope.saveMultichoice
  * $scope.saveDropdown
  * $scope.saveCheckbox：save each type of data into the firebase
  

* * * * *
## membersManagementCtrl

* $scope.members：array of the (key,value) pair of members where key is the unique ID and value is an object containing member's infomation

* $scope.addMemeber: control the show of the 'add member' button. And the input data would be set to default every time the button is clicked.
* $scope.deleteMember: takes 2 parameters as (team, unique_id) to delete a member in firebase.

# servicejs


###  firebaseService

* * * * *
* **retrieveData**: `firebaseService.retrieveData(ref)` will return an data array of the reference

* **pushData**:`firebaseService.pushData(ref, obj)` will push the object under the reference

* **pushDataWithUniqueID**:`firebaseService.pushDataWithUniqueID(ref, obj)` will push the object under the reference with a unique ID generated by firebase


# directive.js
* **Scope variable assignment**
  * "=": data's double binding
  * "@": variable assignment
  * "&": function assignment

* **restrict: 'E'** : the directive can only be used as an element, for example: `<linear-scale></linear-scale>`

# pages

## questionsGenerate.html
* Add quiz part:
    *  quizzesID: quiz name, such as quiz1, quiz2, midterm,etc
    *  5 types of questions: linearScale, paragraph, multiple choices, dropdown, check box
* Quiz content part:
    * questionId: unique ID created by firebase.

* * * * *

## membersManagement.html
* nothing special

## templates
* **checkBox.html**: `inputshow`: when this value is true, the directive is in the *edit mode*. Options can be added and defined
* **dropdown.html**: almost same as checkBox
* **linearScale.html**: set `name="{{name}}"` so that only 1 radio button will be chosen
* **multiChoices.html**: same
* **paragraph.html**: same

