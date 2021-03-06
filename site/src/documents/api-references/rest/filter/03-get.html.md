---

title: 'Get Single Filter'
category: 'Filter'

keywords: 'get'

---


Retrieves a single filter according to the Filter interface in the engine.


Method
------

GET `/filter/{id}`

Parameters
----------

#### Path Parameters

<table class="table table-striped">
  <tr>
    <th>Name</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>id</td>
    <td>The id of the filter to be retrieved.</td>
  </tr>
</table>


Result
------

A JSON object corresponding to the Filter interface in the engine.
Its properties are as follows:

<table class="table table-striped">
  <tr>
    <th>Name</th>
    <th>Value</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>id</td>
    <td>String</td>
    <td>The id of the filter.</td>
  </tr>
  <tr>
    <td>resourceType</td>
    <td>String</td>
    <td>The resource type of the filter, e.g., <code>Task</code>.</td>
  </tr>
  <tr>
    <td>name</td>
    <td>String</td>
    <td>The name of the filter.</td>
  </tr>
  <tr>
    <td>owner</td>
    <td>String</td>
    <td>The user id of the owner of the filter.</td>
  </tr>
  <tr>
    <td>query</td>
    <td>Object</td>
    <td>The save query of the filter as JSON object.</td>
  </tr>
  <tr>
    <td>properties</td>
    <td>Object</td>
    <td>The properties of the filter as JSON object.</td>
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
    <td>403</td>
    <td>application/json</td>
    <td>
      The authenticated user is unauthorized to read this filter.
      See the <a href="ref:#overview-introduction">Introduction</a> for the error response format.
    </td>
  </tr>
  <tr>
    <td>404</td>
    <td>application/json</td>
    <td>
      Filter with given id does not exist. See the
      <a href="ref:#overview-introduction">Introduction</a> for the error response format.
    </td>
  </tr>
</table>


Example
-------

#### Request

GET `/filter/aFilterId`

#### Response

Status 200.

```json
{
  "id": "9917d731-3cde-11e4-b704-f0def1e59da8",
  "name": "Accounting Tasks",
  "owner": null,
  "properties": {
    "color": "#3e4d2f",
    "description": "Tasks assigned to group accounting",
    "priority": 5
  },
  "query": {
    "candidateGroup": "accounting"
  },
  "resourceType": "Task"
}
```
