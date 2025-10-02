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

The server team received remediation scripts and scan reports to address key vulnerabilities. This streamlined their efforts and prepared them for a follow-up review.  

<img width="635" alt="image" src="https://github.com/user-attachments/assets/bbf9478f-e1d1-4898-846e-b510ec8c6f72">

[Remediation Email](https://github.com/joshmadakor1/lognpacific-public/blob/main/misc/remediation-email.md)

---

### Step 8) Mock Meeting: Post-Initial Discovery Scan (Server Team)

The server team reviewed vulnerability scan results, identifying outdated software, insecure accounts, and deprecated protocols. The remediation packages were prepared for submission to the Change Control Board (CAB). 

<a href="https://youtu.be/0tjjFewxSNw" target="_"><img width="600" src="https://github.com/user-attachments/assets/03027c66-5f7c-42d0-b6dd-09d053c040b1"/></a>

[Meeting Video](https://youtu.be/0tjjFewxSNw)

---

### Step 9) Mock CAB Meeting: Implementing Remediations

The Change Control Board (CAB) reviewed and approved the plan to remove insecure protocols and cipher suites. The plan included a rollback script and a tiered deployment approach.  

<a href="https://youtu.be/zOFPkTa9kY8" target="_"><img width="600" src="https://github.com/user-attachments/assets/07164e63-fbce-471a-b469-29a6d41b7bb8"/></a>

[Meeting Video](https://youtu.be/zOFPkTa9kY8)

---
### Step 10 ) Remediation Effort

#### Remediation Round 1: Outdated Wireshark Removal

The server team used a PowerShell script to remove outdated Wireshark. A follow-up scan confirmed successful remediation.  
[Wireshark Removal Script](https://github.com/joshmadakor1/lognpacific-public/blob/main/automation/remediation-wireshark-uninstall.ps1)  

<img width="634" alt="image" src="https://github.com/user-attachments/assets/7b4f9ab2-d230-4458-ac0f-c0ff070ae79a">

[Scan 2 - Third Party Software Removal](https://drive.google.com/file/d/1UiwPPTtuSZKk02hiMyXf31pXUIeC5EWt/view?usp=drive_link)


#### Remediation Round 2: Insecure Protocols & Ciphers

The server team used PowerShell scripts to remediate insecure protocols and cipher suites. A follow-up scan verified successful remediation, and the results were saved for reference.  
[PowerShell: Insecure Protocols Remediation](https://github.com/joshmadakor1/lognpacific-public/blob/main/automation/toggle-protocols.ps1)
[PowerShell: Insecure Ciphers Remediation](https://github.com/joshmadakor1/lognpacific-public/blob/main/automation/toggle-cipher-suites.ps1)

<img width="630" alt="image" src="https://github.com/user-attachments/assets/0e96120d-8ec9-4f76-8e42-79c752200010">

[Scan 3 - Ciphersuites and Protocols](https://drive.google.com/file/d/1Qc6-ezQvwReCGUZNtnva0kCZo_-zW-Sm/view?usp=drive_link)


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
