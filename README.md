
# 🔐 Script-Controlled ACL – Restrict Record Access Based on Field Value

<p align="center">
  <img src="https://img.shields.io/badge/Platform-ServiceNow-00A86B?style=for-the-badge&logo=servicenow&logoColor=white" alt="ServiceNow"/>
  <img src="https://img.shields.io/badge/Language-JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" alt="JavaScript"/>
  <img src="https://img.shields.io/badge/Project-Completed-success?style=for-the-badge" alt="Completed"/>
</p>

<p align="center">
  <b>A ServiceNow security project that uses scripted Access Control Lists (ACLs) to restrict record access based on field values and defined authorization conditions.</b>
</p>

---

## 📌 1. Project Overview

**Script-Controlled ACL** is a ServiceNow project developed and tested in a ServiceNow Developer Instance. It demonstrates how record-level access can be controlled using **Access Control Lists (ACLs)** and server-side JavaScript.

In many applications, different users require different levels of access to records. Allowing every user to view or modify every record can expose sensitive information.

This project addresses that challenge by implementing script-based access control rules. Access is evaluated according to the configured field values and security conditions, helping ensure that users can access only the records permitted by the defined rules.

### 🎯 Project Objectives

- Implement script-based ACLs in ServiceNow.
- Restrict record access based on selected field values.
- Apply conditional authorization rules.
- Prevent unauthorized users from accessing protected records.
- Understand how ServiceNow enforces record-level security.

## ✨ 2. Key Features

| Feature | Description |
|---|---|
| 🔐 Script-Controlled Security | Uses JavaScript conditions in ACL rules. |
| 📋 Field-Based Access | Evaluates selected field values to determine access. |
| 👤 User Authorization | Applies configured user and role conditions. |
| 🛡️ Record Protection | Restricts unauthorized record operations. |
| ⚙️ Dynamic Evaluation | Evaluates the configured security conditions when access is requested. |
| 🧪 Access Validation | Supports testing with permitted and restricted access scenarios. |

## 🛠️ 3. Technologies Used

- **Platform:** ServiceNow Developer Instance
- **Security Mechanism:** Access Control Lists (ACLs)
- **Scripting Language:** JavaScript
- **Environment:** ServiceNow platform and browser-based interface

## ⚙️ 4. System Workflow

The project follows this access-control workflow:

```text
       ┌──────────────────────┐
       │      User Login      │
       └──────────┬───────────┘
                  │
                  ▼
       ┌──────────────────────┐
       │  Requests a Record   │
       └──────────┬───────────┘
                  │
                  ▼
       ┌──────────────────────┐
       │  ServiceNow ACL Rule │
       └──────────┬───────────┘
                  │
                  ▼
       ┌──────────────────────┐
       │ Evaluate Field Value │
       │  and Security Rules  │
       └──────────┬───────────┘
                  │
                  ▼
       ┌──────────────────────┐
       │   Access Decision    │
       └──────────┬───────────┘
                  │
           ┌──────┴──────┐
           ▼             ▼
     ┌───────────┐ ┌───────────┐
     │   Allow   │ │   Deny    │
     │  Access   │ │  Access   │
     └───────────┘ └───────────┘
```

### 🔍 How It Works

1. A user attempts to access a record in ServiceNow.
2. The platform evaluates the applicable ACL rules.
3. The scripted condition checks the configured field values and authorization requirements.
4. The ACL script determines whether its access check passes.
5. ServiceNow enforces the applicable security rules and grants or denies access accordingly.

> **Note:** The final access decision depends on the applicable ACL configuration, including operation, roles, conditions, scripts, and other relevant security checks.

## 💻 5. Implementation

The project was implemented in a ServiceNow Developer Instance using the platform's Access Control configuration.

### Implementation Steps

1. Access the ServiceNow Developer Instance.
2. Open the Access Control (ACL) configuration.
3. Create or configure an ACL for the required table and operation.
4. Define the applicable roles and conditions, if required.
5. Add a server-side JavaScript script to evaluate the selected field value.
6. Configure the script to return the appropriate access result.
7. Save the ACL and test it using relevant user accounts and record scenarios.

### Illustrative ACL Script

The following example demonstrates the basic idea of field-based access control. Replace `u_access_level` and the field values with those used in your actual implementation.

```javascript
answer = false;

if (gs.hasRole('admin')) {
    answer = true;
} else if (current.u_access_level == 'public') {
    answer = true;
}
```

**Script explanation:**

- `answer = false;` initializes the access check as denied.
- `gs.hasRole('admin')` checks whether the user has the specified role.
- `current.u_access_level` reads the field value from the current record.
- `answer = true;` allows this ACL check to pass when a condition is satisfied.

*This is an illustrative example, not necessarily the exact script used in the completed project. The actual ACL script and field names depend on your implementation.*

## 🧪 6. Testing and Validation

The access-control logic can be validated using different users, field values, and record-access scenarios.

| Test Scenario | Expected Result |
|---|---|
| User meets the configured authorization condition | Access is permitted by the applicable ACL. |
| User does not meet the required field-value condition | Access is restricted by the applicable ACL. |
| Authorized administrator accesses a protected record | Access depends on the configured administrator permissions and applicable ACLs. |
| Record field value changes | Access is reevaluated against the configured rules. |

Testing should cover the relevant ACL operations, such as **read, write, create, and delete**, wherever those operations are included in the project.

## 🔒 7. Security Benefits

- Reduces the risk of unauthorized record access.
- Supports field-dependent access decisions.
- Provides more granular control over protected records.
- Helps enforce application security policies.
- Improves understanding of role-based and script-based authorization in ServiceNow.

## 📚 8. Learning Outcomes

By completing this project, I gained practical experience in:

- Configuring Access Control Lists in ServiceNow.
- Writing server-side JavaScript for security rules.
- Understanding record-level access control.
- Evaluating field values and user authorization.
- Testing access permissions in a ServiceNow Developer Instance.
- Applying security principles to enterprise applications.

## 🚀 9. Future Enhancements

- Extend the rules to support multiple field values.
- Introduce additional role-based authorization conditions.
- Add more detailed access-validation scenarios.
- Improve security auditing and documentation.
- Apply similar controls to other tables and business use cases.

## 👨‍💻 10. Project Information

| Detail | Information |
|---|---|
| Project Name | Script-Controlled ACL – Restrict Record Access Based on Field Value |
| Platform | ServiceNow Developer Instance |
| Project Type | Application Security / Access Control |
| Primary Technology | JavaScript |
| Status | Completed |

---

<p align="center">
  <b>Built with 🔐 ServiceNow Security and JavaScript</b>
  <br/>
  <i>Learning, implementing, and strengthening access control in enterprise applications.</i>
</p>

## 👥 Team Members

| Name | Role |
|---|---|
| **Bhuvaneshwaran G** | Team Lead |
| **Rohith Raja K** | Team Member |
| **Uthaya Kumar A** | Team Member |
| **Venuprasad K** | Team Member |

---

<p align="center">
  <b>🤝 Teamwork • Innovation • Learning</b>
  <br/>
  <i>Developed using ServiceNow Developer Instance</i>
</p>
