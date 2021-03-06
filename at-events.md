---

copyright:
  years: 2017, 2019
lastupdated: "2019-09-23"

keywords: Centralized security, security management, alerts, security risk, insights, threat detection

subcollection: security-advisor

---


{:external: target="_blank" .external}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:codeblock: .codeblock}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:deprecated: .deprecated}
{:download: .download}



# {{site.data.keyword.cloudaccesstrailshort}} events
{: #at_events}

You can view, manage, and audit user-initiated activities made in your {{site.data.keyword.security-advisor_long}} service instance by using the {{site.data.keyword.at_short}} service.
{: shortdesc}


For more information about how the service works, see the [{{site.data.keyword.at_short}} docs](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-cloud_services#cloud_services).




## Where to view events
{: #monitor}

Events are available in the {{site.data.keyword.at_short}} **account domain** that is available in the {{site.data.keyword.cloud_notm}} region where the events are generated.

1. Log in to your {{site.data.keyword.cloud_notm}} account.
2. From the catalog, provision an instance of the {{site.data.keyword.at_short}} service in the same account as your {{site.data.keyword.appid_short_notm}} instance.
3. From the **Observability > Activity Tracker** tab, verify the information for the instance that you created.
4. Click **View LogDNA** and make sure you're on the **Everything** dashboard. Any events that meet the qualifications for your {{site.data.keyword.at_short}} payment plan are visible. You can filter your results by tags, sources, apps or levels. You can also search for specific events or jump to a specific timeframe.


For users other than the account owner to view logs, you must use the premium plan. To let other users view events, see [Granting permissions to see account events](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_manage_events).
{: tip}


## List of events
{: #events}

Check out the following table for a list of the events that are sent to {{site.data.keyword.at_short}}.
{: shortdesc}

<table>
  <caption>Table 1. {{site.data.keyword.at_short}} events</caption>
  <tr>
    <th>Action</th>
    <th>Description</th>
  </tr>
  <tr>
    <td><code>security-advisor.metadata.read</code></td>
    <td>View a previously created note or notes.</td>
  </tr>
  <tr>
    <td><code>security-advisor.metadata.write</code></td>
    <td>Create a note.</td>
  </tr>
  <tr>
    <td><code>security-advisor.metadata.delete</code></td>
    <td>Delete a note.</td>
  </tr>
  <tr>
    <td><code>security-advisor.metadata.update</code></td>
    <td>Update a note.</td>
  </tr>
  <tr>
    <td><code>security-advisor.findings.read</code></td>
    <td>View one or more occurrences.</td>
  </tr>
  <tr>
    <td><code>security-advisor.findings.write</code></td>
    <td>Create an occurrence.</td>
  </tr>
  <tr>
    <td><code>security-advisor.findings.delete</code></td>
    <td>Delete an occurrence.</td>
  </tr>
  <tr>
    <td><code>security-advisor.findings.update</code></td>
    <td>Update an occurrence.</td>
  </tr>
  <tr>
    <td><code>security-advisor.custom-solution.read</code></td>
    <td>Read custom solutions that have been added to the service.</td>
  </tr>
  <tr>
    <td><code>security-advisor.custom-solution.write</code></td>
    <td>Add a custom solution to the service.</td>
  </tr>
  <tr>
    <td><code>security-advisor.custom-solution.update</code></td>
    <td>Update an existing custom solution within the service.</td>
  </tr>
  <tr>
    <td><code>security-advisor.custom-solution.delete</code></td>
    <td>Delete a custom solution from the service.</td>
  </tr>
  <tr>
    <td><code>security-advisor.partner-solution.read</code></td>
    <td>View the partner solutions that you have added to your service instance.</td>
  </tr>
  <tr>
    <td><code>security-advisor.partner-solution.write</code></td>
    <td>Add a partner solution to your service instance.</td>
  </tr>
  <tr>
    <td><code>security-advisor.partner-solution.update</code></td>
    <td>Update a partner solution in your service instance.</td>
  </tr>
  <tr>
    <td><code>security-advisor.partner-solution.delete</code></td>
    <td>Delete a partner solution from your service instance.</td>
  </tr>
  <tr>
    <td><code>security-advisor.network-insights.enable</code></td>
    <td>Enable the Network Insights feature that is provided by {{site.data.keyword.security-advisor_short}}.</td>
  </tr>
  <tr>
    <td><code>security-advisor.network-insights.disable</code></td>
    <td>Disable the Network Insights feature that is provided by {{site.data.keyword.security-advisor_short}}.</td>
  </tr>
  <tr>
    <td><code>security-advisor.activity-insights.enable</code></td>
    <td>Enable the Activity Insights feature that is provided by {{site.data.keyword.security-advisor_short}}.</td>
  </tr>
  <tr>
    <td><code>security-advisor.activity-insights.disable</code></td>
    <td>Disable the Activity Insights feature that is provided by {{site.data.keyword.security-advisor_short}}.</td>
  </tr>
  <tr>
    <td><code>security-advisor.insights-cos.create</code></td>
    <td>Create a Cloud Object Storage instance through {{site.data.keyword.security-advisor_short}} for network and activity insights.</td>
  </tr>
</table>
