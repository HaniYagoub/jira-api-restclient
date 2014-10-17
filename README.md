# Jira Api Rest Client

[![Build Status](https://secure.travis-ci.org/chobie/jira-api-restclient.png)](http://travis-ci.org/chobie/jira-api-restclient)


you know JIRA5 supports REST API. this is very useful to make some custom notifications and automated jobs.
(JIRA also supports email notification, but it's too much to custom templates, notification timing. unfortunately it requires Administration permission.)
this API library will help your problems regarding JIRA. hope you enjoy it.

# Usage

composer.json

```

```


````php
<?php
$api = new JiraRestClient\Api(
    "https://your-jira-project.net",
    new JiraRestClient\Api\Authentication\Basic("yourname", "password")
);

$walker = new JiraRestClient\Issues\Walker($api);
$walker->push("project = YOURPROJECT AND (status != closed and status != resolved) ORDER BY priority DESC");
foreach ($walker as $issue) {
    var_dump($issue);
    // send custom notification here.
}
````

# License

MIT License

# Forked from

Shuhei Tanuma
https://github.com/chobie/jira-api-restclient
http://chobie.github.io/


# JIRA5 Rest API Documents

https://developer.atlassian.com/static/rest/jira/6.0.html
