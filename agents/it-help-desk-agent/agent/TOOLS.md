# Tools — IT Help Desk Agent

## IT Service Management (ITSM)

- **ServiceNow** — incident ticket creation, update, and resolution; service request submission; knowledge base article retrieval; escalation routing; SLA tracking; change request submission.
- **Jira Service Management** — incident and request queue management; asset tracking; problem management; knowledge base.
- **Zendesk / Freshservice** — alternative ITSM platforms used by smaller firms; ticket creation, status update, escalation.

## Identity & Access Management

- **Microsoft Entra ID (Azure AD)** — user account management (create, disable, unlock, group membership), MFA reset, conditional access policy status, license assignment, guest access management.
- **Okta** — SSO application access provisioning, MFA enrollment reset, group membership, app assignment, audit log review.
- **Google Workspace Admin** — account management, group membership, drive sharing settings, MFA reset.

## Legal Technology Platforms (Support Context)

- **NetDocuments / iManage** — user provisioning, folder permission changes, workspace creation, client/matter code setup, version recovery requests (escalated).
- **Clio / MyCase / Filevine** — user account setup, permission configuration, billing rate assignment, integration troubleshooting.
- **Relativity / Everlaw** — user provisioning, workspace creation, group permission assignment (escalated to e-discovery team for matter access).

## Endpoint & Remote Access

- **Microsoft Intune / JAMF** — device enrollment status, compliance policy status, remote wipe (escalated), software deployment status.
- **VPN (Cisco AnyConnect / Palo Alto GlobalProtect)** — connection troubleshooting guidance, certificate renewal process, escalation to network team.

## Workspace

- **workspace_write** — save support ticket summaries and escalation records to `/sandbox/.openclaw/workspace/` for audit trail.

## Data Sources

### ITSM Records

- **ServiceNow / Jira / Zendesk** — incident records (ticket ID, requester, category, subcategory, description, priority, assigned team, status, created date, resolved date, resolution notes, SLA status), service request records (request ID, requester, request type, business justification, approver, approval status, fulfillment status), knowledge articles (article ID, title, category, content, last reviewed date, view count)

### Identity & Directory

- **Azure AD / Okta** — user records (user ID, display name, email, title, department, manager, account status, MFA enrolled, last login, licenses assigned, group memberships), group records (group name, type, membership list, owner), application assignments (app name, user, access level, last reviewed), audit logs (action, actor, target, timestamp, IP address, result)
- **Firm directory (LDAP/HR)** — staff name, title, department, office, manager, start date, employment status; used to validate access requests against role

### Device & Endpoint

- **Intune / JAMF** — device records (device ID, device name, owner, OS version, compliance status, encryption status, last check-in, apps installed), compliance policy results (policy name, device, result, non-compliant setting if any)

### Legal Technology Access

- **NetDocuments / iManage provisioning** — user access records (user ID, workspace access, group memberships, access level, provisioned date, last access date), cabinet/database assignments
- **Practice management user records** — user ID, name, role, billing rate, access level, module permissions, last login, account status

### Security & Incidents

- **Security incident log** — incident ID, reported by, date, incident type (phishing, data loss, unauthorized access, malware), affected systems, response actions taken, escalation path, resolution, post-incident review date
