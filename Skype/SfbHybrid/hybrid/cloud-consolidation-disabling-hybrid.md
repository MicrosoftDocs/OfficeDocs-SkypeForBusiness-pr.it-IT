---
title: Disabilitare la distribuzione ibrida per completare la migrazione Teams solo
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
ms.openlocfilehash: 97681f4e9306336874ba4d9428a273b1d31519db
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420841"
---
# <a name="disable-your-hybrid-configuration-to-complete-migration-to-teams-only"></a>Disabilitare la configurazione ibrida per completare la migrazione a Teams solo 

In questo articolo viene descritto come disabilitare la configurazione ibrida prima di rimuovere le autorizzazioni dell'ambiente Skype for Business locale. Questo è il passaggio 2 della procedura seguente per rimuovere le autorizzazioni dell'ambiente locale:

- Passaggio 1. [Spostare tutti gli utenti necessari da locale a online.](decommission-move-on-prem-users.md)

- **Passaggio 2. Disabilitare la configurazione ibrida.** (Questo articolo)

- Passaggio 3. [Eseguire la migrazione degli endpoint dell'applicazione ibrida da locale a online.](decommission-move-on-prem-endpoints.md)

- Passaggio 4. [Rimuovere la distribuzione locale Skype for Business .](decommission-remove-on-prem.md)

> [!NOTE]
> I passaggi 2 e 3 devono essere evasi nella stessa finestra di manutenzione perché gli endpoint delle applicazioni ibride esistenti non saranno individuabili tra i passaggi 2 e il completamento del passaggio 3.

## <a name="overview"></a>Panoramica

Dopo aver aggiornato tutti gli utenti da Skype for Business locale a Teams Solo in Microsoft 365, è possibile rimuovere le autorizzazioni per la distribuzione Skype for Business locale. Prima di rimuovere le autorizzazioni per la distribuzione di Skype for Business locale e rimuovere qualsiasi hardware, è necessario separare logicamente la distribuzione locale da Microsoft 365 disabilitando la distribuzione ibrida. La disabilitazione ibrida prevede i quattro passaggi seguenti:

1. Aggiornare i record NS in modo che puntino a Microsoft 365.

2. Modificare la modalità di coesistenza per l'organizzazione Teams solo.

3. Disabilitare lo spazio di indirizzi SIP condiviso (noto anche come "dominio diviso") nell'Microsoft 365 organizzazione.

4. Disabilitare la possibilità in locale di comunicare con Microsoft 365.

Questi passaggi separano logicamente la distribuzione locale di Skype for Business Server da Microsoft 365 e assicurati che l'organizzazione sia completamente Teams solo. In questo articolo vengono forniti i dettagli per ogni passaggio. Al termine, è possibile rimuovere le autorizzazioni della distribuzione locale Skype for Business utilizzando uno dei due metodi a cui si fa riferimento di seguito.

> [!Important] 
> Al termine di questa separazione logica, gli attributi msRTCSIP da Active Directory locale hanno ancora valori e continueranno a essere sincronizzati tramite Azure AD Connessione in Azure AD. La modalità di rimozione delle autorizzazioni per l'ambiente locale dipende dal fatto che si intenda o meno lasciare tali attributi sul posto o prima di cancellarli da Active Directory locale. Tenere presente che la cancellazione degli attributi msRTCSIP locali dopo la migrazione dall'ambiente locale potrebbe comportare la perdita del servizio per gli utenti. I dettagli e i compromessi dei due approcci di rimozione delle autorizzazioni sono descritti più avanti.

## <a name="detailed-steps"></a>Passaggi dettagliati

1. *Aggiornare DNS in modo che punti a Microsoft 365.* Il DNS esterno dell'organizzazione per l'organizzazione locale deve essere aggiornato in modo che i record di Skype for Business puntino a Microsoft 365 anziché alla distribuzione locale. In particolare:

    |Tipo di record|Nome|TTL|Priorità|Peso|Porta|Value|
    |---|---|---|---|---|---|---|
    |SRV|_sipfederationtls._tcp|3600|100|1 |5061|sipfed.online.lync. <span> com|
    |SRV|_sip._tls|3600|100|1 |443|sipdir.online.lync. <span> com|
    |CNAME| lyncdiscover|   3600| | | |webdir.online.lync. <span> com|
    |CNAME| sip|    3600| | | | sipdir.online.lync. <span> com|

    Inoltre, i record CNAME per meet o dialin (se presente) possono essere eliminati. Infine, tutti i record DNS Skype for Business nella rete interna devono essere rimossi.

    > [!Note] 
    > In rari casi, la modifica del DNS da locale a Microsoft 365 per l'organizzazione può causare la federazione con altre organizzazioni smettere di funzionare finché l'altra organizzazione non aggiorna la configurazione della federazione:
    >
    > - Tutte le organizzazioni federate che utilizzano il modello di federazione diretta precedente (noto anche come Server partner consentito) dovranno aggiornare le voci di dominio consentite per l'organizzazione per rimuovere il nome di dominio completo del proxy. Questo modello di federazione legacy non è basato sui record DNS SRV, quindi una configurazione di questo tipo diventerà non aggiornata dopo che l'organizzazione si sposta nel cloud.
    > 
    > - Qualsiasi organizzazione federata che non dispone di un provider di hosting abilitato per sipfed.online.lync. <span> com dovrà aggiornare la configurazione per abilitarla. Questa situazione è possibile solo se l'organizzazione federata è puramente locale e non ha mai federato con un tenant ibrido o online. In tal caso, la federazione con queste organizzazioni non funzionerà finché non abilita il provider di hosting.
    >
    > Se si sospetta che uno dei partner federati utilizzi la federazione diretta o che non sia federato con un'organizzazione online o ibrida, è consigliabile inviare loro una comunicazione in proposito mentre si prepara a completare la migrazione al cloud.

2.  *Modificare la modalità di coesistenza per l'organizzazione Teams solo.* In questo modo si garantisce che qualsiasi nuovo utente dell'organizzazione sia sempre creato come Teams solo utente. Inoltre, se si tenta di modificare la modalità tenant in Teams Solo verrà verificata automaticamente l'esistenza di eventuali record DNS locali che potrebbero essere stati persi nel passaggio 1 e identificheranno tali record nell'output.  La modifica della modalità tenant in Teams solo avrà esito positivo finché non verranno aggiornati tutti i record DNS per l'organizzazione. Per modificare la modalità tenant in Teams eseguire solo il comando seguente da una Teams di PowerShell.

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
     ```
In alternativa, è possibile utilizzare l'interfaccia di amministrazione di Teams per modificare la modalità di coesistenza del tenant in TeamsOnly, in "Impostazioni a livello di organizzazione" -> "Teams aggiornamento".    
    
3.  *Disabilitare lo spazio di indirizzi SIP condiviso nell Microsoft 365 interno.* Il comando seguente deve essere eseguito da una finestra Teams PowerShell.

     ```PowerShell
     Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
     ```
 
4.  *Disabilitare la possibilità in locale di comunicare con Microsoft 365.* Il comando seguente deve essere eseguito da una finestra di PowerShell locale:

     ```PowerShell
     Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
     ```

## <a name="managing-attributes-after-moving-users-from-on-premises-to-the-cloud"></a>Gestione degli attributi dopo lo spostamento degli utenti dall'ambiente locale al cloud

Per impostazione predefinita, tutti gli utenti precedentemente abilitati per Skype for Business Server e successivamente spostati nel cloud hanno ancora attributi msRTCSIP configurati in Active Directory locale. Questi attributi, in particolare l'indirizzo sip (msRTCSIP-PrimaryUserAddress) e il numero di telefono potenzialmente (msRTCSIP-Line), continuano a essere sincronizzati in Azure AD. Se sono necessarie modifiche a uno degli attributi msRTCSIP, queste modifiche devono essere apportate in Active Directory locale e quindi sincronizzate con Azure AD. Tuttavia, una volta rimossa Skype for Business Server distribuzione, gli Skype for Business Server non saranno disponibili per gestire questi attributi.

Sono disponibili due opzioni per gestire questa situazione:

1. Lasciare gli utenti abilitati Skype for Business account del server e gestire gli attributi msRTCSIP utilizzando gli strumenti di Active Directory. Ciò garantisce la perdita del servizio per gli utenti migrati e consente di rimuovere facilmente la distribuzione di Skype for Business Server eliminando (ad esempio, la cancellazione) dei server, senza una rimozione completa. Tuttavia, i nuovi utenti con licenza non avranno questi attributi popolati in Active Directory locale e dovranno essere gestiti online.

2.  Cancellare tutti gli attributi msRTCSIP dagli utenti migrati in Active Directory locale e gestire questi attributi utilizzando gli strumenti online. Questo metodo consente un approccio di gestione coerente per gli utenti esistenti e nuovi, tuttavia può potenzialmente causare una perdita temporanea del servizio durante il processo di rimozione delle autorizzazioni locale.


### <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a>Metodo 1 - Gestire gli indirizzi SIP e i numeri di telefono per gli utenti in Active Directory

Gli amministratori possono gestire gli utenti spostati in precedenza da un Skype for Business Server locale al cloud, anche dopo la rimozione della distribuzione locale. Se si desidera apportare modifiche all'indirizzo SIP di un utente o al numero di telefono di un utente (e l'indirizzo sip o il numero di telefono ha già un valore in Active Directory locale), è necessario eseguire questa operazione in Active Directory locale e consentire il flusso dei valori fino ad Azure AD. Non richiede l'utilizzo di Skype for Business Server locale. È invece possibile modificare questi attributi direttamente in Active Directory locale, utilizzando lo snap-in MMC Utenti e computer di Active Directory (come illustrato di seguito) o PowerShell. Se si utilizza lo snap-in MMC, aprire la pagina delle proprietà dell'utente, fare clic sulla scheda Editor attributi e individuare gli attributi appropriati da modificare:

- Per modificare l'indirizzo SIP di un utente, modificare la proprietà `msRTCSIP-PrimaryUserAddress` .

    > [!NOTE]
    > Se `ProxyAddresses` l'attributo contiene un indirizzo SIP, aggiornare anche tale valore come procedura consigliata. Anche se l'indirizzo sip in viene ignorato da O365 se viene popolato, può essere utilizzato `ProxyAddresses` `msRTCSIP-PrimaryUserAddress` da altri componenti locali.

- Per modificare il numero di telefono di un utente, modificare `msRTCSIP-Line` *se ha già un valore*.

  ![Strumento Utenti e computer di Active Directory](../media/disable-hybrid-1.png)
  
-  Se l'utente originariamente non aveva un valore per l'ambiente locale prima dello spostamento, è possibile modificare il numero di telefono utilizzando il parametro - nel `msRTCSIP-Line` `onpremLineUri` cmdlet [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) nel modulo powerShell di Skype for Business Online.

Questi passaggi non sono necessari per i nuovi utenti creati dopo la disabilitazione ibrida e possono essere gestiti direttamente nel cloud. Se si ha familiarità con l'utilizzo della combinazione di questi metodi e con l'abbandono degli attributi msRTCSIP in locale in Active Directory, è possibile semplicemente ri-immagine dei server Skype for Business locali. Tuttavia, se si preferisce cancellare tutti gli attributi msRTCSIP ed eseguire una disinstallazione tradizionale di Skype for Business Server, utilizzare il metodo 2.


### <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a>Metodo 2 - Cancellare Skype for Business per tutti gli utenti locali in Active Directory

Questa opzione richiede ulteriori sforzi e una pianificazione adeguata perché è necessario eseguire di nuovo il provisioning degli utenti spostati in precedenza da un Skype for Business Server locale al cloud. Questi utenti possono essere categorizzati in due categorie diverse: gli utenti senza Sistema telefonico e gli utenti con Sistema telefonico. Gli utenti con Sistema telefonico si verificano una perdita temporanea del servizio telefonico durante la transizione del numero di telefono dalla gestione in Active Directory locale al cloud. **È consigliabile eseguire un progetto pilota che coinvolge un numero limitato di utenti con Sistema telefonico prima di avviare le operazioni in blocco degli utenti.** Per distribuzioni di grandi dimensioni gli utenti possono essere elaborati in gruppi più piccoli in finestre di tempo diverse. 

> [!NOTE] 
> Questo processo è più semplice per gli utenti che hanno un indirizzo SIP e UserPrincipalName corrispondenti. Per le organizzazioni con utenti con valori non corrispondenti tra questi due attributi, è necessario fare attenzione come indicato di seguito per una transizione senza problemi.

> [!NOTE]
> Se sono stati configurati endpoint dell'applicazione ibrida locale per operatori automatici o code di chiamata, assicurarsi di spostare questi endpoint in Microsoft 365 prima di rimuovere le autorizzazioni Skype for Business Server.


1. Verificare che il seguente cmdlet di PowerShell Skype for Business locale restituisca un risultato vuoto. Un risultato vuoto indica che nessun utente è ospitato in locale e che è stato spostato in Microsoft 365 o è stato disabilitato:

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. Registrare il numero di telefono corrente degli utenti (LineUri), UserPrincipalName e le informazioni correlate eseguendo il cmdlet di PowerShell Skype for Business Server locale seguente per esportare i dati degli utenti:

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

4. Eliminare le informazioni sugli attributi Skype for Business Server da Active Directory per il set di utenti pronti per l'aggiornamento.  Esistono 2 passaggi per questo processo, come illustrato di seguito.

   > [!Important] 
   > Dopo il ciclo di AAD Sync successivo dopo l'esecuzione di questo passaggio, gli utenti con Sistema telefonico spostati in precedenza da un Skype for Business Server locale al cloud perderanno la possibilità di effettuare e ricevere chiamate fino al completamento e alla conferma del passaggio 8 nel passaggio 9. Inoltre, assicurati di aver salvato i numeri di telefono e le informazioni correlate dell'utente secondo il passaggio 2, poiché queste informazioni sono necessarie per tale passaggio.

 
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

5. Eseguire il seguente cmdlet di Active Directory Windows PowerShell locale per aggiungere nuovamente il valore dell'indirizzo SIP ai proxyAddresses di Active Directory locali. In questo modo si evitano problemi di interoperabilità che si basano su questo attributo. 

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

7. Attendere il completamento del provisioning degli utenti. È possibile monitorare lo stato di avanzamento del provisioning degli utenti eseguendo il comando Skype for Business PowerShell online seguente. Il comando Skype for Business PowerShell online seguente restituisce un risultato vuoto non appena il processo viene completato.

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. Eseguire il seguente comando Skype for Business PowerShell online per assegnare numeri di telefono e abilitare gli utenti per Sistema telefonico:
     
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
   >  Se si dispone ancora di endpoint Skype for Business (client Skype o telefoni di terze parti), è anche necessario impostare -HostedVoiceMail su $true. Se l'organizzazione usa solo Teams endpoint per gli utenti abilitati alla funzionalità vocale, questa impostazione non è applicabile agli utenti. 

9. Verificare che il provisioning degli Sistema telefonico funzionalità sia stato eseguito correttamente. Il comando Skype for Business PowerShell online seguente restituisce un risultato vuoto non appena il processo viene completato.

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
    Skype for Business Comando PowerShell online:

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 
12. Dopo aver completato tutti i passaggi nel metodo 2, vedere Spostare gli endpoint dell'applicazione ibrida da locale a [online](decommission-move-on-prem-endpoints.md) e Rimuovere il [Skype for Business Server](decommission-remove-on-prem.md) locale per ulteriori passaggi per rimuovere la distribuzione locale di Skype for Business Server.


## <a name="see-also"></a>Vedere anche

- [Consolidamento cloud per Teams e Skype for Business](cloud-consolidation.md)

- [Rimuovi le autorizzazioni dell'ambiente locale Skype for Business](decommission-on-prem-overview.md)

