## About the connector
Cyble Threat Intel is an integration which will help users to fetch Cyble's TAXII Feed service into Environment.
<p>This document provides information about the Cyble Vision Connector, which facilitates automated interactions, with a Cyble Vision server using FortiSOAR&trade; playbooks. Add the Cyble Vision Connector as a step in FortiSOAR&trade; playbooks and perform automated operations with Cyble Vision.</p>

### Version information

Connector Version: 1.0.0


Authored By: Fortinet

Certified: No
## Installing the connector
<p>Use the <strong>Content Hub</strong> to install the connector. For the detailed procedure to install a connector, click <a href="https://docs.fortinet.com/document/fortisoar/0.0.0/installing-a-connector/1/installing-a-connector" target="_top">here</a>.</p><p>You can also use the <code>yum</code> command as a root user to install the connector:</p>
<pre>yum install cyops-connector-cyble-vision</pre>

## Prerequisites to configuring the connector
- You must have the credentials of Cyble Vision server to which you will connect and perform automated operations.
- The FortiSOAR&trade; server should have outbound connectivity to port 443 on the Cyble Vision server.

## Minimum Permissions Required
- Not applicable

## Configuring the connector
For the procedure to configure a connector, click [here](https://docs.fortinet.com/document/fortisoar/0.0.0/configuring-a-connector/1/configuring-a-connector)
### Configuration parameters
<p>In FortiSOAR&trade;, on the Connectors page, click the <strong>Cyble Vision</strong> connector row (if you are in the <strong>Grid</strong> view on the Connectors page) and in the <strong>Configurations</strong> tab enter the required configuration details:</p>
<table border=1><thead><tr><th>Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Server URL</td><td>The URL of the Cyble Vision server to which you will connect and perform the automated operations.
</td>
</tr><tr><td>Token</td><td>The token used to access the Cyble Vision APIs and perform the automated operations.
</td>
</tr><tr><td>Verify SSL</td><td>Specifies whether the SSL certificate for the server is to be verified or not. <br/>By default, this option is set to True.</td></tr>
</tbody></table>

## Actions supported by the connector
The following automated operations can be included in playbooks and you can also use the annotations to access operations:
<table border=1><thead><tr><th>Function</th><th>Description</th><th>Annotation and Category</th></tr></thead><tbody><tr><td>Fetch Indicators</td><td>Retrieves indicators based on the start time, end time and other parameters that you have specified.</td><td>fetch_indicators <br/>Investigation</td></tr>
<tr><td>Fetch Alerts</td><td>Retrieves alerts based on the start time, end time, limit, offset other parameters that you have specified.</td><td>fetch_alerts <br/>Investigation</td></tr>
<tr><td>Fetch Event Detail</td><td>Retrieves event details based on the event type, event ID, limit, offset parameters that you have specified.</td><td>fetch_event_detail <br/>Investigation</td></tr>
</tbody></table>

### operation: Fetch Indicators
#### Input parameters
<table border=1><thead><tr><th>Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Start Time</td><td>(Optional) Specify the start date and time from when to retrieve the indicators from Cyble Vision.
</td></tr><tr><td>End Time</td><td>(Optional) Specify the end date and time till when to retrieve the list of executed reports from Cyble Vision.
</td></tr><tr><td>Offset</td><td>(Optional) Specify the maximum number of records that this operation should return. Default value is 50.
</td></tr><tr><td>Limit</td><td>(Optional) Specify the maximum number of records that this operation should return. Default value is 50.
</td></tr><tr><td>Type</td><td>(Optional) Specify the type for which the indicators to retrieve from Cyble Vision. e.g. CIDR, CVE, domain, email, FileHash-IMPHASH, FileHash-MD5, FileHash-PEHASH, FileHash-SHA1, FileHash-SHA256, FilePath, hostname, IPv4, IPv6, Mutex, NIDS, URI, URL, YARA, osquery, Ja3, Bitcoinaddress, Sslcertfingerprint.
</td></tr></tbody></table>

#### Output

 The output contains a non-dictionary value.
### operation: Fetch Alerts
#### Input parameters
<table border=1><thead><tr><th>Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Start Time</td><td>Specify the start date and time from when to retrieve the indicators from Cyble Vision.
</td></tr><tr><td>End Time</td><td>Specify the end date and time till when to retrieve the list of executed reports from Cyble Vision.
</td></tr><tr><td>Offset</td><td>Specify the maximum number of records that this operation should return. Default value is 50.
</td></tr><tr><td>Limit</td><td>Specify the maximum number of records that this operation should return. Default value is 50.
</td></tr><tr><td>Sort by Order</td><td>Specify the sorting order of the result. You choose from following options: Ascending or Descending.
</td></tr><tr><td>Priority</td><td>Specify the type for which the alerts to retrieve from Cyble Vision. e.g. high,medium,low,informational.
</td></tr></tbody></table>
#### Output

 The output contains a non-dictionary value.
### operation: Fetch Event Detail
#### Input parameters
<table border=1><thead><tr><th>Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Event Type</td><td>Specify the event type whose details to retrieve from Cyble Vision.
</td></tr><tr><td>Event ID</td><td>Specify the event ID whose details to retrieve from Cyble Vision.
</td></tr><tr><td>Offset</td><td>Specify the maximum number of records that this operation should return. Default value is 50.
</td></tr><tr><td>Limit</td><td>Specify the maximum number of records that this operation should return. Default value is 50.
</td></tr></tbody></table>

#### Output

 The output contains a non-dictionary value.
## Included playbooks
The `Sample - cyble-vision - 1.0.0` playbook collection comes bundled with the Cyble Vision connector. These playbooks contain steps using which you can perform all supported actions. You can see bundled playbooks in the **Automation** > **Playbooks** section in FortiSOAR&trade; after importing the Cyble Vision connector.

- Cyble Vision  > Fetch and Create
- Cyble Vision > Ingest
- Get Indicators

**Note**: If you are planning to use any of the sample playbooks in your environment, ensure that you clone those playbooks and move them to a different collection since the sample playbook collection gets deleted during connector upgrade and delete.
## Data Ingestion Support
Use the Data Ingestion Wizard to easily ingest data into FortiSOAR&trade; by pulling events/alerts/incidents, based on the requirement.

**TODO:** provide the list of steps to configure the ingestion with the screen shots and limitations if any in this section.