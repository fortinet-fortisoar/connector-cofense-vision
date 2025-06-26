## About the connector
Cofense Vision is a security solution designed to help organizations quickly detect, locate, and quarantine phishing emails across all employee inboxes.
<p>This document provides information about the Cofense Vision Connector, which facilitates automated interactions, with a Cofense Vision server using FortiSOAR&trade; playbooks. Add the Cofense Vision Connector as a step in FortiSOAR&trade; playbooks and perform automated operations with Cofense Vision.</p>

### Version information

Connector Version: 1.0.0

Authored By: Fortinet CSE

Contributor: Hariharan Devaraj

Certified: No

## Installing the connector
<p>From FortiSOAR&trade; 6.4.0 onwards, use the <strong>Connector Store</strong> to install the connector. For the detailed procedure to install a connector, click <a href="https://docs.fortinet.com/document/fortisoar/0.0.0/installing-a-connector/1/installing-a-connector" target="_top">here</a>.<br>You can also use the following <code>yum</code> command as a root user to install connectors from an SSH session:</p>
`yum install cyops-connector-cofense-vision`

## Prerequisites to configuring the connector
- You must have the URL of Cofense Vision server to which you will connect and perform automated operations and credentials to access that server.
- The FortiSOAR&trade; server should have outbound connectivity to port 443 on the Cofense Vision server.

## Minimum Permissions Required
- N/A

## Configuring the connector
For the procedure to configure a connector, click [here](https://docs.fortinet.com/document/fortisoar/0.0.0/configuring-a-connector/1/configuring-a-connector)
### Configuration parameters
<p>In FortiSOAR&trade;, on the Connectors page, click the <strong>Cofense Vision</strong> connector row (if you are in the <strong>Grid</strong> view on the Connectors page) and in the <strong>Configurations&nbsp;</strong> tab enter the required configuration details:&nbsp;</p>
<table border=1><thead><tr><th>Parameter<br></th><th>Description<br></th></tr></thead><tbody><tr><td>Server URL<br></td><td>Specify the URL of the Cofense Vision server to connect and perform automated operations.<br>
<tr><td>Username<br></td><td>Specify the name of the client to connect to the endpoint and perform automated operations<br>
<tr><td>Password<br></td><td>Specify the password of the client to connect to the endpoint and perform automated operations<br>
<tr><td>Verify SSL<br></td><td>Specifies whether the SSL certificate for the server is to be verified or not. <br/>By default, this option is set as True.<br></td></tr>
</tbody></table>

## Actions supported by the connector
The following automated operations can be included in playbooks and you can also use the annotations to access operations from FortiSOAR&trade; release 4.10.0 and onwards:
<table border=1><thead><tr><th>Function<br></th><th>Description<br></th><th>Annotation and Category<br></th></tr></thead><tbody><tr><td>Search Email<br></td><td>Search for emails from Cofense Vision based on the email subject and sender email address you have provided.<br></td><td>search_email <br/>Investigation<br></td></tr>
<tr><td>Quarantine Email<br></td><td>Quarantine an emails in Cofense Vision based on the recipient address and internal message ID you have provided.<br></td><td>quarantine_email <br/>Investigation<br></td></tr>
</tbody></table>

### operation: Search Email

#### Input parameters
<table border=1><thead><tr><th>Parameter<br></th><th>Description<br></th></tr></thead><tbody><tr><td>Email Subject<br></td><td>Specify the comma-separated email subjects based on which you want to retrieve emails.<br>
</td></tr><tr><td>Sender Email Address<br></td><td>Specify the comma-separated sender email address based on which you want to retrieve emails.<br>
</td></tr></tbody></table>

#### Output

 The output contains a non-dictionary value.
### operation: Quarantine Email

#### Input parameters
<table border=1><thead><tr><th>Parameter<br></th><th>Description<br></th></tr></thead><tbody><tr><td>Recipient Address<br></td><td>Specify the comma-separated recipient email address of the account containing the emails to be quarantined.<br>
</td></tr><tr><td>Internet Message ID<br></td><td>Specify the ID of any emails in that account to be quarantined, with each internetMessageId enclosed in angle brackets.<br>
</td></tr></tbody></table>

#### Output

 The output contains a non-dictionary value.
## Included playbooks
The `Sample - Cofense Vision - 1.0.0` playbook collection comes bundled with the Cofense Vision connector. These playbooks contain steps using which you can perform all supported actions. You can see bundled playbooks in the **Automation** > **Playbooks** section in FortiSOAR<sup>TM</sup> after importing the Cofense Vision connector.

- Search Email
- Quarantine Email

**Note**: If you are planning to use any of the sample playbooks in your environment, ensure that you clone those playbooks and move them to a different collection, since the sample playbook collection gets deleted during connector upgrade and delete.
