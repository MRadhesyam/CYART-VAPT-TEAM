<img width="608" height="218" alt="image" src="https://github.com/user-attachments/assets/fe66fef2-2f10-4d29-9a8c-0aff25871dd6" />**Overview**

This section documents the Reconnaissance phase of the VAPT lifecycle.
The goal of this phase was to gather publicly available information, identify exposed services, and map external assets related to the target using OSINT techniques.

**Tools Used**

Shodan – Internet-wide service discovery.
Maltego – Asset and relationship mapping.
Google (Manual OSINT) – Public information gathering.

**Step 1: Target Identification**

Before performing reconnaissance, a target scope was defined.

**Scope**

Target Type: Public IPs / Domains (OSINT only)
Recon Method: Passive reconnaissance (no direct interaction)

**Step 2: Service Discovery Using Shodan**

Shodan was used to identify publicly exposed services and network assets.

**Actions Performed**

Searched public IP ranges
Identified open ports and running services
Collected metadata such as service type and protocol

Shodan revealed multiple exposed services including DNS, HTTPS, and NAS management interfaces.

**Step 3: Open Ports & Services Identification**

The following services were identified during reconnaissance:
<img width="607" height="546" alt="image" src="https://github.com/user-attachments/assets/5b431988-452a-4541-ad47-d95d6a835fa6" />


**Step 4: Asset Mapping Using Maltego**

Maltego was used to perform asset mapping and identify relationships between domains, IPs, and services.

<img width="608" height="218" alt="image" src="https://github.com/user-attachments/assets/6ed06542-deb6-4db7-88b2-948c13d02281" />


Conclusion

The reconnaissance phase successfully mapped exposed services and external assets without directly interacting with the target. 
This information was essential for understanding the attack surface and guiding exploitation strategies in later stages of the VAPT process.
