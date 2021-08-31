---
title: Decidere come gestire gli attributi dopo la rimozione delle autorizzazioni
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
description: In questo articolo viene descritto come gestire gli attributi dopo la rimozione delle autorizzazioni dell'ambiente locale.
ms.openlocfilehash: 64ba4844a1958cfd386a177d91b9c4f2dff89102
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "58736025"
---
# <a name="decide-how-to-manage-attributes-after-decommissioning"></a>Decidere come gestire gli attributi dopo la rimozione delle autorizzazioni

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


Per impostazione predefinita, tutti gli utenti precedentemente abilitati per Skype for Business Server e successivamente spostati nel cloud hanno ancora attributi msRTCSIP configurati in Active Directory locale. 

Questi attributi, in particolare l'indirizzo sip (msRTCSIP-PrimaryUserAddress) e il numero di telefono potenzialmente (msRTCSIP-Line), continuano a essere sincronizzati in Azure AD. Se sono necessarie modifiche a uno degli attributi msRTCSIP, queste modifiche devono essere apportate in Active Directory locale e quindi sincronizzate con Azure AD. Tuttavia, una volta rimossa Skype for Business Server distribuzione, gli Skype for Business Server non saranno disponibili per gestire questi attributi.

Sono disponibili due opzioni per gestire questa situazione:

1. Lasciare gli utenti abilitati per Skype for Business server e gestire gli attributi msRTCSIP utilizzando gli strumenti di Active Directory. Ciò garantisce la perdita del servizio per gli utenti migrati e consente di rimuovere facilmente la distribuzione di Skype for Business Server eliminando (ad esempio, la cancellazione) dei server, senza una rimozione completa. Tuttavia, i nuovi utenti con licenza non avranno questi attributi popolati in Active Directory locale e dovranno essere gestiti online.

2.  Cancellare tutti gli attributi msRTCSIP dagli utenti migrati in Active Directory locale e gestire questi attributi utilizzando gli strumenti online. Questo metodo consente un approccio di gestione coerente per gli utenti esistenti e nuovi, tuttavia può potenzialmente causare una perdita temporanea del servizio durante il processo di rimozione delle autorizzazioni locale.


## <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a>Metodo 1 - Gestire gli indirizzi SIP e i numeri di telefono per gli utenti in Active Directory

Gli amministratori possono gestire gli utenti spostati in precedenza da un Skype for Business Server locale al cloud, anche dopo la rimozione della distribuzione locale. 

Se si desidera apportare modifiche all'indirizzo SIP di un utente o al numero di telefono di un utente (e l'indirizzo sip o il numero di telefono ha già un valore in Active Directory locale), è necessario eseguire questa operazione in Active Directory locale e consentire il flusso dei valori fino ad Azure AD. Non richiede l'utilizzo di Skype for Business Server locale. È invece possibile modificare questi attributi direttamente in Active Directory locale, utilizzando lo snap-in MMC Utenti e computer di Active Directory (come illustrato di seguito) o PowerShell. Se si utilizza lo snap-in MMC, aprire la pagina delle proprietà dell'utente, fare clic sulla scheda Editor attributi e individuare gli attributi appropriati da modificare:

- Per modificare l'indirizzo SIP di un utente, modificare la proprietà `msRTCSIP-PrimaryUserAddress` .

    > [!NOTE]
    > Se `ProxyAddresses` l'attributo contiene un indirizzo SIP, aggiornare anche tale valore come procedura consigliata. Anche se l'indirizzo SIP in viene ignorato da O365 se viene popolato, può essere utilizzato `ProxyAddresses` `msRTCSIP-PrimaryUserAddress` da altri componenti locali.

- Per modificare il numero di telefono di un utente, modificare `msRTCSIP-Line` *se ha già un valore*.

  ![Strumento Utenti e computer di Active Directory.](../media/disable-hybrid-1.png)
  
-  Se l'utente originariamente non aveva un valore per l'ambiente locale prima dello spostamento, è possibile modificare il numero di telefono utilizzando il parametro - nel `msRTCSIP-Line` `onpremLineUri` cmdlet [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) nel modulo di PowerShell di Teams.

Questi passaggi non sono necessari per i nuovi utenti creati dopo la disabilitazione ibrida e possono essere gestiti direttamente nel cloud. Se si ha familiarità con l'uso della combinazione di questi metodi e con l'abbandono degli attributi msRTCSIP in locale in Active Directory, è possibile semplicemente ri-immagine dei server Skype for Business locali. Tuttavia, se si preferisce cancellare tutti gli attributi msRTCSIP ed eseguire una disinstallazione tradizionale di Skype for Business Server, utilizzare il metodo 2.


## <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a>Metodo 2 - Cancellare Skype for Business per tutti gli utenti locali in Active Directory

Questa opzione richiede ulteriori sforzi e una pianificazione adeguata perché è necessario eseguire di nuovo il provisioning degli utenti spostati in precedenza da un Skype for Business Server locale al cloud. Questi utenti possono essere categorizzati in due categorie diverse: gli utenti senza Sistema telefonico e gli utenti con Sistema telefonico. Gli utenti con Sistema telefonico si verificano una perdita temporanea del servizio telefonico come parte della transizione del numero di telefono dalla gestione in Active Directory locale al cloud. **È consigliabile eseguire un progetto pilota che coinvolge un numero limitato di utenti con Sistema telefonico prima di avviare le operazioni in blocco degli utenti.** Per distribuzioni di grandi dimensioni gli utenti possono essere elaborati in gruppi più piccoli in finestre di tempo diverse. 

> [!NOTE] 
> Questo processo è più semplice per gli utenti che hanno un indirizzo SIP e UserPrincipalName corrispondenti. Per le organizzazioni con utenti con valori non corrispondenti tra questi due attributi, è necessario fare attenzione come indicato di seguito per una transizione senza problemi.

> [!NOTE]
> Se sono stati configurati endpoint dell'applicazione ibrida locale per operatori automatici o code di chiamata, assicurarsi di spostare questi endpoint in Microsoft 365 prima di rimuovere le autorizzazioni Skype for Business Server. Per informazioni dettagliate, vedere [Migrate hybrid application endpoints before decommissioning your on-premises environment](decommission-move-on-prem-endpoints.md).  


1. Verificare che il seguente cmdlet di PowerShell Skype for Business locale restituisca un risultato vuoto. Un risultato vuoto indica che nessun utente è ospitato in locale e che è stato spostato in Microsoft 365 o è stato disabilitato:

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. Registrare il numero di telefono corrente degli utenti (LineUri), UserPrincipalName e le informazioni correlate eseguendo il cmdlet di PowerShell Skype for Business Server locale seguente per esportare i dati degli utenti:

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > Prima di procedere, aprire SfbUserSettings.csv file e verificare che tutti i dati utente siano stati esportati correttamente. È consigliabile conservare una copia di questo file.  Non utilizzare questo file nei passaggi seguenti per l'elaborazione degli utenti. 

3. Creare un file con un gruppo di utenti da utilizzare nei passaggi seguenti. Una volta completato correttamente il primo gruppo di utenti, procedere con il gruppo di utenti successivo. Nell'esempio seguente i gruppi di utenti vengono selezionati in ordine alfabetico, ma è possibile filtrare gli utenti in base ai criteri che corrispondono al modo in cui si desidera elaborare gli utenti.

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > Prima di procedere con SfbUsers.csv file e verificare che i dati utente siano stati esportati correttamente. In un passaggio successivo saranno necessari LineUri (numero di telefono), UserPrincipalName, SamAccountName e SipAddress da questo file.

4. Eliminare le informazioni sugli attributi Skype for Business Server da Active Directory per il set di utenti pronti per l'aggiornamento.  Esistono 2 passaggi per questo processo, come illustrato di seguito.

   > [!Important] 
   > Dopo il ciclo di AAD Sync successivo dopo l'esecuzione di questo passaggio, gli utenti con Sistema telefonico spostati in precedenza da un Skype for Business Server locale al cloud perderanno la possibilità di effettuare e ricevere chiamate fino al completamento e alla conferma del passaggio 8 nel passaggio 9. Inoltre, assicurati di aver salvato i numeri di telefono dell'utente e le informazioni correlate nel passaggio 2, poiché queste informazioni sono necessarie per tale passaggio.

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   Successivamente, per lo stesso set di utenti, cancellare il valore di msRTCSIP-DeploymentLocator usando PowerShell di Active Directory locale:

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. Eseguire il seguente cmdlet di Active Directory Module locale per Windows PowerShell per aggiungere nuovamente il valore dell'indirizzo SIP ai proxyAddresses di Active Directory locali. In questo modo si evitano problemi di interoperabilità che si basano su questo attributo. 

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
     $userUpn=$user.UserPrincipalName
     $userSip=$user.SipAddress
     $proxies=Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" -properties * | Select-Object @{Name="proxyAddresses";Expression={$_.proxyAddresses}}
     if(($null -eq $proxies) -or ($proxies.proxyAddresses -NotContains $userSip))
     {
             Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" | Set-ADUser -Add @{"proxyAddresses"=$user.SipAddress}
     }
   }
   ```

6. Esegui Azure AD Sync

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. Attendere il completamento del provisioning degli utenti. È possibile monitorare lo stato di avanzamento del provisioning degli utenti eseguendo il comando Teams PowerShell seguente. Il comando Teams PowerShell seguente restituisce un risultato vuoto non appena il processo viene completato.

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. Eseguire il comando Teams PowerShell seguente per assegnare numeri di telefono e abilitare gli utenti per Sistema telefonico:
     
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   if($user.LineUri)
        {
                Set-CsUser -Identity $user.SipAddress -OnPremLineURI $user.LineUri -EnterpriseVoiceEnabled $True
        }
   }
    ```

   > [!Note]
   >  Se sono ancora disponibili endpoint Skype for Business (client Skype o telefoni di terze parti), è anche necessario impostare -HostedVoiceMail su $true. Se l'organizzazione usa solo Teams endpoint per gli utenti abilitati alla funzionalità vocale, questa impostazione non è applicabile agli utenti. 

9. Verificare che il provisioning degli Sistema telefonico funzionalità sia stato eseguito correttamente. Il comando Teams PowerShell seguente restituisce un risultato vuoto non appena il processo viene completato.

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers)
   {
   if($user.LineUri)
        {
                $u=Get-CsOnlineUser -Identity $user.SipAddress
                if ($u.LineURI -ne $user.LineUri -or $u.EnterpriseVoiceEnabled -ne $true)
                {
                Get-CsOnlineUser -Identity $user.SipAddress | fl SipAddress, InterpretedUserType, OnPremLineURI, LineURI, EnterpriseVoiceEnabled, HostedVoicemail
                }
        }
   }
   ``` 

10. Ripetere i passaggi da 3 a 9 finché non vengono elaborati tutti gli utenti.

11. Verificare che tutti gli utenti siano stati elaborati correttamente eseguendo i due comandi di PowerShell seguenti.

    Comando PowerShell Skype for Business Server locale:

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 

    Teams Comando di PowerShell:

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 

12. Dopo aver completato tutti i passaggi nel metodo 2, vedere Spostare gli endpoint dell'applicazione ibrida da locale a [online](decommission-move-on-prem-endpoints.md) e [Rimuovere](decommission-remove-on-prem.md) il Skype for Business Server locale per ulteriori passaggi per rimuovere la distribuzione locale di Skype for Business Server.


## <a name="see-also"></a>Vedere anche

- [Consolidamento cloud per Teams e Skype for Business](cloud-consolidation.md)

- [Rimuovi le autorizzazioni dell'ambiente locale Skype for Business](decommission-on-prem-overview.md)

