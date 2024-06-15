# TIDSR Security Alert: Potential Malware in Minecraft Mod "eclipse-1.0.0+1.20.5.jar"

## File Details
- **Target:** eclipse-1.0.0+1.20.5.jar
- **Size:** 152KB
- **MD5:** 79aff2ec3f01ee6c52d3c37599b3e959
- **SHA1:** 7d8c09a16a739404b3979a363d78ad51819a2ffd
- **SHA256:** d650c1ed5b82e79896352ef07c7f3a7a482341454dedd4458f2722762eec1469
- **SHA512:** 03017f42abf9c059a156790f5df449da96d10ccd01fa41c913b27ce666277e01db0457967bbfe860328ddd889b8ce9ba36b934287127fe299fc4344228d8c3c9
- **SSDEEP:** 1536:8lYohj8RdsOaM4xxKMG+woXPqjH3FNKcwNm5Yh1yoFGOzIx13V/VbvsFw1rzYEql:twlM4xTlXPMDMakm/l/Vb71rEDIJ3ql

## File Info
- **SHA256:** d650c1ed5b82e79896352ef07c7f3a7a482341454dedd4458f2722762eec1469

### Observations:
- `jumpingcooldown` in `com/entity/eclipse/mixin/ILivingEntityMixin.class`
  - **Possible obfuscation:** Many 15-character functions

- `printstacktrace` in `com/entity/eclipse/utils/SaveManager.class`
  - **Possible obfuscation:** Many 15-character functions

- `compressedbytes` in `com/entity/eclipse/utils/SaveManager.class`
  - **Possible obfuscation:** Many 15-character functions

- `java/lang/runtimeexception` in `com/entity/eclipse/commands/VClip.class`
  - **Excessive exception handling can indicate obfuscation**

## Risk Score
**7/10**

## Suspicion Score
**63/100**

## Discovery
Malware Configuration

## Signatures
- **Modifies file permissions:** 1 TTPs, 1 IoCs
- **Suspicious use of WriteProcessMemory:** 2 IoCs

## Processes Involved
1. **java.exe**
   - **Description:** PID 3764 wrote to memory of PID 4720
   - **Target Process:** icacls.exe

## Process Paths
- **Java Execution:**
  - `C:\Program Files (x86)\Common Files\Oracle\Java\javapath\java.exe`
  - Command: `java -jar C:\Users\Admin\AppData\Local\Temp\eclipse-1.0.0+1.20.5.jar`
  - PID: 3764

- **ICACLS Execution:**
  - `C:\Windows\system32\icacls.exe`
  - Command: `C:\Windows\system32\icacls.exe C:\ProgramData\Oracle\Java\.oracle_jre_usage /grant "everyone":(OI)(CI)M`
  - PID: 4720

## Network Activity
- Multiple DNS requests to `8.8.8.8:53`

## MITRE ATT&CK Techniques
- **File and Directory Permissions Modification:** T1222

## Downloads
- **File:** `C:\ProgramData\Oracle\Java\.oracle_jre_usage\3903daac9bc4a3b7.timestamp`
  - **Filesize:** 46B
  - **MD5:** a7763e842d8fbfe807f768e774842e28
  - **SHA1:** 9dabb15ce398a6442b950570955af37f4811023b
  - **SHA256:** f5a5e846f6f24f733c419e9aaed8bf420118752dd36c8f02e21443b74c648b16
  - **SHA512:** 7db283e844c40fc30c0f37039885800ef1d2ab5e736e1a590e89a3f80f7ad7d8e4bd6d448f69fa101e8e14ff1f836c750f4b6786da3355c81a00945a2544f5e4

## Memory Dumps
- `memory/3764-2-0x0000026C83340000-0x0000026C835B0000-memory.dmp` (2.4MB)
- `memory/3764-12-0x0000026C81AC0000-0x0000026C81AC1000-memory.dmp` (4KB)
- `memory/3764-14-0x0000026C81AC0000-0x0000026C81AC1000-memory.dmp` (4KB)
- `memory/3764-15-0x0000026C83340000-0x0000026C835B0000-memory.dmp` (2.4MB)

## Antivirus Detection
This mod was tested against multiple antivirus programs and found undetected by all, including major vendors such as Avast, McAfee, Microsoft, and Kaspersky.

## Detailed Report Links
- **VirusTotal Scan Report:** [View Report](https://www.virustotal.com/gui/file/d650c1ed5b82e79896352ef07c7f3a7a482341454dedd4458f2722762eec1469/detection)
- **TRIAge Scan Report:** [View Report](https://tria.ge/240517-vv3sjsab73/behavioral1)

## Recommendations from TIDSR
1. **Quarantine and Analyze:**
   - Immediately quarantine the affected system and isolate the file `eclipse-1.0.0+1.20.5.jar` for further analysis.

2. **Monitor and Investigate:**
   - Monitor network traffic for unusual DNS requests and HTTPS connections.
   - Investigate any suspicious changes to file and directory permissions.

3. **Patch and Secure:**
   - Apply the latest security patches to your system.
   - Ensure that Java installations and other software are up to date.

4. **Review Permissions:**
   - Review and correct any unauthorized permission changes made by `icacls.exe`.

5. **Consult Security Experts:**
   - If unsure about the steps to take or the severity of the infection, consult with cybersecurity professionals for a thorough analysis and response plan.

## If You Have Used the Mod
If you have already used the mod "eclipse-1.0.0+1.20.5.jar," follow these steps:

1. **Uninstall the Mod:**
   - Remove the mod from your Minecraft installation.

2. **Run a Full System Scan:**
   - Use a reputable antivirus program to perform a full system scan to detect and remove any potential malware.

3. **Change Passwords:**
   - Change passwords for all accounts that might have been accessed from the infected system.

4. **Monitor for Suspicious Activity:**
   - Keep an eye on your accounts and systems for any unusual activity.

5. **Consult a Professional:**
   - Consider consulting a cybersecurity expert for a thorough system inspection and cleanup.

Staying vigilant and proactive is crucial in protecting your systems from potential threats posed by seemingly benign files such as Minecraft mods.

---

**The Independent Security Research Organisation (TIDSR)** aims to empower individuals and organizations by providing comprehensive security analysis and actionable recommendations.