---
title: Disabilitare la soluzione ibrida per completare la migrazione al cloud
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
localization_priority: Normal
description: Questo articolo include la procedura dettagliata per disabilitare l'ambiente ibrido come parte del consolidamento del cloud per Teams e Skype for Business.
ms.openlocfilehash: 90ec73246007542ad0215007b0da91f4fe9405e8
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2021
ms.locfileid: "50874696"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud-overview"></a>Disabilitare la migrazione ibrida per completare la migrazione nel cloud: panoramica

Dopo aver spostato tutti gli utenti dall'infrastruttura locale al cloud, è possibile ritirare la distribuzione locale di Skype for Business. Oltre a rimuovere qualsiasi hardware, un passaggio critico consiste nel separare logicamente la distribuzione locale da Microsoft 365 o Office 365 disabilitando la distribuzione ibrida. Disabilitare l'ambiente ibrido consiste in tre passaggi:

1. Aggiornare i record DNS in modo che puntino a Microsoft 365 o Office 365.

2. Disabilitare lo spazio di indirizzi SIP condiviso (noto anche come "dominio diviso") nell'organizzazione di Microsoft 365 o Office 365.

3. Disabilitare la possibilità in locale di comunicare con Microsoft 365 o Office 365.

Questi passaggi separano logicamente la distribuzione locale di Skype for Business Server da Office 365 e devono essere evasi insieme come unità. I dettagli per ogni passaggio sono forniti in questo articolo di seguito. Al termine, puoi rimuovere le autorizzazioni per la distribuzione locale di Skype for Business usando uno dei due metodi indicati di seguito.

> [!Important] 
>Una volta completata questa separazione logica, gli attributi msRTCSIP da Active Directory locale hanno ancora valori e continueranno a essere sincronizzati tramite Azure AD Connect in Azure AD. La modalità di rimozione delle autorizzazioni per l'ambiente locale dipende dal fatto che si intenda o meno lasciare tali attributi sul posto o prima di cancellarli da Active Directory locale. Tenere presente che la cancellazione degli attributi msRTCSIP locali dopo la migrazione dall'ambiente locale potrebbe comportare la perdita del servizio per gli utenti. I dettagli e i compromessi dei due approcci di rimozione delle autorizzazioni sono descritti più avanti.

## <a name="disable-hybrid-to-complete-migration-to-the-cloud-detailed-steps"></a>Disabilitare la migrazione ibrida per completare la migrazione nel cloud: passaggi dettagliati

1. *Aggiornare DNS in modo che punti a Microsoft 365 o Office 365.* Il DNS esterno dell'organizzazione per l'organizzazione locale deve essere aggiornato in modo che i record di Skype for Business puntino a Microsoft 365 o Office 365 anziché alla distribuzione locale. In particolare:

    |Tipo di record|Nome|TTL|Value|
    |---|---|---|---|
    |SRV|_sipfederationtls._tcp|3600|100 1 5061 sipfed.online.lync. <span> com|
    |SRV|_sip._tls|3600|100 1 443 sipdir.online.lync. <span> com|
    |CNAME| lyncdiscover|   3600|   webdir.online.lync. <span> com|
    |CNAME| sip|    3600|   sipdir.online.lync. <span> com|

    Inoltre, i record CNAME per meet o dialin (se presente) possono essere eliminati. Infine, tutti i record DNS per Skype for Business nella rete interna devono essere rimossi.

    > [!Note] 
    > In rari casi, la modifica del DNS dal puntare in locale a Microsoft 365 o Office 365 per l'organizzazione può causare la federazione con altre organizzazioni a smettere di funzionare finché l'altra organizzazione non aggiorna la configurazione della federazione:
    >
    > - Tutte le organizzazioni federate che utilizzano il modello di federazione diretta precedente (noto anche come Server partner consentito) dovranno aggiornare le voci di dominio consentite per l'organizzazione per rimuovere il nome di dominio completo del proxy. Questo modello di federazione legacy non è basato sui record DNS SRV, quindi una configurazione di questo tipo diventerà non aggiornata dopo che l'organizzazione si sposta nel cloud.
    > 
    > - Qualsiasi organizzazione federata che non dispone di un provider di hosting abilitato per sipfed.online.lync. <span> com dovrà aggiornare la configurazione per abilitarla. Questa situazione è possibile solo se l'organizzazione federata è puramente locale e non ha mai federato con un tenant ibrido o online. In tal caso, la federazione con queste organizzazioni non funzionerà finché non abilita il provider di hosting.
    >
    > Se si sospetta che uno dei partner federati utilizzi la federazione diretta o che non sia federato con un'organizzazione online o ibrida, è consigliabile inviare loro una comunicazione in proposito mentre si prepara a completare la migrazione al cloud.


2.  *Disabilitare lo spazio di indirizzi SIP condiviso nell'organizzazione di Microsoft 365 o Office 365.* Il comando seguente deve essere eseguito da una finestra di PowerShell di Skype for Business Online.

     ```PowerShell
     Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
     ```
 
3.  *Disabilitare la possibilità in locale di comunicare con Microsoft 365 o Office 365.* Il comando seguente deve essere eseguito da una finestra di PowerShell locale:

     ```PowerShell
     Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
     ```

## <a name="managing-attributes-after-moving-users-from-on-premises-to-the-cloud"></a>Gestione degli attributi dopo lo spostamento degli utenti dall'ambiente locale al cloud

Per impostazione predefinita, tutti gli utenti precedentemente abilitati per Skype for Business Server e successivamente spostati nel cloud hanno ancora attributi msRTCSIP configurati in Active Directory locale. Questi attributi, in particolare l'indirizzo sip (msRTCSIP-PrimaryUserAddress) e il numero di telefono potenzialmente (msRTCSIP-Line), continuano a essere sincronizzati in Azure AD. Se sono necessarie modifiche a uno degli attributi msRTCSIP, queste modifiche devono essere apportate in Active Directory locale e quindi sincronizzate con Azure AD. Tuttavia, una volta rimossa la distribuzione di Skype for Business Server, gli strumenti di Skype for Business Server non saranno disponibili per gestire questi attributi.

Sono disponibili due opzioni per gestire questa situazione:

1. Lasciare gli utenti abilitati per gli account del server Skype for Business così com'è e gestire gli attributi msRTCSIP con gli strumenti di Active Directory. Questo garantisce la perdita del servizio per gli utenti migrati e consente di rimuovere facilmente la distribuzione di Skype for Business Server eliminando (ad esempio, la cancellazione) dei server, senza una rimozione completa. Tuttavia, i nuovi utenti con licenza non avranno questi attributi popolati in Active Directory locale e dovranno essere gestiti online.

2.  Cancellare tutti gli attributi msRTCSIP dagli utenti migrati in Active Directory locale e gestire questi attributi utilizzando gli strumenti online. Questo metodo consente un approccio di gestione coerente per gli utenti esistenti e nuovi, tuttavia può potenzialmente causare una perdita temporanea del servizio durante il processo di rimozione delle autorizzazioni locale.


### <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a>Metodo 1 - Gestire gli indirizzi SIP e i numeri di telefono per gli utenti in Active Directory

Gli amministratori possono gestire gli utenti che in precedenza erano stati spostati da Skype for Business Server locale al cloud, anche dopo la rimozione della distribuzione locale. Se si desidera apportare modifiche all'indirizzo SIP di un utente o al numero di telefono di un utente (e l'indirizzo sip o il numero di telefono ha già un valore in Active Directory locale), è necessario eseguire questa operazione in Active Directory locale e consentire il flusso dei valori fino ad Azure AD. Questo non richiede Skype for Business Server locale. È invece possibile modificare questi attributi direttamente in Active Directory locale, utilizzando lo snap-in MMC Utenti e computer di Active Directory (come illustrato di seguito) o PowerShell. Se si utilizza lo snap-in MMC, aprire la pagina delle proprietà dell'utente, fare clic sulla scheda Editor attributi e individuare gli attributi appropriati da modificare:

- Per modificare l'indirizzo SIP di un utente, modificare la proprietà `msRTCSIP-PrimaryUserAddress` . Si noti che, `ProxyAddresses` se l'attributo contiene un indirizzo sip, aggiornare anche tale valore come procedura consigliata. Anche se l'indirizzo sip in viene ignorato da O365 se viene popolato, può essere utilizzato `ProxyAddresses` `msRTCSIP-PrimaryUserAddress` da altri componenti locali.

- Per modificare il numero di telefono di un utente, modificare `msRTCSIP-Line` *se ha già un valore*.

  ![Strumento Utenti e computer di Active Directory](../media/disable-hybrid-1.png)
  
-  Se l'utente in origine non aveva un valore per l'ambiente locale prima dello spostamento, è possibile modificare il numero di telefono utilizzando il parametro - nel `msRTCSIP-Line` `onpremLineUri` cmdlet [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) nel modulo PowerShell di Skype for Business Online.

Questi passaggi non sono necessari per i nuovi utenti creati dopo la disabilitazione ibrida e possono essere gestiti direttamente nel cloud. Se si ha familiarità con l'uso della combinazione di questi metodi e con l'abbandono degli attributi msRTCSIP in locale in Active Directory, è sufficiente ri-immagine dei server Skype for Business locali. Tuttavia, se preferisci cancellare tutti gli attributi msRTCSIP ed eseguire una disinstallazione tradizionale di Skype for Business Server, usa il metodo 2.


### <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a>Metodo 2 - Cancellare gli attributi di Skype for Business per tutti gli utenti locali in Active Directory

Questa opzione richiede ulteriori sforzi e una pianificazione adeguata perché gli utenti che in precedenza erano stati spostati da Skype for Business Server locale al cloud devono essere nuovamente provisioning. Questi utenti possono essere categorizzati in due categorie diverse: gli utenti senza Sistema telefonico e gli utenti con Sistema telefonico. Gli utenti con sistema telefonico sperimenteranno una perdita temporanea del servizio telefonico nell'ambito della transizione del numero di telefono dalla gestione in Active Directory locale al cloud. **È consigliabile eseguire un progetto pilota che coinvolge un numero limitato di utenti con Sistema telefonico prima di avviare le operazioni in blocco degli utenti.** Per distribuzioni di grandi dimensioni gli utenti possono essere elaborati in gruppi più piccoli in finestre di tempo diverse. 

> [!NOTE]
> Il processo è più semplice per gli utenti che dispongono di un indirizzo SIP e userPrincipalName corrispondenti. Per le organizzazioni con utenti con valori non corrispondenti tra questi due attributi, è necessario fare attenzione come indicato di seguito per una transizione senza problemi. 


1. Verificare che il seguente cmdlet di PowerShell di Skype for Business locale restituisca un risultato vuoto. Un risultato vuoto indica che nessun utente è ospitato in locale e che è stato spostato in Office 365 o è stato disabilitato:

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. Registrare il numero di telefono corrente degli utenti (LineUri), UserPrincipalName e le informazioni correlate eseguendo il cmdlet di PowerShell di Skype for Business Server locale seguente per esportare i dati degli utenti:

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > Prima di procedere con SfbUserSettings.csv file e verificare che tutti i dati utente siano stati esportati correttamente. È consigliabile conservare una copia di questo file.  Non utilizzare questo file nei passaggi seguenti per l'elaborazione degli utenti. 

3. Creare un file con un gruppo di utenti da utilizzare nei passaggi seguenti. Una volta completato correttamente il primo gruppo di utenti, procedere con il gruppo di utenti successivo. Nell'esempio seguente i gruppi di utenti vengono selezionati in ordine alfabetico, ma è possibile filtrare gli utenti in base ai criteri che corrispondono al modo in cui si desidera elaborare gli utenti.

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > Prima di procedere con SfbUsers.csv file e verificare che i dati utente siano stati esportati correttamente. In un passaggio successivo saranno necessari LineUri (numero di telefono), UserPrincipalName, SamAccountName e SipAddress da questo file.

4. Eliminare le informazioni sugli attributi relative a Skype for Business Server da Active Directory per il set di utenti pronti per l'aggiornamento.  Esistono 2 passaggi per questo processo, come illustrato di seguito.

   > [!Important] 
   > Dopo il successivo ciclo di sincronizzazione AAD dopo l'esecuzione di questo passaggio, gli utenti con Sistema telefonico che in precedenza erano stati spostati da un Skype for Business Server locale al cloud perderanno la possibilità di effettuare e ricevere chiamate fino al completamento e alla conferma del passaggio 8 nel passaggio 9. Inoltre, assicurati di aver salvato i numeri di telefono e le informazioni correlate dell'utente secondo il passaggio 2, poiché queste informazioni sono necessarie per tale passaggio.

 
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

5. Eseguire il seguente cmdlet di PowerShell di Skype for Business locale per aggiungere nuovamente il valore dell'indirizzo sip ai proxyAddresses di Active Directory locali. In questo modo si evitano problemi di interoperabilità che si basano su questo attributo. 

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

6. Eseguire Azure AD Sync

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. Attendere il completamento del provisioning degli utenti. È possibile monitorare lo stato di avanzamento del provisioning degli utenti eseguendo il seguente comando di PowerShell di Skype for Business Online. Il seguente comando di PowerShell di Skype for Business online restituisce un risultato vuoto non appena il processo viene completato.

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. Eseguire il comando di PowerShell di Skype for Business online seguente per assegnare numeri di telefono e abilitare gli utenti per Sistema telefonico:
     
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
   >  Se hai ancora endpoint Skype for Business (client Skype o telefoni di terze parti), devi anche impostare -HostedVoiceMail su $true. Se l'organizzazione usa solo endpoint di Teams per gli utenti abilitati alla funzionalità vocale, questa impostazione non è applicabile agli utenti. 

9. Verificare che il provisioning degli utenti con funzionalità sistema telefonico sia stato eseguito correttamente. Il seguente comando di PowerShell di Skype for Business online restituisce un risultato vuoto non appena il processo viene completato.

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

    Comando di PowerShell locale di Skype for Business Server locale:

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 
    Comando di PowerShell di Skype for Business online:

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 


## <a name="see-also"></a>Vedere anche

[Consolidamento cloud per Teams e Skype for Business](cloud-consolidation.md)
