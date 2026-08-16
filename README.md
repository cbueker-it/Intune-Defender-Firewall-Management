**Intune-Defender-Firewall-Management**

Microsoft Intune lab documenting centralized Microsoft Defender Firewall policy deployment, security-groups, and endpoint verification on a Windows 11 Pro virtual machine.

**Baseline Firewall State**

* Establishes the Windows Defender Firewall state before centralized Intune policy management.
* Shows the Domain, Private, and Public firewall profiles were already enabled.
* Shows `DefaultInboundAction` and `DefaultOutboundAction` as `NotConfigured`.
* Shows `LogBlocked: False`, establishing that dropped-packet logging had not yet been configured through the Intune policy.

<img src="image1/01-firewall-baseline-before-intune.png" alt="Windows Defender Firewall baseline before Intune policy deployment" width="800"/>

**Intune Device Security Group**

* Creates a Security group to target the Windows 11 lab endpoint with Intune policy.
* Uses an assigned membership type so the intended endpoint can be explicitly included.
* Confirms one device was selected as a member of the group.
* Provides a reusable group-based targeting structure for centralized endpoint management.

<img src="image1/02-intune-device-security-group.png" alt="Microsoft Intune device security group for Windows 11 lab endpoint" width="800"/>

**Intune Policy Deployment Success**

* Confirms the Windows 11 Pro Defender Firewall policy successfully reached the targeted endpoint.
* Shows one successful deployment with zero errors, conflicts, or deployments still in progress.
* Confirms the `Intune-Windows11-Lab-Devices` group is included in the policy assignment.
* Provides Intune-side confirmation before validating the resulting configuration directly on Windows.

<img src="image1/06-intune-policy-deployment-success.png" alt="Microsoft Intune Defender Firewall policy deployment success" width="800"/>

**Intune Firewall Policy Settings**

* Reviews the Defender Firewall settings configured through the Microsoft Intune admin center.
* Confirms the Domain Network Firewall is enabled.
* Confirms dropped-packet logging is enabled for additional troubleshooting and security visibility.
* Shows the centrally defined firewall configuration from the Intune administrative side.

<img src="image1/04-intune-firewall-settings.png" alt="Microsoft Intune Defender Firewall policy settings" width="800"/>

**Windows Security Administrator Management**

* Moves from the Intune administration portal to the managed Windows 11 endpoint for local verification.
* Windows Security reports that the Microsoft Defender Firewall setting is managed by an administrator.
* Demonstrates that the endpoint recognizes the centrally applied organizational firewall policy.

<img src="image1/05-windows-security-admin-managed.png" alt="Windows Security showing Microsoft Defender Firewall managed by administrator" width="800"/>

**Windows Defender Firewall GUI Validation**

* Uses Windows Defender Firewall with Advanced Security to inspect the effective configuration directly on the endpoint.
* Confirms the Domain profile uses `Block (default)` for inbound connections.
* Confirms dropped-packet logging is enabled.
* Provides GUI-based validation that the centrally configured Intune policy became effective on Windows.

<img src="image1/03-windows-firewall-gui-validation.png" alt="Windows Defender Firewall with Advanced Security policy validation" width="800"/>

**PowerShell ActiveStore Validation**

* Queries the Windows Firewall `ActiveStore` to validate the effective system-level firewall configuration.
* Confirms Domain, Private, and Public firewall profiles are enabled.
* Verifies the effective inbound action is `Block` and the outbound action is `Allow` across all three profiles.
* Confirms `LogBlocked: True`, demonstrating that dropped-packet logging became active.
* Completes the before-and-after validation by comparing the effective policy with the original firewall baseline.

<img src="image1/07-powershell-activestore-validation.png" alt="PowerShell ActiveStore validation of Microsoft Defender Firewall policy" width="800"/>
