---

title: 'Get Tasks Count (POST)'
category: 'Task'

keywords: 'post query list'

---


Get the number of tasks that fulfill the given filter.
Corresponds to the size of the result set of the [get tasks (POST)](ref:#task-get-tasks-post) method and takes the same parameters.


Method
------

POST `/task/count`


Parameters
----------

#### Request Body

A JSON object with the following properties:

<table class="table table-striped">
  <tr>
    <th>Name</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>processInstanceId</td>
    <td>Restrict to tasks that belong to process instances with the given id.</td>
  </tr>
  <tr>
    <td>processInstanceBusinessKey</td>
    <td>Restrict to tasks that belong to process instances with the given business key.</td>
  </tr>
  <tr>
    <td>processInstanceBusinessKeyLike</td>
    <td>Restrict to tasks that have a process instance business key that has the parameter value as a substring.</td>
  </tr>
  <tr>
    <td>processDefinitionId</td>
    <td>Restrict to tasks that belong to a process definition with the given id.</td>
  </tr>
  <tr>
    <td>processDefinitionKey</td>
    <td>Restrict to tasks that belong to a process definition with the given key.</td>
  </tr>
  <tr>
    <td>processDefinitionName</td>
    <td>Restrict to tasks that belong to a process definition with the given name.</td>
  </tr>
  <tr>
    <td>processDefinitionNameLike</td>
    <td>Restrict to tasks that have a process definition name that has the parameter value as a substring.</td>
  </tr>
  <tr>
    <td>executionId</td>
    <td>Restrict to tasks that belong to an execution with the given id.</td>
  </tr>
  <tr>
    <td>caseInstanceId</td>
    <td>Restrict to tasks that belong to case instances with the given id.</td>
  </tr>
  <tr>
    <td>caseInstanceBusinessKey</td>
    <td>Restrict to tasks that belong to case instances with the given business key.</td>
  </tr>
  <tr>
    <td>caseInstanceBusinessKeyLike</td>
    <td>Restrict to tasks that have a case instance business key that has the parameter value as a substring.</td>
  </tr>
  <tr>
    <td>caseDefinitionId</td>
    <td>Restrict to tasks that belong to a case definition with the given id.</td>
  </tr>
  <tr>
    <td>caseDefinitionKey</td>
    <td>Restrict to tasks that belong to a case definition with the given key.</td>
  </tr>
  <tr>
    <td>caseDefinitionName</td>
    <td>Restrict to tasks that belong to a case definition with the given name.</td>
  </tr>
  <tr>
    <td>caseDefinitionNameLike</td>
    <td>Restrict to tasks that have a case definition name that has the parameter value as a substring.</td>
  </tr>
  <tr>
    <td>caseExecutionId</td>
    <td>Restrict to tasks that belong to a case execution with the given id.</td>
  </tr>
  <tr>
    <td>activityInstanceIdIn</td>
    <td>Only include tasks which belong to one of the passed activity instance ids.</td>
  </tr>

  <tr>
    <td>assignee</td>
    <td>Restrict to tasks that the given user is assigned to.</td>
  </tr>
  <tr>
    <td>assigneeExpression</td>
    <td>Restrict to tasks that the user described by the given expression is assigned to.
        See the <a href="/guides/user-guide/#process-engine-expression-language-internal-context-functions">
        user guide</a> for more information on available functions.
    </td>
  </tr>
  <tr>
    <td>assigneeLike</td>
    <td>Restrict to tasks that have an assignee that has the parameter value as a substring.</td>
  </tr>
  <tr>
    <td>assigneeLikeExpression</td>
    <td>Restrict to tasks that have an assignee that has the parameter value described by the given
expression as a substring.
        See the <a href="/guides/user-guide/#process-engine-expression-language-internal-context-functions">
        user guide</a> for more information on available functions.
    </td>
  </tr>
  <tr>
    <td>owner</td>
    <td>Restrict to tasks that the given user owns.</td>
  </tr>
  <tr>
    <td>ownerExpression</td>
    <td>Restrict to tasks that the user described by the given expression owns.
        See the <a href="/guides/user-guide/#process-engine-expression-language-internal-context-functions">
        user guide</a> for more information on available functions.
    </td>
  </tr>
  <tr>
    <td>candidateGroup</td>
    <td>Only include tasks that are offered to the given group.</td>
  </tr>
  <tr>
    <td>candidateGroupExpression</td>
    <td>Only include tasks that are offered to the group described by the given expression.
        See the <a href="/guides/user-guide/#process-engine-expression-language-internal-context-functions">
        user guide</a> for more information on available functions.
    </td>
  </tr>
  <tr>
    <td>candidateUser</td>
    <td>Only include tasks that are offered to the given user.</td>
  </tr>
  <tr>
    <td>candidateUserExpression</td>
    <td>Only include tasks that are offered to the user described by the given expression.
        See the <a href="/guides/user-guide/#process-engine-expression-language-internal-context-functions">
        user guide</a> for more information on available functions.
    </td>
  </tr>
  <tr>
    <td>involvedUser</td>
    <td>Only include tasks that the given user is involved in.
    A user is involved in a task if an identity link exists between task and user (e.g. the user is the assignee).</td>
  </tr>
  <tr>
    <td>involvedUserExpression</td>
    <td>Only include tasks that the user described by the given expression is involved in.
        A user is involved in a task if an identity link exists between task and user (e.g. the user is the assignee).
        See the <a href="/guides/user-guide/#process-engine-expression-language-internal-context-functions">user
        guide</a> for more information on available functions.
    </td>
  </tr>
  <tr>
    <td>unassigned</td>
    <td>If set to <code>true</code>, restricts the query to all tasks that are unassigned.</td>
  </tr>

  <tr>
    <td>taskDefinitionKey</td>
    <td>Restrict to tasks that have the given key.</td>
  </tr>
  <tr>
    <td>taskDefinitionKeyLike</td>
    <td>Restrict to tasks that have a key that has the parameter value as a substring.</td>
  </tr>
  <tr>
    <td>name</td>
    <td>Restrict to tasks that have the given name.</td>
  </tr>
  <tr>
    <td>nameLike</td>
    <td>Restrict to tasks that have a name with the given parameter value as substring.</td>
  </tr>
  <tr>
    <td>description</td>
    <td>Restrict to tasks that have the given description.</td>
  </tr>
  <tr>
    <td>descriptionLike</td>
    <td>Restrict to tasks that have a description that has the parameter value as a substring.</td>
  </tr>

  <tr>
    <td>priority</td>
    <td>Restrict to tasks that have the given priority.</td>
  </tr>
  <tr>
    <td>maxPriority</td>
    <td>Restrict to tasks that have a lower or equal priority.</td>
  </tr>
  <tr>
    <td>minPriority</td>
    <td>Restrict to tasks that have a higher or equal priority.</td>
  </tr>

  <tr>
    <td>due</td>
    <td>Restrict to tasks that are due on the given date. The date must have the format <code>yyyy-MM-dd'T'HH:mm:ss</code>, e.g., <code>2013-01-23T14:42:45</code>.</td>
  </tr>
  <tr>
    <td>dueDateExpression</td>
    <td>Restrict to tasks that are due on the date described by the given expression.
        See the <a href="/guides/user-guide/#process-engine-expression-language-internal-context-functions">
        user guide</a> for more information on available functions.
        The expression must evaluate to a <code>java.util.Date</code> or <code>org.joda.time.DateTime</code> object.
    </td>
  </tr>
  <tr>
    <td>dueAfter</td>
    <td>Restrict to tasks that are due after the given date. The date must have the format <code>yyyy-MM-dd'T'HH:mm:ss</code>, e.g., <code>2013-01-23T14:42:45</code>.</td>
  </tr>
  <tr>
    <td>dueAfterExpression</td>
    <td>Restrict to tasks that are due after the date described by the given expression.
        See the <a href="/guides/user-guide/#process-engine-expression-language-internal-context-functions">
        user guide</a> for more information on available functions.
        The expression must evaluate to a <code>java.util.Date</code> or <code>org.joda.time.DateTime</code> object.
    </td>
  </tr>
  <tr>
    <td>dueBefore</td>
    <td>Restrict to tasks that are due before the given date. The date must have the format <code>yyyy-MM-dd'T'HH:mm:ss</code>, e.g., <code>2013-01-23T14:42:45</code>.</td>
  </tr>
  <tr>
    <td>dueBeforeExpression</td>
    <td>Restrict to tasks that are due before the date described by the given expression.
        See the <a href="/guides/user-guide/#process-engine-expression-language-internal-context-functions">
        user guide</a> for more information on available functions.
        The expression must evaluate to a <code>java.util.Date</code> or <code>org.joda.time.DateTime</code> object.
    </td>
  </tr>
  <tr>
    <td>followUp</td>
    <td>Restrict to tasks that have a followUp date on the given date. The date must have the format <code>yyyy-MM-dd'T'HH:mm:ss</code>, e.g., <code>2013-01-23T14:42:45</code>.</td>
  </tr>
  <tr>
    <td>followUpDateExpression</td>
    <td>Restrict to tasks that have a followUp date on the date described by the given expression.
        See the <a href="/guides/user-guide/#process-engine-expression-language-internal-context-functions">
        user guide</a> for more information on available functions.
        The expression must evaluate to a <code>java.util.Date</code> or <code>org.joda.time.DateTime</code> object.
    </td>
  </tr>
  <tr>
    <td>followUpAfter</td>
    <td>Restrict to tasks that have a followUp date after the given date. The date must have the format <code>yyyy-MM-dd'T'HH:mm:ss</code>, e.g., <code>2013-01-23T14:42:45</code>.</td>
  </tr>
  <tr>
    <td>followUpAfterExpression</td>
    <td>Restrict to tasks that have a followUp date after the date described by the given expression.
        See the <a href="/guides/user-guide/#process-engine-expression-language-internal-context-functions">
        user guide</a> for more information on available functions.
        The expression must evaluate to a <code>java.util.Date</code> or <code>org.joda.time.DateTime</code> object.
    </td>
  </tr>
  <tr>
    <td>followUpBefore</td>
    <td>Restrict to tasks that have a followUp date before the given date. The date must have the format <code>yyyy-MM-dd'T'HH:mm:ss</code>, e.g., <code>2013-01-23T14:42:45</code>.</td>
  </tr>
  <tr>
    <td>followUpBeforeExpression</td>
    <td>Restrict to tasks that have a followUp date before the date described by the given expression.
        See the <a href="/guides/user-guide/#process-engine-expression-language-internal-context-functions">
        user guide</a> for more information on available functions.
        The expression must evaluate to a <code>java.util.Date</code> or <code>org.joda.time.DateTime</code> object.
    </td>
  </tr>
  <tr>
    <td>created</td>
    <td>Restrict to tasks that were created on the given date. The date must have the format <code>yyyy-MM-dd'T'HH:mm:ss</code>, e.g., <code>2013-01-23T14:42:45</code>.</td>
  </tr>
  <tr>
    <td>createdOnExpression</td>
    <td>Restrict to tasks that were created on the date described by the given expression.
        See the <a href="/guides/user-guide/#process-engine-expression-language-internal-context-functions">
        user guide</a> for more information on available functions.
        The expression must evaluate to a <code>java.util.Date</code> or <code>org.joda.time.DateTime</code> object.
    </td>
  </tr>
  <tr>
    <td>createdAfter</td>
    <td>Restrict to tasks that were created after the given date. The date must have the format <code>yyyy-MM-dd'T'HH:mm:ss</code>, e.g., <code>2013-01-23T14:42:45</code>.</td>
  </tr>
  <tr>
    <td>createdAfterExpression</td>
    <td>Restrict to tasks that were created after the date described by the given expression.
        See the <a href="/guides/user-guide/#process-engine-expression-language-internal-context-functions">
        user guide</a> for more information on available functions.
        The expression must evaluate to a <code>java.util.Date</code> or <code>org.joda.time.DateTime</code> object.
    </td>
  </tr>
  <tr>
    <td>createdBefore</td>
    <td>Restrict to tasks that were created before the given date. The date must have the format <code>yyyy-MM-dd'T'HH:mm:ss</code>, e.g., <code>2013-01-23T14:42:45</code>.</td>
  </tr>
  <tr>
    <td>createdBeforeExpression</td>
    <td>Restrict to tasks that were created before the date described by the given expression.
        See the <a href="/guides/user-guide/#process-engine-expression-language-internal-context-functions">
        user guide</a> for more information on available functions.
        The expression must evaluate to a <code>java.util.Date</code> or <code>org.joda.time.DateTime</code> object.
    </td>
  </tr>
  <tr>
    <td>delegationState</td>
    <td>Restrict to tasks that are in the given delegation state. Valid values are <code>PENDING</code> and <code>RESOLVED</code>.</td>
  </tr>
  <tr>
    <td>candidateGroups</td>
    <td>Restrict to tasks that are offered to any of the given candidate groups. Takes a JSON array of group names, so for example <code>["developers", "support", "sales"]</code>.</td>
  </tr>
  <tr>
    <td>candidateGroupsExpression</td>
    <td>Restrict to tasks that are offered to any of the candidate groups described by the given expression.
        See the <a href="/guides/user-guide/#process-engine-expression-language-internal-context-functions">user
        guide</a> for more information on available functions.
        The expression must evaluate to <code>java.util.List</code> of Strings.
    </td>
  </tr>
  <tr>
    <td>active</td>
    <td>Only include active tasks. Values may be <code>true</code> or <code>false</code>.</td>
  </tr>
  <tr>
    <td>suspended</td>
    <td>Only include suspended tasks. Values may be <code>true</code> or <code>false</code>.</td>
  </tr>
  <tr>
    <td>taskVariables</td>
    <td>A JSON array to only include tasks that have variables with certain values. <br/>

    The array consists of JSON objects with three properties <code>name</code>, <code>operator</code> and <code>value</code>.
    <code>name</code> is the variable name, <code>operator</code> is the comparison operator to be used and <code>value</code> the variable value.<br/>
    <code>value</code> may be of type <code>String</code>, <code>Number</code> or <code>Boolean</code>.<br/>
    <br/>
    Valid operator values are: <code>eq</code> - equal to; <code>neq</code> - not equal to; <code>gt</code> - greater than;
    <code>gteq</code> - greater than or equal to; <code>lt</code> - lower than; <code>lteq</code> - lower than or equal to;
    <code>like</code>.<br/>
    </td>
  </tr>
  <tr>
    <td>processVariables</td>
    <td>A JSON array to only include tasks that belong to a process instance with variables with certain values.<br/>
    The array consists of JSON objects with three properties <code>name</code>, <code>operator</code> and <code>value</code>.
    <code>name</code> is the variable name, <code>operator</code> is the comparison operator to be used and <code>value</code> the variable value.<br/>
    <code>value</code> may be of type <code>String</code>, <code>Number</code> or <code>Boolean</code>.<br/>
    <br/>
    Valid operator values are: <code>eq</code> - equal to; <code>neq</code> - not equal to; <code>gt</code> - greater than;
    <code>gteq</code> - greater than or equal to; <code>lt</code> - lower than; <code>lteq</code> - lower than or equal to;
    <code>like</code>.<br/>
    </td>
  </tr>
  <tr>
    <td>caseInstanceVariables</td>
    <td>Only include tasks that belong to case instances that have variables with certain values.
    Variable filtering expressions are comma-separated and are structured as follows:<br/>
    A valid parameter value has the form <code>key_operator_value</code>.
    <code>key</code> is the variable name, <code>operator</code> is the comparison operator to be used and <code>value</code> the variable value.<br/>
    <strong>Note:</strong> Values are always treated as <code>String</code> objects on server side.<br/>
    <br/>
    Valid operator values are: <code>eq</code> - equal to; <code>neq</code> - not equal to; <code>gt</code> - greater than;
    <code>gteq</code> - greater than or equal to; <code>lt</code> - lower than; <code>lteq</code> - lower than or equal to;
    <code>like</code>.<br/>
    <code>key</code> and <code>value</code> may not contain underscore or comma characters.
    </td>
  </tr>
</table>


Result
------

A JSON object with a single count property.

<table class="table table-striped">
  <tr>
    <th>Name</th>
    <th>Value</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>count</td>
    <td>Number</td>
    <td>The number of tasks that fulfill the query criteria.</td>
  </tr>
</table>


Response codes
--------------

<table class="table table-striped">
  <tr>
    <th>Code</th>
    <th>Media type</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>200</td>
    <td>application/json</td>
    <td>Request successful.</td>
  </tr>
  <tr>
    <td>400</td>
    <td>application/json</td>
    <td>Returned if some of the query parameters are invalid, for example if a <code>sortOrder</code> parameter is supplied, but no <code>sortBy</code>, or if an invalid operator for variable comparison is used. See the <a href="ref:#overview-introduction">Introduction</a> for the error response format.</td>
  </tr>
</table>


Example
-------

#### Request

POST `/task/count`

Request body:

    {"taskVariables":
        [{"name": "varName",
        "value": "varValue",
        "operator": "eq"
        },
        {"name": "anotherVarName",
        "value": 30,
        "operator": "neq"}],
    "priority":10}

#### Response

    {"count":1}
