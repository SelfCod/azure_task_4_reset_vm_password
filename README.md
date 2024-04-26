# Reset the VM Admin Password

You can easily forget the VM password or lose the SSH key, but don't worry—it's not the end of the world! In Azure, you can easily reset the VM admin password; you will practice it in this task. 

## Prerequisites

Before completing any task in the module, make sure that you followed all the steps described in the **Environment Setup** topic, in particular: 

1. Ensure you have an [Azure](https://azure.microsoft.com/en-us/free/) account and subscription.

2. Create a resource group called *"mate-resources"* in the Azure subscription.

3. In the *"mate-resources"* resource group, create a storage account (any name) and a *"task-artifacts"* container.

4. Install [PowerShell 7](https://learn.microsoft.com/en-us/powershell/scripting/install/installing-powershell?view=powershell-7.4) on your computer. All tasks in this module use PowerShell 7. To run it in the terminal, execute the following command: 
    ```
    pwsh
    ```

5. Install [Azure module for PowerShell 7](https://learn.microsoft.com/en-us/powershell/azure/install-azure-powershell?view=azps-11.3.0): 
    ```
    Install-Module -Name Az -Repository PSGallery -Force
    ```
If you are a Windows user, before running this command, please also run the following: 
    ```
    Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
    ```

6. Log in to your Azure account using PowerShell:
    ```
    Connect-AzAccount -TenantId <your Microsoft Entra ID tenant id>
    ```

## Requirements

In this task, you need to perform the following steps: 


1. Use the infrastructure you created in the [previous task](https://github.com/mate-academy/azure_task_2_create_a_vm). Reset the VM admin password on the virtual machine you created earlied: 

    - use a username that is different from the one you used to create the VM 
    
    - use password authentification for the user. 

    After the password reset, connect to the VM with the new credentials using SSH to test whether the password has been reset. 

2. Run artifacts generation script `scripts/generate-artifacts.ps1`

3. Test yourself using the script `scripts/validate-artifacts.ps1`

4. Submit the solution for a review

5. When the solution is validated, stop the virtual machine. 

## How to Complete Tasks in This Module 

Tasks in this module are relying on 2 PowerShell scripts: 

- `scripts/generate-artifacts.ps1` generates the task "artifacts" and uploads them to cloud storage. An "artifact" is evidence of a task completed by you. Each task will have its own script, which will gather the required artifacts. The script also adds a link to the generated artifact in the `artifacts.json` file in this repository — make sure to commit changes to this file after you run the script. 
- `scripts/validate-artifacts.ps1` validates the artifacts generated by the first script. It loads information about the task artifacts from the `artifacts.json` file.

Here is how to complete tasks in this module:

1. Clone task repository

2. Make sure you completed the steps described in the Prerequisites section

3. Complete the task described in the Requirements section 

4. Run `scripts/generate-artifacts.ps1` to generate task artifacts. The script will update the file `artifacts.json` in this repo. 

5. Run `scripts/validate-artifacts.ps1` to test yourself. If tests are failing — follow the recommendation from the test script error message to fix or re-deploy your infrastructure. When you are ready to test yourself again — **re-generate the artifacts** (step 4) and re-run tests again. 

6. When all tests will pass — commit your changes and submit the solution for review. 

Pro tip: If you are stuck with any of the implementation steps, run `scripts/generate-artifacts.ps1` and `scripts/validate-artifacts.ps1`. The validation script might give you a hint on what to do.  
