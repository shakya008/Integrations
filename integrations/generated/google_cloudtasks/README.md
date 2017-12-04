# @datafire/google_cloudtasks

Client library for Cloud Tasks

## Installation and Usage
```bash
npm install --save datafire @datafire/google_cloudtasks
```

```js
let datafire = require('datafire');
let google_cloudtasks = require('@datafire/google_cloudtasks').create({
  access_token: "",
  refresh_token: "",
  client_id: "",
  client_secret: "",
  redirect_uri: "",
});

google_cloudtasks.projects.locations.queues.tasks.delete({}).then(data => {
  console.log(data);
})
```

## Description
Manages the execution of large numbers of distributed requests. Cloud Tasks is in Alpha.

## Actions
### oauthCallback
Exchange the code passed to your redirect URI for an access_token


```js
google_cloudtasks.oauthCallback({
  "code": ""
}, context)
```

#### Parameters
* code (string) **required**

### oauthRefresh
Exchange a refresh_token for an access_token


```js
google_cloudtasks.oauthRefresh(null, context)
```

#### Parameters
*This action has no parameters*

### projects.locations.queues.tasks.delete
Deletes a task.

A task can be deleted if it is scheduled or dispatched. A task
cannot be deleted if it has completed successfully or permanently
failed.


```js
google_cloudtasks.projects.locations.queues.tasks.delete({
  "name": ""
}, context)
```

#### Parameters
* name (string) **required** - Required.
* $.xgafv (string) - V1 error format.
* access_token (string) - OAuth access token.
* alt (string) - Data format for response.
* bearer_token (string) - OAuth bearer token.
* callback (string) - JSONP
* fields (string) - Selector specifying which fields to include in a partial response.
* key (string) - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* oauth_token (string) - OAuth 2.0 token for the current user.
* pp (boolean) - Pretty-print response.
* prettyPrint (boolean) - Returns response with indentations and line breaks.
* quotaUser (string) - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* uploadType (string) - Legacy upload protocol for media (e.g. "media", "multipart").
* upload_protocol (string) - Upload protocol for media (e.g. "raw", "multipart").

### projects.locations.queues.tasks.get
Gets a task.


```js
google_cloudtasks.projects.locations.queues.tasks.get({
  "name": ""
}, context)
```

#### Parameters
* name (string) **required** - Required.
* responseView (string) - The response_view specifies which subset of the Task will be
* $.xgafv (string) - V1 error format.
* access_token (string) - OAuth access token.
* alt (string) - Data format for response.
* bearer_token (string) - OAuth bearer token.
* callback (string) - JSONP
* fields (string) - Selector specifying which fields to include in a partial response.
* key (string) - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* oauth_token (string) - OAuth 2.0 token for the current user.
* pp (boolean) - Pretty-print response.
* prettyPrint (boolean) - Returns response with indentations and line breaks.
* quotaUser (string) - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* uploadType (string) - Legacy upload protocol for media (e.g. "media", "multipart").
* upload_protocol (string) - Upload protocol for media (e.g. "raw", "multipart").

### projects.locations.queues.patch
Updates a queue.

This method creates the queue if it does not exist and updates
the queue if it does exist.

WARNING: This method is only available to whitelisted
users. Using this method carries some risk. Read
[Overview of Queue Management and queue.yaml](/cloud-tasks/docs/queue-yaml)
carefully and then sign up for
[whitelist access to this method](https://goo.gl/Fe5mUy).


```js
google_cloudtasks.projects.locations.queues.patch({
  "name": ""
}, context)
```

#### Parameters
* body (object) - A queue is a container of related tasks. Queues are configured to manage
* name (string) **required** - The queue name.
* updateMask (string) - A mask used to specify which fields of the queue are being updated.
* $.xgafv (string) - V1 error format.
* access_token (string) - OAuth access token.
* alt (string) - Data format for response.
* bearer_token (string) - OAuth bearer token.
* callback (string) - JSONP
* fields (string) - Selector specifying which fields to include in a partial response.
* key (string) - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* oauth_token (string) - OAuth 2.0 token for the current user.
* pp (boolean) - Pretty-print response.
* prettyPrint (boolean) - Returns response with indentations and line breaks.
* quotaUser (string) - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* uploadType (string) - Legacy upload protocol for media (e.g. "media", "multipart").
* upload_protocol (string) - Upload protocol for media (e.g. "raw", "multipart").

### projects.locations.list
Lists information about the supported locations for this service.


```js
google_cloudtasks.projects.locations.list({
  "name": ""
}, context)
```

#### Parameters
* filter (string) - The standard list filter.
* name (string) **required** - The resource that owns the locations collection, if applicable.
* pageSize (integer) - The standard list page size.
* pageToken (string) - The standard list page token.
* $.xgafv (string) - V1 error format.
* access_token (string) - OAuth access token.
* alt (string) - Data format for response.
* bearer_token (string) - OAuth bearer token.
* callback (string) - JSONP
* fields (string) - Selector specifying which fields to include in a partial response.
* key (string) - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* oauth_token (string) - OAuth 2.0 token for the current user.
* pp (boolean) - Pretty-print response.
* prettyPrint (boolean) - Returns response with indentations and line breaks.
* quotaUser (string) - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* uploadType (string) - Legacy upload protocol for media (e.g. "media", "multipart").
* upload_protocol (string) - Upload protocol for media (e.g. "raw", "multipart").

### projects.locations.queues.tasks.pull
Pulls tasks from a pull queue and acquires a lease on them for a
specified PullTasksRequest.lease_duration.

This method is invoked by the lease holder to obtain the
lease. The lease holder must acknowledge the task via
CloudTasks.AcknowledgeTask after they have performed the work
associated with the task.

The payload is intended to store data that the lease holder needs
to perform the work associated with the task. To return the
payloads in the PullTasksResponse, set
PullTasksRequest.response_view to Task.View.FULL.

A maximum of 10 qps of CloudTasks.PullTasks requests are allowed per
queue. google.rpc.Code.RESOURCE_EXHAUSTED is returned when this limit
is exceeded. google.rpc.Code.RESOURCE_EXHAUSTED is also returned when
RateLimits.max_tasks_dispatched_per_second is exceeded.


```js
google_cloudtasks.projects.locations.queues.tasks.pull({
  "name": ""
}, context)
```

#### Parameters
* body (object) - Request message for pulling tasks using CloudTasks.PullTasks.
* name (string) **required** - Required.
* $.xgafv (string) - V1 error format.
* access_token (string) - OAuth access token.
* alt (string) - Data format for response.
* bearer_token (string) - OAuth bearer token.
* callback (string) - JSONP
* fields (string) - Selector specifying which fields to include in a partial response.
* key (string) - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* oauth_token (string) - OAuth 2.0 token for the current user.
* pp (boolean) - Pretty-print response.
* prettyPrint (boolean) - Returns response with indentations and line breaks.
* quotaUser (string) - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* uploadType (string) - Legacy upload protocol for media (e.g. "media", "multipart").
* upload_protocol (string) - Upload protocol for media (e.g. "raw", "multipart").

### projects.locations.queues.tasks.acknowledge
Acknowledges a pull task.

The lease holder, that is, the entity that received this task in
a PullTasksResponse, must call this method to indicate that
the work associated with the task has finished.

The lease holder must acknowledge a task within the
PullTasksRequest.lease_duration or the lease will expire and
the task will become ready to be returned in a different
PullTasksResponse. After the task is acknowledged, it will
not be returned by a later CloudTasks.PullTasks,
CloudTasks.GetTask, or CloudTasks.ListTasks.


```js
google_cloudtasks.projects.locations.queues.tasks.acknowledge({
  "name": ""
}, context)
```

#### Parameters
* body (object) - Request message for acknowledging a task using
* name (string) **required** - Required.
* $.xgafv (string) - V1 error format.
* access_token (string) - OAuth access token.
* alt (string) - Data format for response.
* bearer_token (string) - OAuth bearer token.
* callback (string) - JSONP
* fields (string) - Selector specifying which fields to include in a partial response.
* key (string) - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* oauth_token (string) - OAuth 2.0 token for the current user.
* pp (boolean) - Pretty-print response.
* prettyPrint (boolean) - Returns response with indentations and line breaks.
* quotaUser (string) - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* uploadType (string) - Legacy upload protocol for media (e.g. "media", "multipart").
* upload_protocol (string) - Upload protocol for media (e.g. "raw", "multipart").

### projects.locations.queues.tasks.cancelLease
Cancel a pull task's lease.

The lease holder can use this method to cancel a task's lease
by setting Task.schedule_time to now. This will make the task
available to be leased to the next caller of CloudTasks.PullTasks.


```js
google_cloudtasks.projects.locations.queues.tasks.cancelLease({
  "name": ""
}, context)
```

#### Parameters
* body (object) - Request message for canceling a lease using
* name (string) **required** - Required.
* $.xgafv (string) - V1 error format.
* access_token (string) - OAuth access token.
* alt (string) - Data format for response.
* bearer_token (string) - OAuth bearer token.
* callback (string) - JSONP
* fields (string) - Selector specifying which fields to include in a partial response.
* key (string) - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* oauth_token (string) - OAuth 2.0 token for the current user.
* pp (boolean) - Pretty-print response.
* prettyPrint (boolean) - Returns response with indentations and line breaks.
* quotaUser (string) - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* uploadType (string) - Legacy upload protocol for media (e.g. "media", "multipart").
* upload_protocol (string) - Upload protocol for media (e.g. "raw", "multipart").

### projects.locations.queues.pause
Pauses the queue.

If a queue is paused then the system will stop executing the
tasks in the queue until it is resumed via
CloudTasks.ResumeQueue. Tasks can still be added when the
queue is paused. The state of the queue is stored in
Queue.queue_state; if paused it will be set to
Queue.QueueState.PAUSED.

WARNING: This method is only available to whitelisted
users. Using this method carries some risk. Read
[Overview of Queue Management and queue.yaml](/cloud-tasks/docs/queue-yaml)
carefully and then sign up for
[whitelist access to this method](https://goo.gl/Fe5mUy).


```js
google_cloudtasks.projects.locations.queues.pause({
  "name": ""
}, context)
```

#### Parameters
* body (object) - Request message for CloudTasks.PauseQueue.
* name (string) **required** - Required.
* $.xgafv (string) - V1 error format.
* access_token (string) - OAuth access token.
* alt (string) - Data format for response.
* bearer_token (string) - OAuth bearer token.
* callback (string) - JSONP
* fields (string) - Selector specifying which fields to include in a partial response.
* key (string) - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* oauth_token (string) - OAuth 2.0 token for the current user.
* pp (boolean) - Pretty-print response.
* prettyPrint (boolean) - Returns response with indentations and line breaks.
* quotaUser (string) - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* uploadType (string) - Legacy upload protocol for media (e.g. "media", "multipart").
* upload_protocol (string) - Upload protocol for media (e.g. "raw", "multipart").

### projects.locations.queues.purge
Purges a queue by deleting all of its tasks.

All tasks created before this method is called are permanently deleted.

Purge operations can take up to one minute to take effect. Tasks
might be dispatched before the purge takes effect. A purge is irreversible.


```js
google_cloudtasks.projects.locations.queues.purge({
  "name": ""
}, context)
```

#### Parameters
* body (object) - Request message for CloudTasks.PurgeQueue.
* name (string) **required** - Required.
* $.xgafv (string) - V1 error format.
* access_token (string) - OAuth access token.
* alt (string) - Data format for response.
* bearer_token (string) - OAuth bearer token.
* callback (string) - JSONP
* fields (string) - Selector specifying which fields to include in a partial response.
* key (string) - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* oauth_token (string) - OAuth 2.0 token for the current user.
* pp (boolean) - Pretty-print response.
* prettyPrint (boolean) - Returns response with indentations and line breaks.
* quotaUser (string) - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* uploadType (string) - Legacy upload protocol for media (e.g. "media", "multipart").
* upload_protocol (string) - Upload protocol for media (e.g. "raw", "multipart").

### projects.locations.queues.tasks.renewLease
Renew the current lease of a pull task.

The lease holder can use this method to extend the lease by a new
duration, starting from now. The new task lease will be
returned in Task.schedule_time.


```js
google_cloudtasks.projects.locations.queues.tasks.renewLease({
  "name": ""
}, context)
```

#### Parameters
* body (object) - Request message for renewing a lease using CloudTasks.RenewLease.
* name (string) **required** - Required.
* $.xgafv (string) - V1 error format.
* access_token (string) - OAuth access token.
* alt (string) - Data format for response.
* bearer_token (string) - OAuth bearer token.
* callback (string) - JSONP
* fields (string) - Selector specifying which fields to include in a partial response.
* key (string) - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* oauth_token (string) - OAuth 2.0 token for the current user.
* pp (boolean) - Pretty-print response.
* prettyPrint (boolean) - Returns response with indentations and line breaks.
* quotaUser (string) - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* uploadType (string) - Legacy upload protocol for media (e.g. "media", "multipart").
* upload_protocol (string) - Upload protocol for media (e.g. "raw", "multipart").

### projects.locations.queues.resume
Resume a queue.

This method resumes a queue after it has been
Queue.QueueState.PAUSED or Queue.QueueState.DISABLED. The state of
a queue is stored in Queue.queue_state; after calling this method it
will be set to Queue.QueueState.RUNNING.

WARNING: This method is only available to whitelisted
users. Using this method carries some risk. Read
[Overview of Queue Management and queue.yaml](/cloud-tasks/docs/queue-yaml)
carefully and then sign up for
[whitelist access to this method](https://goo.gl/Fe5mUy).

WARNING: Resuming many high-QPS queues at the same time can
lead to target overloading. If you are resuming high-QPS
queues, follow the 500/50/5 pattern described in
[Managing Cloud Tasks Scaling Risks](/cloud-tasks/pdfs/managing-cloud-tasks-scaling-risks-2017-06-05.pdf).


```js
google_cloudtasks.projects.locations.queues.resume({
  "name": ""
}, context)
```

#### Parameters
* body (object) - Request message for CloudTasks.ResumeQueue.
* name (string) **required** - Required.
* $.xgafv (string) - V1 error format.
* access_token (string) - OAuth access token.
* alt (string) - Data format for response.
* bearer_token (string) - OAuth bearer token.
* callback (string) - JSONP
* fields (string) - Selector specifying which fields to include in a partial response.
* key (string) - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* oauth_token (string) - OAuth 2.0 token for the current user.
* pp (boolean) - Pretty-print response.
* prettyPrint (boolean) - Returns response with indentations and line breaks.
* quotaUser (string) - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* uploadType (string) - Legacy upload protocol for media (e.g. "media", "multipart").
* upload_protocol (string) - Upload protocol for media (e.g. "raw", "multipart").

### projects.locations.queues.tasks.run
Forces a task to run now.

This command is meant to be used for manual debugging. For
example, CloudTasks.RunTask can be used to retry a failed
task after a fix has been made or to manually force a task to be
dispatched now.

When this method is called, Cloud Tasks will dispatch the task to its
target, even if the queue is Queue.QueueState.PAUSED.

The dispatched task is returned. That is, the task that is returned
contains the Task.task_status after the task is dispatched but
before the task is received by its target.

If Cloud Tasks receives a successful response from the task's
handler, then the task will be deleted; otherwise the task's
Task.schedule_time will be reset to the time that
CloudTasks.RunTask was called plus the retry delay specified
in the queue and task's RetryConfig.

CloudTasks.RunTask returns google.rpc.Code.NOT_FOUND when
it is called on a task that has already succeeded or permanently
failed. google.rpc.Code.FAILED_PRECONDITION is returned when
CloudTasks.RunTask is called on task that is dispatched or
already running.


```js
google_cloudtasks.projects.locations.queues.tasks.run({
  "name": ""
}, context)
```

#### Parameters
* body (object) - Request message for forcing a task to run now using
* name (string) **required** - Required.
* $.xgafv (string) - V1 error format.
* access_token (string) - OAuth access token.
* alt (string) - Data format for response.
* bearer_token (string) - OAuth bearer token.
* callback (string) - JSONP
* fields (string) - Selector specifying which fields to include in a partial response.
* key (string) - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* oauth_token (string) - OAuth 2.0 token for the current user.
* pp (boolean) - Pretty-print response.
* prettyPrint (boolean) - Returns response with indentations and line breaks.
* quotaUser (string) - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* uploadType (string) - Legacy upload protocol for media (e.g. "media", "multipart").
* upload_protocol (string) - Upload protocol for media (e.g. "raw", "multipart").

### projects.locations.queues.list
Lists queues.

Queues are returned in lexicographical order.


```js
google_cloudtasks.projects.locations.queues.list({
  "parent": ""
}, context)
```

#### Parameters
* filter (string) - `filter` can be used to specify a subset of queues. Any Queue
* pageSize (integer) - Requested page size.
* pageToken (string) - A token identifying the page of results to return.
* parent (string) **required** - Required.
* $.xgafv (string) - V1 error format.
* access_token (string) - OAuth access token.
* alt (string) - Data format for response.
* bearer_token (string) - OAuth bearer token.
* callback (string) - JSONP
* fields (string) - Selector specifying which fields to include in a partial response.
* key (string) - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* oauth_token (string) - OAuth 2.0 token for the current user.
* pp (boolean) - Pretty-print response.
* prettyPrint (boolean) - Returns response with indentations and line breaks.
* quotaUser (string) - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* uploadType (string) - Legacy upload protocol for media (e.g. "media", "multipart").
* upload_protocol (string) - Upload protocol for media (e.g. "raw", "multipart").

### projects.locations.queues.create
Creates a queue.

WARNING: This method is only available to whitelisted
users. Using this method carries some risk. Read
[Overview of Queue Management and queue.yaml](/cloud-tasks/docs/queue-yaml)
carefully and then sign up for
[whitelist access to this method](https://goo.gl/Fe5mUy).


```js
google_cloudtasks.projects.locations.queues.create({
  "parent": ""
}, context)
```

#### Parameters
* body (object) - A queue is a container of related tasks. Queues are configured to manage
* parent (string) **required** - Required.
* $.xgafv (string) - V1 error format.
* access_token (string) - OAuth access token.
* alt (string) - Data format for response.
* bearer_token (string) - OAuth bearer token.
* callback (string) - JSONP
* fields (string) - Selector specifying which fields to include in a partial response.
* key (string) - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* oauth_token (string) - OAuth 2.0 token for the current user.
* pp (boolean) - Pretty-print response.
* prettyPrint (boolean) - Returns response with indentations and line breaks.
* quotaUser (string) - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* uploadType (string) - Legacy upload protocol for media (e.g. "media", "multipart").
* upload_protocol (string) - Upload protocol for media (e.g. "raw", "multipart").

### projects.locations.queues.tasks.list
Lists the tasks in a queue.

By default response_view is Task.View.BASIC; not all
information is retrieved by default due to performance
considerations; ListTasksRequest.response_view controls the
subset of information which is returned.


```js
google_cloudtasks.projects.locations.queues.tasks.list({
  "parent": ""
}, context)
```

#### Parameters
* orderBy (string) - Sort order used for the query. The only fields supported for sorting
* pageSize (integer) - Requested page size. Fewer tasks than requested might be returned.
* pageToken (string) - A token identifying the page of results to return.
* parent (string) **required** - Required.
* responseView (string) - The response_view specifies which subset of the Task will be
* $.xgafv (string) - V1 error format.
* access_token (string) - OAuth access token.
* alt (string) - Data format for response.
* bearer_token (string) - OAuth bearer token.
* callback (string) - JSONP
* fields (string) - Selector specifying which fields to include in a partial response.
* key (string) - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* oauth_token (string) - OAuth 2.0 token for the current user.
* pp (boolean) - Pretty-print response.
* prettyPrint (boolean) - Returns response with indentations and line breaks.
* quotaUser (string) - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* uploadType (string) - Legacy upload protocol for media (e.g. "media", "multipart").
* upload_protocol (string) - Upload protocol for media (e.g. "raw", "multipart").

### projects.locations.queues.tasks.create
Creates a task and adds it to a queue.

To add multiple tasks at the same time, use
[HTTP batching](/storage/docs/json_api/v1/how-tos/batch)
or the batching documentation for your client library, for example
https://developers.google.com/api-client-library/python/guide/batch.

Tasks cannot be updated after creation; there is no UpdateTask command.

* For [App Engine queues](google.cloud.tasks.v2beta2.AppEngineHttpTarget),
  the maximum task size is 100KB.
* For [pull queues](google.cloud.tasks.v2beta2.PullTarget), this
  the maximum task size is 1MB.


```js
google_cloudtasks.projects.locations.queues.tasks.create({
  "parent": ""
}, context)
```

#### Parameters
* body (object) - Request message for CloudTasks.CreateTask.
* parent (string) **required** - Required.
* $.xgafv (string) - V1 error format.
* access_token (string) - OAuth access token.
* alt (string) - Data format for response.
* bearer_token (string) - OAuth bearer token.
* callback (string) - JSONP
* fields (string) - Selector specifying which fields to include in a partial response.
* key (string) - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* oauth_token (string) - OAuth 2.0 token for the current user.
* pp (boolean) - Pretty-print response.
* prettyPrint (boolean) - Returns response with indentations and line breaks.
* quotaUser (string) - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* uploadType (string) - Legacy upload protocol for media (e.g. "media", "multipart").
* upload_protocol (string) - Upload protocol for media (e.g. "raw", "multipart").

### projects.locations.queues.getIamPolicy
Gets the access control policy for a Queue.
Returns an empty policy if the resource exists and does not have a policy
set.

Authorization requires the following [Google IAM](/iam) permission on the
specified resource parent:

* `cloudtasks.queues.getIamPolicy`



```js
google_cloudtasks.projects.locations.queues.getIamPolicy({
  "resource": ""
}, context)
```

#### Parameters
* body (object) - Request message for `GetIamPolicy` method.
* resource (string) **required** - REQUIRED: The resource for which the policy is being requested.
* $.xgafv (string) - V1 error format.
* access_token (string) - OAuth access token.
* alt (string) - Data format for response.
* bearer_token (string) - OAuth bearer token.
* callback (string) - JSONP
* fields (string) - Selector specifying which fields to include in a partial response.
* key (string) - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* oauth_token (string) - OAuth 2.0 token for the current user.
* pp (boolean) - Pretty-print response.
* prettyPrint (boolean) - Returns response with indentations and line breaks.
* quotaUser (string) - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* uploadType (string) - Legacy upload protocol for media (e.g. "media", "multipart").
* upload_protocol (string) - Upload protocol for media (e.g. "raw", "multipart").

### projects.locations.queues.setIamPolicy
Sets the access control policy for a Queue. Replaces any existing
policy.

Authorization requires the following [Google IAM](/iam) permission on the
specified resource parent:

* `cloudtasks.queues.setIamPolicy`



```js
google_cloudtasks.projects.locations.queues.setIamPolicy({
  "resource": ""
}, context)
```

#### Parameters
* body (object) - Request message for `SetIamPolicy` method.
* resource (string) **required** - REQUIRED: The resource for which the policy is being specified.
* $.xgafv (string) - V1 error format.
* access_token (string) - OAuth access token.
* alt (string) - Data format for response.
* bearer_token (string) - OAuth bearer token.
* callback (string) - JSONP
* fields (string) - Selector specifying which fields to include in a partial response.
* key (string) - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* oauth_token (string) - OAuth 2.0 token for the current user.
* pp (boolean) - Pretty-print response.
* prettyPrint (boolean) - Returns response with indentations and line breaks.
* quotaUser (string) - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* uploadType (string) - Legacy upload protocol for media (e.g. "media", "multipart").
* upload_protocol (string) - Upload protocol for media (e.g. "raw", "multipart").

### projects.locations.queues.testIamPermissions
Returns permissions that a caller has on a Queue.
If the resource does not exist, this will return an empty set of
permissions, not a google.rpc.Code.NOT_FOUND error.

Note: This operation is designed to be used for building permission-aware
UIs and command-line tools, not for authorization checking. This operation
may "fail open" without warning.



```js
google_cloudtasks.projects.locations.queues.testIamPermissions({
  "resource": ""
}, context)
```

#### Parameters
* body (object) - Request message for `TestIamPermissions` method.
* resource (string) **required** - REQUIRED: The resource for which the policy detail is being requested.
* $.xgafv (string) - V1 error format.
* access_token (string) - OAuth access token.
* alt (string) - Data format for response.
* bearer_token (string) - OAuth bearer token.
* callback (string) - JSONP
* fields (string) - Selector specifying which fields to include in a partial response.
* key (string) - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* oauth_token (string) - OAuth 2.0 token for the current user.
* pp (boolean) - Pretty-print response.
* prettyPrint (boolean) - Returns response with indentations and line breaks.
* quotaUser (string) - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* uploadType (string) - Legacy upload protocol for media (e.g. "media", "multipart").
* upload_protocol (string) - Upload protocol for media (e.g. "raw", "multipart").
