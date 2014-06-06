---

title: 'Process Definition View'
category: 'Cockpit'

---

<div class="row">
  <div class="col-xs-6 col-sm-6 col-md-3">
    <img data-img-thumb src="ref:asset:/assets/img/implementation-cockpit/cockpit-process-definitions-view.png" />
  </div>
  <div class="col-xs-6 col-sm-6 col-md-9">
    <p>The Process Definition View provides you with information about the definition and the status of a process. On the left hand side you can easily survey the versions of the process and how many instances of the version are running. Incidents of all running process instances are displayed together with an instances counter label in the corresponding rendered diagram. So it is easy to locate <a href="ref:#cockpit-failed-jobs">failed activities</a> in the process. Use the mouse to navigate through the diagram. By turning the mouse wheel you can zoom in out. Hold the left mouse button pressed to pan the diagram in the desired direction.</p>
    <p>In the tab <code>Process Instances</code> all running instances are listed in a tabular view. Besides information about start time, business key and state you can select an instance by ID and go down to the <a href="ref:#cockpit-process-instance-detail-view">Process Instance View</a>.<br>
    The tab <code>Called Process Definitions</code> displays the called child processes. In the column <em>Called Process Definition</em> the names of the called sub processes are listed. Click on the name to display the process in the Process Definition View. Please note that a filter called Parent is automatically set for the process so that you only see the instances that belong to the parent process. In the column <em>Activity</em> you can select the instance that is calling the child process.<br>
    The tab <code>Job Definitions</code> displays the Job Definitions that are linked to this Process Definition. You can see the name of the activity, the type of job, the configuration thereof and the state thereof. You can also suspend and re-activate the job definition (see <a href="ref:#cockpit-suspension-job-definition-suspension">Job Definition Suspension</a> for more information).</p>
  </div>
</div>

## Filter

The filter function on the left hand side of the Process Definition View allows you to find certain instances by filtering for variables, business keys, start time and date or by selecting the version of a process. Beyond that you can combine different filters as logical _AND_ relation. Filter expressions on variables must be specified as `variableName OPERATOR value` where the _operator_ my be one of the following terms `=`, `!=`, `>`, `>=`, `<`, `<=`, `like`. Apart from the `like` operator, the operator expressions do not have to be separated by spaces.
The `like` operator is for string variables only. You can use `%` as wildcard in the _value_ expression. String values must be properly enclosed in `" "`.
