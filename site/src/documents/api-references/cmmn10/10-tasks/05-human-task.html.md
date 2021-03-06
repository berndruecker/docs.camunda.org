---

title: 'Human Task'
category: 'Tasks'

keywords: 'human task due date assignment custom extensions'

---

A `human task` is used to model work that needs to be done by a human actor.

<img class="img-responsive" src="ref:asset:/assets/cmmn/human-task.png"/>

A human task is defined in XML as follows:

```xml
<humanTask id="theHumanTask" name="A Human Task" />
```

An `ENABLED` human task can be started manually using the `CaseService` as follows:

```java
caseService
  .withCaseExecution("aCaseExecutionId")
  .manualStart();
```

When the defined human task becomes <code>ACTIVE</code>, a new task is created in the task list of the user(s) or group(s) assigned to that task.

If the work associated with the human task is completed, it is possible to complete the human task manually using the `CaseService` as follows:

```java
caseService
  .withCaseExecution("aCaseExecutionId")
  .complete();
```

This will complete the created task as well.

Instead of using the `CaseService` it is also possible to use the `TaskService` to complete a human task:

```java
taskService.complete("aTaskId");
```

In that case the associated human task will be completed as well.

## Description

A human task can have also a description. In fact, any CMMN 1.0 element can have a description. A description is defined by adding the description attribute.

```xml
<humanTask id="theTask" name="Schedule meeting" description="Schedule an engineering meeting for next week with the new hire" />
```

The description text can be retrieved from the task in the standard Java way:

```java
task.getDescription();
```

## Due Date

Each task has a field indicating the due date of that task. The Query API can be used to query for tasks that are due on, before or after a certain date.

There is an activity extension which allows you to specify an expression in your task-definition to set the initial due date of a task when it is created. The expression should always resolve to a java.util.Date, java.util.String ([ISO8601](http://en.wikipedia.org/wiki/ISO_8601) formatted) or null. When using ISO8601 formatted Strings, you may either specify an exact point in time or a time period relative to the time the task is created.

```xml
<humanTask id="theTask" name="Important task" camunda:dueDate="${dateVariable}"/>
```

The due date of a task can also be altered using the TaskService or in TaskListeners using the passed DelegateTask.

## Follow Up Date

Each task has a field indicating the follow up date of that task. The Query API can be used to query for tasks that need to be followed up on, before or after a certain date.

There is an activity extension which allows you to specify an expression in your task-definition to set the initial follow up date of a task when it is created. The expression should always resolve to a java.util.Date, java.util.String ([ISO8601](http://en.wikipedia.org/wiki/ISO_8601) formatted) or null. When using ISO8601 formatted Strings, you may either specify an exact point in time or a time period relative to the time the task is created.

```xml
<humanTask id="theTask" name="Important task" camunda:followUpDate="${dateVariable}"/>
```

## User Assignment

A human task can be directly assigned to a user. This is done by using the attribute <code>performerRef</code> on a human task element. The defined <code>performerRef</code> attribute references an existing role. Such a role definition needs a name that actually defines the user.

```xml
<case ... >
  ...
  <humanTask id="theTask" name='important task' perfomerRef="aCaseRole" />
  <caseRoles id="aCaseRole" name="kermit" />

</case>
```

Only one user can be assigned to the task as a performer. In the engine terminology, this user is called the assignee. Tasks that have an assignee are not visible in the task lists of other users and can be found in the so-called personal task list of the assignee instead.

Tasks directly assigned to users can be retrieved through the TaskService as follows:

```java
List<Task> tasks = taskService.createTaskQuery().taskAssignee("kermit").list();
```

## User Assignment using custom extensions

It is clear that user and group assignments are quite cumbersome for use cases where the assignment is more complicated. To avoid these complexities, custom extensions on the human task are possible.

* `assignee` attribute: this custom extension allows direct assignment of a human task to a given user.

  ```xml
  <humanTask id="theTask" name="my task" camunda:assignee="kermit" />
  ```

  This is exactly the same as using a <code>perfomerRef</code> construct as defined [above](ref:#tasks-human-task-user-assignment).
* `candidateUsers` attribute: this custom extension allows you to make a user a candidate for a task.

  ```xml
  <humanTask id="theTask" name="my task" camunda:candidateUsers="kermit, gonzo" />
  ```

* `candidateGroups` attribute: this custom extension allows you to make a group a candidate for a task.

  ```xml
  <humanTask id="theTask" name="my task" camunda:candidateGroups="management, accountancy" />
  ```

* `candidateUsers` and `candidateGroups` can both be defined for the same human task.

Note: Although the camunda engine provides an identity management component, which is exposed through the IdentityService, it does not check whether a provided user is known by the identity component. This allows integration of the engine with existing identity management solutions when it is embedded into an application.

When using Spring or CDI it is possible to use the custom assignment attributes as described in the section above and delegate to a bean with an expression that listens to task create events. In the following example, the assignee will be set by calling the <code>findManagerOfEmployee()</code> on the <code>ldapService</code> Spring/CDI bean. The <code>emp</code> parameter that is passed is a variable.

```xml
<humanTask id="task" name="My Task" camunda:assignee="${ldapService.findManagerForEmployee(emp)}"/>
```

This also works in a similar way for candidate users and groups:

```xml
<humanTask id="task" name="My Task" camunda:candidateUsers="${ldapService.findAllSales()}"/>
```

Note that this will only work if the return type of the invoked methods is String or Collection<String> (for candidate users and groups):

```java
public class FakeLdapService {

  public String findManagerForEmployee(String employee) {
    return "Kermit The Frog";
  }

  public List<String> findAllSales() {
    return Arrays.asList("kermit", "gonzo", "fozzie");
  }
}
```

## camunda Extensions

<table class="table table-striped">
  <tr>
    <th>Attributes</th>
    <td>
      <a href="ref:#custom-extensions-camunda-extension-attributes-camundaassignee">camunda:assignee</a>,
      <a href="ref:#custom-extensions-camunda-extension-attributes-camundacandidategroups">camunda:candidateGroups</a>,
      <a href="ref:#custom-extensions-camunda-extension-attributes-camundacandidateusers">camunda:candidateUsers</a>,
      <a href="ref:#custom-extensions-camunda-extension-attributes-camundaduedate">camunda:dueDate</a>,
      <a href="ref:#custom-extensions-camunda-extension-attributes-camundaformkey">camunda:formKey</a>,
      <a href="ref:#custom-extensions-camunda-extension-attributes-camundapriority">camunda:priority</a>
    </td>
  </tr>
  <tr>
    <th>Constraints</th>
    <td>
      The attribute <code>camunda:assignee</code> cannot be used simultaneously with the <code>perfomerRef</code>
      attribute on a human task element.
    </td>
  </tr>
</table>
