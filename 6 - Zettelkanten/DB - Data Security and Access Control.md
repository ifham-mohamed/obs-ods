
2024-08-11 19:36

Status:

Tags: #UOM #L2S2-S4 #DB 


# DB - Data Security and access control

Database access control is a method of allowing access to company’s sensitive data only to those people (database users) who are allowed to access such data and to restrict access to unauthorized persons. It includes two main components: authentication and authorization.

Authentication is a method of verifying the identity of a person who is accessing your database. Note that authentication isn’t enough to protect data. An additional layer of security is required, authorization, which determines whether a user should be allowed to access the data or make the transaction he’s attempting. Without authentication and authorization, there is no [data security](https://www.datasunrise.com/knowledge-center/database-security/).

Any company whose employees connect to the Internet, thus, every company today, needs some level of access control implemented.

### Types of Access Control

Obsolete access models include Discretionary Access Control (DAC) and Mandatory Access Control (MAC). Role Based Access Control (RBAC) is the most common method today, and the most recent model is Attribute Based Access Control (ABAC).

#### Discretionary Access Control (DAC)

With DAC models, the data owner allows access. DAC is a means of assigning access rights based on user-specified rules.

#### Mandatory Access Control (MAC)

MAC was developed using a nondiscretionary model, in which people are granted access based on an information clearance. MAC is a policy in which access rights are assigned based on central authority regulations.

#### Role Based Access Control (RBAC)

[RBAC](https://www.datasunrise.com/knowledge-center/role-based-access-control-rbac/) grants access based on a user’s role and implements key security principles such as “least privilege” and “separation of privilege.” Thus, someone attempting to access information can only access data necessary for their role.

#### Attribute Based Access Control (ABAC)

In [ABAC](https://www.datasunrise.com/knowledge-center/abac-attribute-based-access-control/), each resource and user are assigned a series of attributes. In this dynamic method, a comparative assessment of the user’s attributes, including time of day, position and location, are used to make a decision on access to a resource.

### How it Works

Let’s take a look how access control works in DataSunrise.

#### Two-Factor Authentication

DataSunrise includes [two-factor authentication](https://www.datasunrise.com/professional-info/2fa-as-extra-access-security/) mechanisms based on emails and one-time passwords (OTP) which allow to access the target database. Database users should input database’s password and complete email-based or Google Authenticator based authentication to get access to the target database.

#### Database Access Restriction

DataSunrise features Data [Security component](https://www.datasunrise.com/guides/security-rules-against-sql-injections/) which enables you to restrict access to a complete database or certain database objects depending on the following factors:

- Database username;
- Client application;
- Application username;
- IP address or hostname;
- Operating system user;
- Number of unsuccessful login attempts;
- Query text.

Thus, DataSunrise utilizes the ABAC method of access control. Data Security’s functionality is based on security rules created by DataSunrise administrator.

Regular [auditing and monitoring](https://www.datasunrise.com/guides/audit-guide/) of data access control systems can help identify potential vulnerabilities and ensure that access rights are being granted and revoked appropriately. Ultimately, investing in it is essential for protecting the most valuable assets and maintaining the trust of customers.


# Reference