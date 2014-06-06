---

title: 'User Assignment'
category: 'Tasklist'

---

<div class="row">
  <div class="col-xs-6 col-sm-6 col-md-3">
    <img data-img-thumb src="ref:asset:/assets/img/implementation-tasklist/tasklist-task-forms-eclipse.png" />
  </div>
  <div class="col-xs-6 col-sm-6 col-md-9">
      <p>Tasks can be directly assigned to a user, to a candidate group (group) or to a candidate list (multiple users). Compared to the direct assignment of tasks, the tasks of candidate groups or candidate lists are not yet assigned. They must be claimed by a user who is part of the list or belongs to the group. Depending on this affiliation the Tasklist displays tasks in different <a href="ref:#tasklist-human-workflow-management-user-and-group-task-overview">folders</a>.</p>
      <p>In the properties panel in your <a href="http://camunda.org/bpmn/tool/">camunda Modeler</a> you can configure all relevant attributes.</p>
  </div>  
</div>

To determine which user or user group is able to work on a task you can set the following extension attributes for your [User Task](ref:/api-references/bpmn20/#tasks-user-task):

* Assignee: directly assign a task to a user
  
  ```xml
  <userTask id="theTask" name="my task" camunda:assignee="John" ></userTask>
  ```

* Candidate User: makes a user a candidate for a task
  ```xml
  <userTask id="theTask" name="my task" camunda:candidateUsers="John, Mary" ></userTask>
  ```

* Candidate Group: makes a user group a candidate for a task
  ```xml
  <userTask id="theTask" name="my task" camunda:candidateGroups="management, accountancy" ></userTask>
  ```

You can define the Candidate User and the Candidate Group on the same task. Find more detailed information regarding extension attributes for [User Tasks here](ref:/api-references/bpmn20/#tasks-user-task).