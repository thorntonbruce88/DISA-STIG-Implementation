# Vulnerability Management Program Implementation
In this project, we simulate the implementation of a comprehensive vulnerability management program, from inception to completion.

_**Inception State:**_ the organization has no existing policy or vulnerability management practices in place.

_**Completion State:**_ a formal policy is enacted, stakeholder buy-in is secured, and a full cycle of organization-wide vulnerability remediation is successfully completed.

---

<img width="1000" alt="image" src="https://github.com/user-attachments/assets/cfc5dbcf-3fcb-4a71-9c13-2a49f8bab3e6">

# Technology Utilized
- Tenable (enterprise vulnerability management platform)
- Azure Virtual Machines (Nessus scan engine + scan targets)
- PowerShell & BASH (remediation scripts)

---


# Table of Contents

- [Vulnerability Management Policy Draft Creation](#vulnerability-management-policy-draft-creation)
- [Mock Meeting: Policy Buy-In (Stakeholders)](#step-2-mock-meeting-policy-buy-in-stakeholders)
- [Policy Finalization and Senior Leadership Sign-Off](#step-3-policy-finalization-and-senior-leadership-sign-off)
- [Mock Meeting: Initial Scan Permission (Server Team)](#step-4-mock-meeting-initial-scan-permission-server-team)
- [Initial Scan of Server Team Assets](#step-5-initial-scan-of-server-team-assets)
- [Vulnerability Assessment and Prioritization](#step-6-vulnerability-assessment-and-prioritization)
- [Distributing Remediations to Remediation Teams](#step-7-distributing-remediations-to-remediation-teams)
- [Mock Meeting: Post-Initial Discovery Scan (Server Team)](#step-8-mock-meeting-post-initial-discovery-scan-server-team)
- [Mock CAB Meeting: Implementing Remediations](#step-9-mock-cab-meeting-implementing-remediations)
- [Remediation Round 1: Outdated Wireshark Removal](#remediation-round-1-outdated-wireshark-removal)
- [Remediation Round 2: Insecure Protocols & Ciphers](#remediation-round-2-insecure-protocols--ciphers)
- [Remediation Round 3: Guest Account Group Membership](#remediation-round-3-guest-account-group-membership)
- [Remediation Round 4: Windows OS Updates](#remediation-round-4-windows-os-updates)
- [First Cycle Remediation Effort Summary](#first-cycle-remediation-effort-summary)

---

### Vulnerability Management Policy Draft Creation

This phase focuses on drafting a Vulnerability Management Policy as a starting point for stakeholder engagement. The initial draft outlines scope, responsibilities, and remediation timelines, and may be adjusted based on feedback from relevant departments to ensure practical implementation before final approval by upper management.  
[Draft Policy](https://docs.google.com/document/d/1CLSWm1_9JL1oUqgyNNwtPXW6FzXJ7ddVnSAUQTyqC8I/edit?usp=drive_link)

---

### Step 2) Mock Meeting: Policy Buy-In (Stakeholders)

Mock Project: Remediation Policy Rollout Meeting

📅 Date: (Mock date)

👥 Attendees: Josh, Jimmy

📝 Meeting Type: Policy Draft Review (Security Remediation Program)

📖 Meeting Recap 

This morning, Josh and Jimmy held a focused meeting to review the draft Remediation Policy. Jimmy confirmed that the draft was well-structured but raised a concern: with current staffing levels, the proposed 48-hour remediation requirement for critical vulnerabilities would be difficult to achieve.

Josh acknowledged this challenge and proposed a compromise — extending the remediation window for most critical vulnerabilities to one week, while reserving the 48-hour window exclusively for urgent, high-impact zero-day threats. Jimmy agreed that this adjustment was practical and supported operational feasibility.

Additionally, Jimmy requested a grace period during the initial rollout to allow teams time to adapt. Josh confirmed that once the policy is finalized, all departments will have a six-month adjustment period before strict enforcement begins.

The meeting concluded on a positive note, with both parties emphasizing the value of collaboration and expressing appreciation for being included in the decision-making process.

🔑 Key Highlights

Issue Identified: Current staffing cannot meet a strict 48-hour remediation requirement.

Compromise Reached:

1 week for standard critical vulnerabilities.

48 hours reserved for zero-day vulnerabilities only.

Transition Period: Six months of adjustment after policy finalization before enforcement.

Outcome: Agreement reached with a collaborative, solution-oriented approach.

Tone of Meeting: Short, effective, and inclusive — ensuring all departments feel part of the solution.

✅ Outcome

The team reached a balanced agreement that ensures security standards remain strong while also accounting for staffing realities. This compromise not only improves adoption feasibility but also fosters stronger collaboration across departments.

---

### Step 3) Policy Finalization and Senior Leadership Sign-Off

After gathering feedback from the server team, the policy is revised, addressing aggressive remediation timelines. With final approval from upper management, the policy now guides the program, ensuring compliance and reference for pushback resolution.  
- 📄 [Vulnerability Management Policy](https://docs.google.com/document/d/1cANtAQ6hty16fBSA7lt038e-DRWX9VHgGHREh4ZbK48/edit?tab=t.0#heading=h.5clv4qeychvj)



---

### Step 4) Mock Meeting: Initial Scan Permission (Server Team)

Vulnerability Scan Kickoff Meeting

📅 Date: (Mock date)

👥 Attendees: Josh, Jimmy

📝 Meeting Type: Security Operations Discussion

📖 Meeting Recap 

This morning, Josh and Jimmy met to discuss the kickoff of vulnerability scanning under the newly implemented Vulnerability Management Policy. Josh explained the plan to conduct weekly credentialed scans across the server infrastructure, estimating that scanning all 2,200 assets would take approximately 4–6 hours.

Jimmy raised valid concerns regarding resource utilization during scans and the security risks of providing administrative credentials to all systems. Josh clarified that the scan engine generates test traffic to assess vulnerabilities, including checks for outdated software, insecure protocols, and weak cipher suites. He also emphasized that scans should not cause downtime.

To address these concerns, both parties agreed to start with a single-server test scan to observe system performance. For credentials, Josh suggested a just-in-time access approach, where temporary Active Directory accounts are enabled only during scans and then disabled immediately afterward. Jimmy agreed and committed to having Susan begin work on automation for account provisioning to streamline this process.

The meeting concluded with agreement on a phased rollout, starting with a pilot scan, and a plan to reconvene once the credentials are prepared.

🔑 Key Highlights

Plan: Weekly credentialed vulnerability scans across ~2,200 assets.

Duration Estimate: 4–6 hours per full scan cycle.

Concerns Raised:

Potential server performance impact.

Risks of providing broad admin access.

Mitigations:

Start with a single-server scan as a test.

Use temporary Active Directory accounts (just-in-time access model).

Action Item: Susan to automate account provisioning workflow.

Outcome: Agreement to pilot the process before scaling to full infrastructure.

✅ Outcome

The team aligned on a phased scanning approach that balances security requirements with operational safety. By piloting on a single server and using controlled, temporary credentials, the team ensures both confidence in the process and a smoother transition to organization-wide vulnerability management.

---

### Step 5) Initial Scan of Server Team Assets

In this phase, an insecure Windows Server is provisioned to simulate the server team's environment. After creating vulnerabilities, an authenticated scan is performed, and the results are exported for future remediation steps.  

<<img width="717" height="475" alt="image" src="https://github.com/user-attachments/assets/a4985bb9-189b-4e4a-b33c-25cf7209056e" />
>

- 🔍 [Vulnerability Management Baseline Scan](https://docs.google.com/document/d/1NYHIWNLFujn9Yv4wuFa_1AhXIrAh-ddqKFmM4yJBJ5c/edit?tab=t.0)






---

### Step 6) Vulnerability Assessment and Prioritization

We assessed vulnerabilities and established a remediation prioritization strategy based on ease of remediation and impact. The following priorities were set:

1. Third Party Software Removal (Wireshark)
2. Windows OS Secure Configuration (Protocols & Ciphers)
3. Windows OS Secure Configuration (Guest Account Group Membership)
4. Windows OS Updates

---

### Step 7) Distributing Remediations to Remediation Teams

Email sent:

Subject: Vulnerability Remediation Scripts – Testing and Deployment

Hi Team,

Following our initial vulnerability scan and assessment, we have developed a set of remediation scripts to assist with addressing key findings. These scripts are designed for seamless integration into deployment platforms such as SCCM.

Before rolling them out in production, please ensure thorough testing in a controlled environment.

🔧 Remediation 

Third-Party Software Removal (Wireshark)

-----> Uninstall Wireshark: Script: https://github.com/joshmadakor1/lognpacific-public/blob/main/automation/remediation-wireshark-uninstall.ps1

     

Windows OS Secure Configuration – Insecure Protocols

-----> Disable the insecure protocols, enable secure ones: Script: https://github.com/joshmadakor1/lognpacific-public/blob/main/automation/toggle-protocols.ps1 


Windows OS Secure Configuration – Insecure Cipher Suites

-----> Disable the insecure ciphers, enable secure ones: Script: https://github.com/joshmadakor1/lognpacific-public/blob/main/automation/toggle-cipher-suites.ps1 


Windows OS Secure Configuration – Guest Account Group Membership

-----> Remove the “Guest” account from the “Administrators” Security Group: Script: https://github.com/joshmadakor1/lognpacific-public/blob/main/automation/toggle-guest-local-administrators.ps1

Windows OS Updates - Please run Windows Update, this may need multiple attempts.


Restart the server following each remediation.

If you encounter any issues during testing or require modifications, please don’t hesitate to reach out.

Best regards,

Bruce Thornton

Security Analyst, 
Governance, Risk, and Compliance

---

### Step 8) Mock Meeting: Post-Initial Discovery Scan (Server Team)

The server team reviewed vulnerability scan results, identifying outdated software, insecure accounts, and deprecated protocols. The remediation packages were prepared for submission to the Change Control Board (CAB). 

Mock Project: Post-Discovery Scan Review Meeting

📅 Date: (Mock date)

👥 Attendees: Josh, Jimmy

📝 Meeting Type: Security Vulnerability Review with Server Team

📖 Meeting Recap 

Josh and Jimmy met to review the results of the initial discovery vulnerability scan across the server environment. Jimmy confirmed that the scans ran smoothly with no outages or noticeable performance issues, aside from the expected open connections. Both agreed that resource utilization would continue to be monitored, but no significant risks were anticipated.

Josh then presented the vulnerability findings. The most common issue stemmed from outdated Wireshark installations, which appeared across multiple servers. Additionally, Josh discovered that the local guest account was a member of the local administrators group, raising a serious configuration concern. Other findings included deprecated TLS protocols (1.0 and 1.1), medium-strength cipher suites, and some issues potentially resolved through routine Windows Updates (e.g., Edge Chromium updates). Self-signed certificates were noted but considered low priority.

Jimmy agreed that the major focus areas should be removing Wireshark, addressing insecure protocols and cipher suites, and removing the guest account from administrative groups. He noted that most servers share the same configuration baseline, meaning remediation should be more efficient.

The team also confirmed that patch management is already in place for Windows Updates, so vulnerabilities addressed through normal patch cycles were not a concern. Josh committed to building remediation packages for the server team and to return with recommendations ahead of the next Change Control Board meeting.

🔑 Key Highlights

Scan Results:

No outages or major performance issues during the scan.

Monitoring confirmed minimal impact on server resources.

Findings:

Outdated Wireshark installations on multiple servers.

Guest account improperly assigned to local administrators group.

Deprecated TLS protocols (1.0 & 1.1) in use.

Medium-strength cipher suites detected.

Some vulnerabilities likely resolved by Windows Updates.

Self-signed certificates noted, low priority.

Next Steps:

Remove Wireshark from servers.

Remediate guest account group membership.

Disable insecure protocols and cipher suites.

Leverage existing patch management for update-related vulnerabilities.

Prepare remediation packages for streamlined deployment.

✅ Outcome

The server team and security analyst reached alignment on the priority vulnerabilities requiring remediation. The phased approach—starting with Wireshark removal, guest account fixes, and protocol hardening—ensures that risks are addressed efficiently without operational disruption. Josh will prepare remediation packages and return with a proposal before the next Change Control Board session.

---

### Step 9) Mock CAB Meeting: Implementing Remediations

The Change Control Board (CAB) reviewed and approved the plan to remove insecure protocols and cipher suites. The plan included a rollback script and a tiered deployment approach.  

Mock Project: CAB Meeting – Vulnerability Remediation Approval

📅 Date: (Mock date)

👥 Attendees: Change Advisory Board, Josh (Risk), Jimmy (Infrastructure)

📝 Meeting Type: Change Advisory Board (CAB) Review


📖 Meeting Recap

During this week’s CAB meeting, the server team presented two planned vulnerability remediations: removal of insecure protocols and removal of insecure cipher suites. While Jimmy from the Infrastructure team was initially expected to provide the technical overview, he deferred to Josh from the Risk department, who had developed the remediation solution.

Josh explained that the issue stems from outdated or deprecated cryptographic protocols and cipher suites still being available on servers. If left enabled, these could allow systems to negotiate insecure connections. The solution involves a PowerShell script that updates the Windows registry, disabling weak protocols and ciphers while ensuring that only secure, modern standards remain enabled.

The CAB raised a key question regarding rollback planning. Josh confirmed that the team had designed a tiered deployment strategy (pilot → pre-production → full production) and also developed an automated rollback script to restore original settings if unexpected issues occur. This approach reassured the board that risks were mitigated and the change was safe to move forward.

The meeting concluded with no further objections, and the CAB approved the proposed remediation changes for deployment.

🔑 Key Highlights

Planned Changes:

Disable insecure cryptographic protocols.

Disable deprecated cipher suites.

Technical Approach:

PowerShell scripts modify Windows registry keys.

Secure, modern algorithms enabled by default.

Risk Mitigation:

Tiered rollout strategy: pilot → pre-production → full deployment.

Automated rollback scripts provided for rapid recovery.

CAB Concerns Addressed:

Ensured rollback capability was available.

Verified change scope was limited to registry updates.

✅ Outcome

The CAB approved the remediation plan, recognizing that the solution was low-risk, well-documented, and fully reversible. With rollback safeguards and phased deployment in place, the team is cleared to move forward with implementation.

---
### Step 10 ) Remediation Effort

#### Remediation Round 1: Outdated Wireshark Removal

The server team used a PowerShell script to remove outdated Wireshark. 

Initial Scan:

<img width="787" height="728" alt="image" src="https://github.com/user-attachments/assets/397dda84-c7a9-4770-8200-94d2facd95b9" />


A follow-up scan confirmed successful remediation.

<img width="698" height="386" alt="image" src="https://github.com/user-attachments/assets/4bfc5640-35ad-44a3-be5f-3cbadb61ca05" />

[Wireshark Removal Script](https://github.com/joshmadakor1/lognpacific-public/blob/main/automation/remediation-wireshark-uninstall.ps1)  




#### Remediation Round 2: Insecure Protocols & Ciphers

The server team used PowerShell scripts to remediate insecure protocols and cipher suites. A follow-up scan verified successful remediation, and the results were saved for reference.  
[PowerShell: Insecure Protocols Remediation](https://github.com/joshmadakor1/lognpacific-public/blob/main/automation/toggle-protocols.ps1)
[PowerShell: Insecure Ciphers Remediation](https://github.com/joshmadakor1/lognpacific-public/blob/main/automation/toggle-cipher-suites.ps1)

<img width="701" height="410" alt="image" src="https://github.com/user-attachments/assets/2ca2efae-f442-4e3f-a28a-5a1bf5924037" />

[Scan 3 - Ciphersuites and Protocols] https://docs.google.com/document/d/1gB40h11Roi6XZ3hEBUKkIvyXA-io7spPSusehpdI95E/edit?tab=t.0


#### Remediation Round 3: Guest Account Group Membership

The server team removed the guest account from the administrator group. A new scan confirmed remediation, and the results were exported for comparison.  
[PowerShell: Guest Account Group Membership Remediation](https://github.com/joshmadakor1/lognpacific-public/blob/main/automation/toggle-guest-local-administrators.ps1)  

<img width="627" alt="image" src="https://github.com/user-attachments/assets/870a3eac-3398-44fe-91c0-96f3c2578df4">

[Scan 4 - Guest Account Group Removal](https://drive.google.com/file/d/1jVgikjfrV1YjOcL3QRT_oUB0Y82w22V7/view?usp=drive_link)


#### Remediation Round 4: Windows OS Updates

Windows updates were re-enabled and applied until the system was fully up to date. A final scan verified the changes  

<img width="627" alt="image" src="https://github.com/user-attachments/assets/870a3eac-3398-44fe-91c0-96f3c2578df4">

[Scan 5 - Post Windows Updates](https://drive.google.com/file/d/1tmDjeHl5uiGitRwWy8kFRi33q-nGi1Zt/view?usp=drive_link)

---

### First Cycle Remediation Effort Summary

The remediation process reduced total vulnerabilities by 80%, from 30 to 6. Critical vulnerabilities were resolved by the second scan (100%), and high vulnerabilities dropped by 90%. Mediums were reduced by 76%. In an actual production environment, asset criticality would further guide future remediation efforts.  

<img width="1920" alt="image" src="https://github.com/user-attachments/assets/51f0aae8-7f36-4d90-b29f-5257e57155f9">

[Remediation Data](https://docs.google.com/spreadsheets/d/1FTtFfZYmFsNLU6pm8nTzsKyKE-d2ftXzX_DPwcnFNfA/edit?gid=0#gid=0)

---

### On-going Vulnerability Management (Maintenance Mode)

After completing the initial remediation cycle, the vulnerability management program transitions into **Maintenance Mode**. This phase ensures that vulnerabilities continue to be managed proactively, keeping systems secure over time. Regular scans, continuous monitoring, and timely remediation are crucial components of this phase. (See [Finalized Policy](https://docs.google.com/document/d/1rvueLX_71pOR8ldN9zVW9r_zLzDQxVsnSUtNar8ftdg/edit?usp=drive_link) for scanning and remediation cadence requirements.)

Key activities in Maintenance Mode include:
- **Scheduled Vulnerability Scans**: Perform regular scans (e.g., weekly or monthly) to detect new vulnerabilities as systems evolve.
- **Patch Management**: Continuously apply security patches and updates, ensuring no critical vulnerabilities remain unpatched.
- **Remediation Follow-ups**: Address newly identified vulnerabilities promptly, prioritizing based on risk and impact.
- **Policy Review and Updates**: Periodically review the Vulnerability Management Policy to ensure it aligns with the latest security best practices and organizational needs.
- **Audit and Compliance**: Conduct internal audits to ensure compliance with the vulnerability management policy and external regulations.
- **Ongoing Communication with Stakeholders**: Maintain open communication with teams responsible for remediation, ensuring efficient coordination.

By maintaining an active vulnerability management process, organizations can stay ahead of emerging threats and ensure long-term security resilience.
