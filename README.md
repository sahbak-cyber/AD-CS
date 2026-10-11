<h1>🔐 On-Premises Identity & Access Management Project</h1>

<h3>Active Directory, Role-Based Access Control, Group Policy, Security Filtering and Identity Lifecycle Management</h3>

<p>
  <img src="https://img.shields.io/badge/Windows%20Server-2022-0078D4" alt="Windows Server 2022">
  <img src="https://img.shields.io/badge/Active%20Directory-AD%20DS-005A9C" alt="Active Directory">
  <img src="https://img.shields.io/badge/Users-12-6A1B9A" alt="12 Users">
  <img src="https://img.shields.io/badge/Locations-3-FF6600" alt="Three Locations">
  <img src="https://img.shields.io/badge/Access%20Model-RBAC-008000" alt="RBAC">
  <img src="https://img.shields.io/badge/Identity%20Lifecycle-JML-D71920" alt="JML">
</p>

<h3>📌 Project Overview</h3>

<p>
This project demonstrates the design and implementation of an on-premises Identity and Access Management environment using Microsoft Active Directory Domain Services on Windows Server 2022.
</p>

<p>
The lab was built around the simulated Sahbak organisation and demonstrates practical IAM administration, identity lifecycle management, Role-Based Access Control, Group Policy implementation, security filtering, application control, auditing, and Windows security hardening.
</p>

<p>
A new Active Directory forest was created using the simulated domain <strong>sahbak.com</strong>. The environment was organised using location-based Organisational Units, role-based security groups, standardised user accounts, and targeted Group Policy Objects.
</p>

<h3>🏢 Organisational Unit Structure</h3>

<p>
Three primary Organisational Units were created to represent different organisational locations:
</p>

<ol>
  <li>Ashford,</li>
  <li>Kent and,</li>
  <li>Sheffield.</li>
</ol>

<p>
Each location-based OU contains security groups representing its associated business functions.
</p>

<table>
  <thead>
    <tr>
      <th>Organisational Unit</th>
      <th>Business Security Groups</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Ashford</td>
      <td>Human Resources and IT Department</td>
    </tr>
    <tr>
      <td>Kent</td>
      <td>Logistics and Procurement</td>
    </tr>
    <tr>
      <td>Sheffield</td>
      <td>Audit and Finance</td>
    </tr>
  </tbody>
</table>

<h3>👥 Identity Provisioning</h3>

<p>
A total of 12 simulated user accounts were provisioned. Each user was placed in the appropriate Organisational Unit and assigned to a security group based on their office location and business role.
</p>

<p>
User Principal Names followed a standardised organisational naming convention:
</p>

<pre><code>firstname.lastname@sahbak.com</code></pre>

<p>
Security-group membership was used to provide Role-Based Access Control and reduce the need to assign permissions directly to individual user accounts.
</p>

<h3>🛡️ IAM Controls Implemented</h3>

<ul>
  <li>Active Directory Domain Services deployment,</li>
  <li>Domain Controller promotion,</li>
  <li>Active Directory forest and domain configuration,</li>
  <li>Organisational Unit design and administration,</li>
  <li>User-account provisioning,</li>
  <li>Identity-attribute management,</li>
  <li>Security-group creation,</li>
  <li>Role-Based Access Control,</li>
  <li>Password Security Policy,</li>
  <li>Account Lockout Policy,</li>
  <li>Control Panel and Command Prompt restrictions,</li>
  <li>AppLocker application controls,</li>
  <li>Removable-media and USB-storage restrictions,</li>
  <li>Advanced Audit Policy configuration,</li>
  <li>Group Policy security filtering,</li>
  <li>Joiner-Mover-Leaver processes and,</li>
  <li>Disabled Users OU for de-provisioned accounts.</li>
</ul>

<h3>🔑 Password Security Policy</h3>

<table>
  <thead>
    <tr>
      <th>Setting</th>
      <th>Configured Value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Password history</td>
      <td>24 passwords remembered</td>
    </tr>
    <tr>
      <td>Maximum password age</td>
      <td>90 days</td>
    </tr>
    <tr>
      <td>Minimum password age</td>
      <td>1 day</td>
    </tr>
    <tr>
      <td>Minimum password length</td>
      <td>12 characters</td>
    </tr>
    <tr>
      <td>Password complexity</td>
      <td>Enabled</td>
    </tr>
    <tr>
      <td>Reversible password encryption</td>
      <td>Disabled</td>
    </tr>
  </tbody>
</table>

<h3>🔒 Account Lockout Policy</h3>

<table>
  <thead>
    <tr>
      <th>Setting</th>
      <th>Configured Value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Account lockout threshold</td>
      <td>5 failed sign-in attempts</td>
    </tr>
    <tr>
      <td>Account lockout duration</td>
      <td>30 minutes</td>
    </tr>
    <tr>
      <td>Reset account lockout counter</td>
      <td>30 minutes</td>
    </tr>
  </tbody>
</table>

<h3>⚙️ Group Policy Implementation</h3>

<p>
Multiple custom Group Policy Objects were created and managed through the Group Policy Management Console. Each GPO addressed a specific security requirement and was linked at the appropriate domain or OU level.
</p>

<p>
The implemented policies included password requirements, account-lockout protection, application execution controls, removable-storage restrictions, Windows configuration restrictions, firewall settings, software-installation controls, and identity-related audit logging.
</p>

<table>
  <thead>
    <tr>
      <th>Group Policy Object</th>
      <th>Security Purpose</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Password Security Policy</td>
      <td>Established password length, complexity, history and age requirements.</td>
    </tr>
    <tr>
      <td>Account Lockout Policy</td>
      <td>Protected accounts against repeated authentication attempts.</td>
    </tr>
    <tr>
      <td>Prevent CMD and Control Panel</td>
      <td>Restricted access to administrative and configuration tools.</td>
    </tr>
    <tr>
      <td>AppLocker Policy</td>
      <td>Controlled which applications targeted users could execute.</td>
    </tr>
    <tr>
      <td>Removable Media and USB Block</td>
      <td>Restricted removable-storage access.</td>
    </tr>
    <tr>
      <td>Firewall Policy</td>
      <td>Applied Windows Firewall security settings.</td>
    </tr>
    <tr>
      <td>Software Installation Policy</td>
      <td>Restricted unauthorised software installation.</td>
    </tr>
    <tr>
      <td>Advanced Audit Policy</td>
      <td>Enabled security-event logging and accountability.</td>
    </tr>
  </tbody>
</table>

<h3>🎯 Group Policy Security Filtering</h3>

<p>
Security filtering was configured to demonstrate targeted policy application. A dedicated <strong>All-Sahbak-Users</strong> security group was created for user-targeted Group Policies.
</p>

<p>
Specific groups, including Procurement, were excluded from selected policies through the <strong>Deny – Apply Group Policy</strong> permission. This demonstrated how GPO scope and security filtering can be used to apply different controls to different business groups.
</p>

<h3>🚫 AppLocker Application Control</h3>

<p>
AppLocker was configured to demonstrate application execution control within the Active Directory environment.
</p>

<p>
Default executable allow rules were created to permit authorised Windows and Program Files applications. A custom deny rule was then created to restrict access to <strong>cmd.exe</strong> for targeted users.
</p>

<p>
This demonstrated how application control can reduce unauthorised command-line activity and restrict access to administrative tools.
</p>

<h3>🔄 Joiner-Mover-Leaver Lifecycle</h3>

<h4>🟢 Joiner Process</h4>

<ol>
  <li>Receive an approved user-account request,</li>
  <li>Identify the user’s office location and business role,</li>
  <li>Create the account in the appropriate OU,</li>
  <li>Assign a standardised User Principal Name,</li>
  <li>Configure the required identity attributes,</li>
  <li>Add the user to the appropriate security groups,</li>
  <li>Apply the required Group Policies,</li>
  <li>Issue a temporary password and,</li>
  <li>Verify that the correct access has been provided.</li>
</ol>

<h4>🟠 Mover Process</h4>

<ol>
  <li>Receive an approved role or department change,</li>
  <li>Move the account to a new OU where required,</li>
  <li>Remove security groups associated with the previous role,</li>
  <li>Add the groups required for the new role,</li>
  <li>Update relevant identity attributes and,</li>
  <li>Verify that obsolete access has been removed.</li>
</ol>

<p>
The Mover process supports least privilege by ensuring users retain only the permissions needed for their current responsibilities.
</p>

<h4>🔴 Leaver Process</h4>

<ol>
  <li>Disable the departing user’s account,</li>
  <li>Prevent further authentication,</li>
  <li>Remove unnecessary security-group memberships,</li>
  <li>Revoke access to organisational resources,</li>
  <li>Move the account to the Disabled Users OU and,</li>
  <li>Retain the account according to organisational retention requirements.</li>
</ol>

<p>
The Leaver process reduces the risk of unauthorised access through accounts that are no longer required.
</p>

<h3>🔍 Auditing and Accountability</h3>

<p>
Advanced Audit Policy settings were configured to generate security events relating to authentication, account management, policy changes, and other relevant activities.
</p>

<p>
The audit configuration supports security monitoring, incident investigation, accountability, and the identification of unauthorised changes.
</p>

<h3>🔐 Security Principles Demonstrated</h3>

<ul>
  <li>Least privilege,</li>
  <li>Role-Based Access Control,</li>
  <li>Identity lifecycle management,</li>
  <li>Access governance,</li>
  <li>Separation of duties,</li>
  <li>Secure authentication,</li>
  <li>Application control,</li>
  <li>Security hardening,</li>
  <li>Policy-based administration and,</li>
  <li>Auditability and accountability.</li>
</ul>

<h3>🧰 Tools and Technologies</h3>

<ul>
  <li>Windows Server 2022,</li>
  <li>Active Directory Domain Services,</li>
  <li>Active Directory Users and Computers,</li>
  <li>Group Policy Management Console,</li>
  <li>AppLocker,</li>
  <li>Advanced Audit Policy Configuration,</li>
  <li>Windows PowerShell and,</li>
  <li>Oracle VirtualBox.</li>
</ul>

<h3>🧪 Validation Performed</h3>

<ol>
  <li>Verified successful domain and Domain Controller configuration,</li>
  <li>Confirmed the OU and security-group structure,</li>
  <li>Verified that all 12 user accounts were created correctly,</li>
  <li>Confirmed users were assigned to the correct OUs and groups,</li>
  <li>Used Group Policy Results to validate policy application,</li>
  <li>Verified password and account-lockout requirements,</li>
  <li>Tested Control Panel and Command Prompt restrictions,</li>
  <li>Validated AppLocker application restrictions,</li>
  <li>Confirmed removable-storage restrictions,</li>
  <li>Verified security-filtering exclusions and,</li>
  <li>Tested the Joiner-Mover-Leaver processes.</li>
</ol>

<h3>🧠 Key Learning Outcomes</h3>

<p>
This project provided practical experience in designing and administering an enterprise-style Active Directory IAM environment.
</p>

<p>
The lab demonstrated how identities are created, organised, governed, secured, monitored, updated, and eventually de-provisioned throughout their lifecycle.
</p>

<p>
The project also strengthened my understanding of how Active Directory, Group Policy, security groups, application controls, authentication policies, audit logging, and identity lifecycle processes work together to support enterprise Identity and Access Management.
</p>

<h3>⚠️ Disclaimer</h3>

<p>
This project was created for educational and professional portfolio purposes within a controlled virtual laboratory. The organisation, domain, users, and configurations shown are simulated and do not represent a production environment.
</p>

<h3>👤 Author</h3>

<p>
<strong>Saheed Bakare</strong><br>
IT Support Engineer | Cybersecurity Analyst | IAM & Cloud Security Practitioner
</p>
