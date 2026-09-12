# AD-CS
<h1>On-Premises Identity & Access Management (IAM) Project</h1>

<h3>Active Directory Domain Services, Role-Based Access Control, Group Policy, Security Filtering, and Joiner-Mover-Leaver Lifecycle Management</h3>

<p>
This project demonstrates the design and implementation of an on-premises Identity and Access Management (IAM) environment using Microsoft Active Directory Domain Services (AD DS) on Windows Server 2022.
The lab environment was built around the simulated Sahbak organisation and was designed to demonstrate practical IAM administration, identity lifecycle management, role-based access control, Group Policy implementation, security filtering, application control, auditing, and security hardening.
</p>

<p>
A new Active Directory forest was created using the domain <b>sahbak.com</b>. The environment was structured using three Organisational Units (OUs) representing different office locations:
</p>

<ol>
  <li>Ashford</li>
  <li>Kent</li>
  <li>Sheffield</li>
</ol>

<p>
Each OU was configured with security groups representing different business functions. The group structure consisted of:
</p>

<ul>
  <li>Ashford – Human Resources and IT Department</li>
  <li>Kent – Logistic and Procurement</li>
  <li>Sheffield – Audit and Finance</li>
</ul>

<p>
A total of 12 user accounts were provisioned using the naming convention <b>firstname.lastname@sahbak.com</b>. Users were assigned to the appropriate Organisational Unit and security group based on their simulated office location and job role.
This demonstrated the use of security groups to support Role-Based Access Control (RBAC) and reduce the need to assign permissions directly to individual users.
</p>

<h2>IAM Controls Implemented</h2>

<ul>
  <li>Active Directory Domain Services deployment and Domain Controller promotion</li>
  <li>Organisational Unit design and administration</li>
  <li>User account provisioning and identity attribute management</li>
  <li>Security group creation and Role-Based Access Control</li>
  <li>Password Security Policy</li>
  <li>Account Lockout Policy</li>
  <li>Control Panel and Command Prompt restrictions</li>
  <li>AppLocker application execution controls</li>
  <li>Removable Media and USB storage restrictions</li>
  <li>Advanced Audit Policy configuration</li>
  <li>Group Policy security filtering and scope management</li>
  <li>Joiner, Mover, and Leaver identity lifecycle processes</li>
  <li>Disabled Users OU for de-provisioned accounts</li>
</ul>

<h2>Group Policy Implementation</h2>

<p>
Multiple custom Group Policy Objects (GPOs) were created and managed through the Group Policy Management Console (GPMC). Each GPO was designed to address a specific security requirement and was linked at the appropriate domain or OU scope.
</p>

<p>
The policies implemented included password complexity and password history requirements, account lockout protection, application execution controls, removable storage restrictions, Windows configuration restrictions, and identity-related audit logging.
</p>

<p>
Security filtering was also configured to demonstrate targeted policy application. A dedicated <b>All-Sahbak-Users</b> security group was created for user-targeted policies, while specific groups such as Procurement were excluded from selected policies using the <b>Deny – Apply Group Policy</b> permission.
</p>

<h2>AppLocker Application Control</h2>

<p>
AppLocker was configured to demonstrate application execution control within the Active Directory environment.
Default executable allow rules were created to permit normal Windows and Program Files applications, while a custom deny rule was created to restrict access to <b>cmd.exe</b> for targeted users.
</p>

<p>
This demonstrated how application control can be used to reduce unauthorised command-line activity and restrict access to administrative tools.
</p>

<h2>Joiner-Mover-Leaver Lifecycle</h2>

<h3>Joiner</h3>

<p>
New users were provisioned into the appropriate OU based on office location and assigned to the relevant security group according to their business role.
User Principal Names (UPNs) followed the standard format <b>firstname.lastname@sahbak.com</b>.
</p>

<h3>Mover</h3>

<p>
The Mover process demonstrated how access should be updated when an employee changes role, department, or office location.
Users can be moved between OUs, removed from security groups associated with their previous role, and added to groups required for their new responsibilities.
This supports the principle of least privilege by ensuring that obsolete access is removed when responsibilities change.
</p>

<h3>Leaver</h3>

<p>
The Leaver process demonstrated secure identity de-provisioning. Departing user accounts were disabled to prevent further authentication, removed from unnecessary security groups, and moved into a dedicated <b>Disabled Users</b> OU.
This reduces the risk of unauthorised access through accounts that are no longer required.
</p>

<h2>Security Principles Demonstrated</h2>

<ul>
  <li>Least Privilege</li>
  <li>Role-Based Access Control (RBAC)</li>
  <li>Identity Lifecycle Management</li>
  <li>Access Governance</li>
  <li>Separation of Duties</li>
  <li>Secure Authentication</li>
  <li>Application Control</li>
  <li>Security Hardening</li>
  <li>Auditability and Accountability</li>
</ul>

<h2>Tools and Technologies</h2>

<ul>
  <li>Windows Server 2022</li>
  <li>Active Directory Domain Services (AD DS)</li>
  <li>Active Directory Users and Computers (ADUC)</li>
  <li>Group Policy Management Console (GPMC)</li>
  <li>AppLocker</li>
  <li>Advanced Audit Policy Configuration</li>
  <li>Windows PowerShell</li>
</ul>

<h2>Key Learning Outcomes</h2>

<p>
This project provided practical experience in designing and administering an enterprise-style Active Directory IAM environment.
The lab demonstrated how identities are created, grouped, governed, secured, monitored, and eventually de-provisioned throughout their lifecycle.
</p>

<p>
The project also strengthened understanding of how Group Policy, security groups, application controls, authentication policies, audit logging, and identity lifecycle processes work together to support enterprise Identity and Access Management.
</p>
