# WEEK 7 (Security Audit and System Evaluation)
## 1. Purpose and Scope of the Security Audit
The purpose of a security audit aims at critically assessing the operating system security controls that have been employed throughout the coursework. Instead of merely relying on system configuration as a determinant of security, this security audit aims at objectively assessing the system’s resistance to attacks. The security audit covers areas of host security posture, network exposure, enforcement of access control, service minimization, and assessment of system security after remediation measures are taken.

This is the standard practice in the industry with respect to security, where the system is always being evaluated and improved.

## 2. Audit Methodology & Rationale
To make sure that all aspects of the system were covered, a layered approach to auditing was adopted as follows:

- Host-based evaluation for analyzing configuration vulnerabilities and insecure defaults
- Assessment of the network in order to detect the exposed services as well as the possible points of entry
- Access control verification for the purpose of proving enforcement as opposed to simple installation
- Service audit to decrease unnecessary attack surface
- Reassessment post-remediation for improvement measurement

This approach is consistent with the principle of defense in depth because it provides multiple independent controls for the system instead of using only one control mechanism.

## 3. Host-Based Security Evaluation
Host-based audits involve system configuration, authentication policy, file permissions, and updates. Automated audit tools enable a systematic and repeatable process to detect misconfigurations and deviations from best practices. The generated security score and recommendations allow for quantifiable comparison before and after the fix, and thus enable the measurement of improved security instead of mere description.

This illustrates that the state of operating system security is a dynamic process that needs to be constantly validated.

## 4. Network Security Assessment
The network assessment is a test of the network from an outside perspective in a controlled setting. Through the identification of the ports that are opened and the exposed services, this network assessment ensures that the operation of the firewalls is accurate. Few exposed services ensure that the network hardening is successful.

This is a very important point, as many real-world compromises have occurred due to unnecessary or misconfigured network services.

## 5. Access Control Enforcement
The mandatory access control mechanisms are analyzed to ensure that the security policies are being enforced. Unlike the traditional discretionary access control permissions, the mandatory access control will not allow the processes to do their tasks even if the processes are compromised. This is important to ensure that the services run within the predetermined limits.

This underlines the significance of policy enforcement over the reliance upon user permissions.

6. Service Audit and Principle of Least Exposure

The service audit is a process that reviews all the running services on a computer system with the objective of ensuring that each has a valid reason for its operation on the computer. Non-essential services are sources of complexity on a computer system as they increase the attack surface.

By justifying each running service on a computer system, the computer operates on the principle of least exposure.

It is the standard practice for professional system administration, as would be found in any production environment.

## 7. Post-Remediation Security
After the remediation process, the system is re-assessed to ensure that the identified vulnerabilities have been remediated. This is shown by the decrease in the number of warnings received, the increase in the scores received during the audit process, and the decrease in the number of exposed services. This shows that security hardening is a continuous process of assessment, remediation, and re-assessment.

This step is crucial to prove that the changes made have a positive effect.

## 8. Residual Risks and Limitations
Despite hardening, there are risks which remain. These risks include risks of possible misconfigurations in the future, depending on updates, as well as risks associated with virtualization. Recognition of risks associated with virtualization shows realistic risk analysis.

Identification of residual risk is a critical part of professional security risk evaluation.

## 9. Overall System Evaluation
The final system assessment confirms that the layered security controls of authentication hardening, firewall enforcement, mandatory access control, automated updates, as well as intrusion detection, function in a manner that collectively enhances the security of the system. This audit shows that the system's security, usability, as well as performance, have been well balanced.
