# myFirstApp
Simple Ionic Todo App

----------new-task.html----------

<!-- <script id="new-task.html" type="text/ng-template">

  <div class="modal">

    
    <ion-header-bar class="bar-secondary">
      <h1 class="title">New Task</h1>
      <button class="button button-clear button-positive" ng-click="closeNewTask()">Cancel</button>
    </ion-header-bar>

    
    <ion-content>

      <form ng-submit="createTask(task)">
        <div class="list">
          <label class="item item-input">
            <input type="text" placeholder="What do you need to do?" ng-model="task.title">
          </label>
        </div>
        <div class="padding">
          <button type="submit" class="button button-block button-positive">Create Task</button>
        </div>
      </form>

    </ion-content>

  </div>

</script> -->


----------ToDoController---------Content-----------



 $scope.tasks = [
    { title: 'Collect coins' },
    { title: 'Eat mushrooms'},
    { title: 'Get high enough to grab the flag' },
    { title: 'Find the Princess'}
  ];

  $ionicModal.fromTemplateUrl('new-task.html', function(modal) {
    $scope.taskModal = modal;
  }, {
    scope: $scope,
    animation: 'slide-in-up'
  });

  // Called when the form is submitted
  $scope.createTask = function(task) {
    $scope.tasks.push({
      title: task.title
    });
    $scope.taskModal.hide();
    task.title = "";
  };

  // Open our new task modal
  $scope.newTask = function() {
    $scope.taskModal.show();
  };

  // Close the new task modal
  $scope.closeNewTask = function() {
    $scope.taskModal.hide();
  };