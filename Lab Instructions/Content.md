!INSTRUCTIONS [ ](https://raw.githubusercontent.com/LODSContent/SkillableLabSolutions/main/Header.md)

:::module(module=Environment)

### End User Licensing Agreement

By using this lab solution, you agree to the terms outlined in the End User License Agreement (EULA), which you can review by following this ^[link][Reference Link].

> [Reference Link]:
> !instructions [ ](https://raw.githubusercontent.com/LODSContent/SkillableLabSolutions/main/EULA%20062424.md)

### Environment

| Item | Detail |
| :--- | :----- |
| **Description** | Windows 11 Desktop with Edge |
| **Operating System** | Windows 11 Desktop |
| **Software/Configuration** | Default installation with Desktop Experience, no supplemental software |
| **Platform/Fabric** | Hyper-V Virtual Machine |
| **Hardware** | 4 CPU, 16GB Memory |
| **Networking** | Internet access provided |
|  |  |

:::


:::module(module=Access&#32and&#32Credentials)

### Access and Credentials

| Item | Detail |
| :--- | :----- |
| User | +++@lab.VirtualMachine(Workstation1).Username+++ |
| Password | +++@lab.VirtualMachine(Workstation1).Password+++ |
|  |  |

:::


:::module(module=Software&#32and&#32Updates)

### Software and Updates

| Software Product | Install Date or Version | Configuration Notes |
| :--------------- | :---------------------- | :------------------ |
| Windows 11 Desktop | 23H2 | Installed with the latest patches and updates. |
|  |  |


> [!note] Software patches current as of 08/13/2024.

:::


:::module(module=Skillable&#32Optimizations)

### Skillable Optimizations

For more information, see the [Optimization](https://docs.skillable.com/docs/skillable-virtual-machine-optimization-recommendations) documentation.

:::


:::module(module=Software&#32Licensing)

### Software Licensing

Skillable can optionally provide license activation for certain operating systems or Microsoft software products. If you would like to discuss license option please contact your account executive. All other licensing is the responsibility of the user of this template.

For more information, see the [Windows licensing](https://docs.skillable.com/docs/windows-licensing) documentation.

> [+]How do I activate Microsoft Windows?
> 
> Activating Windows in labs can be achieved one of three ways depending on your use cases:
>
> 1. Rearm: When the software environment is complete. Opening an administrative command or PowerShell prompt and using the command `slmgr -rearm` will reset the Windows activation clock.
> 2. Use a Multiple Activation Key (MAK): You can add your own Microsoft Windows Product Key to license the Windows software. This can be added using the Activation tool in Settings.
> 3. Using a Skillable License: Skillable can activate and license the Windows VM automatically. If you have already signed up for a SPLA agreement just ensure the production copies of the Lab Profiles are saved to your  **<CompanyName> - Production - SPLA** organization. This will automatically license the Windows VM for you. If you do not have a SPLA agreement, please see the [Windows and Office licensing](https://docs.skillable.com/docs/windows-licensing) documentation.

:::


:::module(module=Using&#32this&#32Template)

## Using this Template

> [+Alert]Saving changes
> 
> If you customize the software environment the changes need to be saved to become persistent. Review the section below on committing changes to see how to do this.

> [+]Any restrictions on the software I can install and use?
> 
> Any software that meets Skillable's lab software usage policy and does not contravene the [Terms and Conditions](https://www.skillable.com/company/legal-and-security/terms-and-conditions/) may be installed.

> [+]How do I modify, add content to the environment?
> 
> The environment can be modified just like a normal operating system. Adding software can be achieved in several ways. The size of the application may impact the method you choose. Here are the options, in preferred order to minimize negative impact on the VM's performance:
>
> 1. For applications less than 2GB, use the **Load Files** on the Settings menu
> 2. For applications greater than 2GB, upload an ISO file into the Skillable storage using the Skillable [Manage Storage tool](https://labondemand.com/Storage) on the Studio Admin page
> 3. If the VM has Internet access, the application can be downloaded from the Internet, which is best for small applications of a few MB's in size. Also, use InPrivate/Incognito browsing to leave a minimum browser impact in the VM
>
> If you make any changes to the environment, they are not saved until **committed**.

> [+]Operating system updates and patches
> 
> To ensure optimal performance, Windows software updating (including applications) using the Windows Update service is disabled. This environment and its applications were updated based on the published date unless otherwise noted in the [software and updates](#software-and-updates) section.
> 
> If you wish to install additional updates you may do so manually, or enable Windows Update by reversing the instructions in the [Skillable optimization documentation](https://docs.skillable.com/docs/skillable-virtual-machine-optimization-recommendations).
> 
> If you enable Windows Update, it is highly recommended that you follow the same instructions to disable it before committing changes to the lab.

> [+] Committing changes to the Lab Profile
> 
> If you have made changes to the environment and those changes need to persist, they have to be committed (saved). If the running lab is ended without saving it, all modifications to the environment will be lost.
> 
> To commit/save the changes, from the Settings menu, choose the **Commit Changes** option and follow the instructions.

> [+]Publishing a Lab Profile
> 
> Publishing a Lab Profile makes it available on customer/user-facing platforms, such as commercial LMSs (e.g., Blackboard or Cornerstone), the Skillable Training Management System, or an organization’s in-house developed system. The basic process for publishing is as follows:
>
> 1. **Copy the Lab Series and the Lab Profile** (single action) to the ***companyname* - Production** organization.
> 2. **Test launch the new Lab Profile** to ensure it functions correctly.
> 3. **Edit the Lab Profile** and set the development state to complete.
> 4. **Request a security review** if the Lab Profile includes cloud components.
> 5. **Edit the Lab Series** and specify the API Endpoint (Consumer) that the Lab Series should be advertised to on the Publish page. Multiple endpoints can be chosen if > required.
> 6. **Save the Lab Series**.
>
> For full details, refer to the document [Publish Lab Series](https://docs.skillable.com/docs/publish-lab-series).



> [!knowledge] For more information, review the documentation on [Template Gallery](https://docs.skillable.com/docs/template-gallery)

:::


:::module(module=Scoring&#32this&#32Template)

### Scoring this Template

Skillable labs offer robust capabilities to validate user performance in software environments through a feature called Automated Activities. Detailed information with examples can be reviewed on our [Validating Skills](https://docs.skillable.com/docs/pbt-overview) documentation page.

In Windows-based environments, we recommend using PowerShell as the scripting language. Skillable also provides tools including the Scripting Copilot and Script Library to get you started.

* Skillable Copilot: Enables you to use AI to create the script for you
* The Script Library: Contains customizable example scripts to streamline script creation.

> [+]Example Scoring Script - From the Script library
> 
> This is an example of a PowerShell validation script for a Windows VM. This script will check to see if a file has been created. Line 5 can be modified to specify the filename that needs to be checked. If the file is found, the script returns boolean **True**. If the file is not found, a boolean **False** is returned. This can be added to an Automated Activity in the instructions.
>
> ```powershell-linenums
> # Set '$result' to FALSE so the Activity is not completed by default.
> $result = $false
> 
> # Query variables. Modify these to match the lab environment.
> $file = "C:\labfiles\output.txt"
> $evidence = "The file $file was not found"
> 
> 
> # Try/Catch block to suppress any errors.
> try {
>    # Enter commands to get values.
>    $exists = Test-Path -Path $file
>    
>    # Test output of commands for expected value.
>    if ($exists -eq $true) {
>        # Set '$result' to TRUE for completing Activity correctly.
>        $evidence = "The file $file was found"
>        $result = $true
>    }
> } catch {
>    return $result
> }
> 
> # Return the result of the Activity script.
> $evidence
> return $result
> 
> ```

:::
