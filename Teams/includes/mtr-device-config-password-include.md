
Come qualsiasi altro account di Microsoft 365, la password di un account di risorsa appena creato scade automaticamente dopo un periodo di tempo. Tuttavia, se la password dell'account della risorsa scade, il dispositivo Teams Rooms a cui ha eseguito l'accesso non potrà più accedere alla data di scadenza. 

Per evitare di dover reimpostare la password dell'account della risorsa e quindi accedere di nuovo a ogni Teams Rooms dispositivo, è possibile disattivare la scadenza della password per l'account.
  
> [!NOTE]
> L'impostazione della **password non scade mai** è un requisito per i dispositivi Microsoft Teams condivisi. Se le regole di dominio proibiscono password che non scadono, è necessario creare un'eccezione per ogni account di risorse del dispositivo Teams.

Segui i passaggi descritti in una delle schede seguenti per disattivare la scadenza della password:

#### <a name="azure-active-directory-20"></a>[**Azure Active Directory 2.0**](#tab/azure-active-directory2-password/)

Prima di tutto, connettersi a PowerShell di Active Directory:

```PowerShell
   Connect-AzureAD
```

Quindi, vedere [Impostare una password in modo che non scada mai](/microsoft-365/admin/add-users/set-password-to-never-expire#set-a-password-to-never-expire).

In questo esempio la password dell'account ConferenceRoom01@contoso.com non scade mai.

```PowerShell
Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -PasswordPolicies DisablePasswordExpiration
```

#### <a name="azure-active-directory-10"></a>[**Azure Active Directory 1.0**](#tab/azure-active-directory1-password/)

 1. Connettersi a PowerShell per MSOnline:

       ```PowerShell
       Connect-MsolService
       ```

       Per informazioni dettagliate su Active Directory, vedere [Azure Active Directory (MSOnline).For details about Active Directory, see Azure Active Directory (MSOnline)](/powershell/azure/active-directory/overview?view=azureadps-1.0&preserve-view=true).

2. Impostare la password in modo che non scada mai usando la sintassi seguente:

    ```PowerShell
    Set-MsolUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    In questo esempio la password dell'account ConferenceRoom01@contoso.com non scade mai.

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -PasswordNeverExpires $true
    ```

#### <a name="active-directory-on-premises"></a>[**Active Directory (locale)**](#tab/active-directory1-password/)

1. Connettersi a PowerShell di Active Directory:

    ```PowerShell
       Import-Module ActiveDirectory
    ```
    
    Per informazioni dettagliate su PowerShell di Active Directory, vedere [ActiveDirectory](/powershell/module/activedirectory).

2. Impostare la password in modo che non scada mai usando la sintassi seguente:

    ```PowerShell
    Set-ADUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    In questo esempio la password dell'account ConferenceRoom01@contoso.com non scade mai.

    ```PowerShell
    Set-ADUser -Identity ConferenceRoom01@contoso.com -PasswordNeverExpires $true
    ```

---