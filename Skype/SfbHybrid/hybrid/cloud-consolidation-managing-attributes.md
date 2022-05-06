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
description: Questo articolo descrive come gestire gli attributi dopo la rimozione dell'ambiente locale.
ms.openlocfilehash: b838b965430a007fa74320d7dbebdcf7ee36c3a9
ms.sourcegitcommit: 140c34f20f9cd48d7180ff03fddd60f5d1d3459f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2022
ms.locfileid: "65249018"
---
# <a name="decide-how-to-manage-attributes-after-decommissioning"></a>Decidere come gestire gli attributi dopo la rimozione delle autorizzazioni

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


Per impostazione predefinita, tutti gli utenti abilitati per Skype for Business Server e quindi spostati nel cloud hanno ancora attributi msRTCSIP configurati nel Active Directory locale. 

Questi attributi, in particolare l'indirizzo sip (msRTCSIP-PrimaryUserAddress) e il numero di telefono (msRTCSIP-Line), continuano a essere sincronizzati in Azure AD. Se sono necessarie modifiche a uno qualsiasi degli attributi msRTCSIP, queste modifiche devono essere apportate nel Active Directory locale e quindi sincronizzate con Azure AD. Tuttavia, una volta rimossa la distribuzione Skype for Business Server, gli strumenti di Skype for Business Server non saranno disponibili per gestire questi attributi.

Per gestire questa situazione sono disponibili due opzioni:

1. Lasciare gli utenti abilitati per Skype for Business account server così come sono e gestire gli attributi msRTCSIP usando gli strumenti di Active Directory. Questo metodo non garantisce alcuna perdita di servizio per gli utenti migrati e consente di rimuovere la distribuzione Skype for Business Server eliminando ( ad esempio, la cancellazione) dei server, senza una rimozione completa. Tuttavia, i nuovi utenti con licenza non avranno questi attributi popolati nel Active Directory locale e dovranno essere gestiti online.

2.  Cancellare tutti gli attributi msRTCSIP dagli utenti migrati nel Active Directory locale e gestire questi attributi usando gli strumenti online. Questo metodo consente un approccio di gestione coerente per utenti nuovi e esistenti. Tuttavia, può causare una perdita temporanea del servizio durante il processo di disattivazione locale.


## <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a>Metodo 1 - Gestire indirizzi sip e numeri di telefono per gli utenti in Active Directory

Gli amministratori possono gestire gli utenti che sono stati spostati da un Skype for Business Server locale al cloud, anche dopo che la distribuzione locale è stata rimossa. 

Se si desidera apportare modifiche all'indirizzo sip di un utente o al numero di telefono di un utente (e l'indirizzo sip o il numero di telefono ha già un valore nella Active Directory locale), è necessario apportare la modifica nel Active Directory locale e lasciare scorrere i valori fino a Azure AD. Questo metodo NON richiede Skype for Business Server locali. È invece possibile modificare questi attributi direttamente nel Active Directory locale, usando lo snap-in MMC Utenti e computer di Active Directory (come illustrato di seguito) o tramite PowerShell. Se si usa lo snap-in MMC, aprire la pagina delle proprietà dell'utente, fare clic sulla scheda Editor attributi e trovare gli attributi appropriati da modificare:

- Per modificare l'indirizzo sip di un utente, modificare .`msRTCSIP-PrimaryUserAddress`

    > [!NOTE]
    > Se l'attributo `ProxyAddresses` contiene un indirizzo sip, aggiornare anche tale valore come procedura consigliata. Anche se l'indirizzo sip in `ProxyAddresses` viene ignorato da O365 se `msRTCSIP-PrimaryUserAddress` viene popolato, può essere usato da altri componenti locali.

- Per modificare il numero di telefono di un utente, modificare `msRTCSIP-Line` *se ha già un valore*.

  ![Strumento per utenti e computer di Active Directory.](../media/disable-hybrid-1.png)


- Se in origine l'utente non aveva un valore per `msRTCSIP-Line` l'ambiente locale prima dello spostamento, è possibile modificare il numero di telefono usando il `-PhoneNumber` parametro nel [cmdlet Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment) nel modulo Teams PowerShell.

Questi passaggi non sono necessari per i nuovi utenti creati dopo la disabilitazione dell'ambiente ibrido e possono essere gestiti direttamente nel cloud. Se si ha familiarità con l'uso della combinazione di questi metodi e se si lasciano gli attributi msRTCSIP presenti nel Active Directory locale, è possibile ricreare l'immagine dei server Skype for Business locali. Tuttavia, se si preferisce cancellare tutti gli attributi msRTCSIP ed eseguire una disinstallazione tradizionale di Skype for Business Server, usare il metodo 2.


## <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a>Metodo 2- Cancellare gli attributi di Skype for Business per tutti gli utenti locali in Active Directory

Questa opzione richiede maggiore impegno e pianificazione appropriata perché è necessario effettuare di nuovo il provisioning degli utenti che sono stati spostati da un Skype for Business Server locale al cloud. Questi utenti possono essere classificati in due categorie diverse: utenti senza Sistema telefonico e utenti con Sistema telefonico. Gli utenti con Sistema telefonico si verificheranno una perdita temporanea del servizio telefonico durante la transizione del numero di telefono dalla gestione in Active Directory locale al cloud. **È consigliabile eseguire un progetto pilota che coinvolga un numero ridotto di utenti con Sistema telefonico prima di avviare le operazioni degli utenti in blocco.** Per le distribuzioni di grandi dimensioni, gli utenti possono essere elaborati in gruppi più piccoli in finestre temporali diverse. 

> [!NOTE] 
> Questo processo è più semplice per gli utenti che hanno un indirizzo SIP corrispondente e UserPrincipalName. Per le organizzazioni che hanno utenti con valori non corrispondenti tra questi due attributi, è necessario prestare maggiore attenzione come indicato di seguito per una transizione senza problemi.

> [!NOTE]
> Se sono stati configurati endpoint dell'applicazione ibrida locale per operatori automatici o code di chiamata, assicurarsi di spostarli in Microsoft 365 prima di rimuovere Skype for Business Server. Per informazioni dettagliate, vedere [Eseguire la migrazione degli endpoint dell'applicazione ibrida prima di rimuovere l'ambiente locale](decommission-move-on-prem-endpoints.md).  


1. Verificare che il seguente Skype for Business cmdlet di PowerShell restituisca un risultato vuoto. Un risultato vuoto indica che nessun utente è ospitato in locale e che è stato spostato in Microsoft 365 o è stato disabilitato:

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. Registrare il numero di telefono corrente degli utenti (LineUri), UserPrincipalName e le informazioni correlate, eseguendo il cmdlet di PowerShell Skype for Business Server locale seguente per esportare i dati utente:

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > Prima di procedere, aprire SfbUserSettings.csv file e verificare che tutti i dati utente siano stati esportati correttamente. È consigliabile conservare una copia di questo file.  Non usare questo file nei passaggi seguenti per l'elaborazione degli utenti. 

3. Creare un file con un gruppo di utenti da usare nei passaggi seguenti. Al termine del primo gruppo di utenti, procedere con il gruppo di utenti successivo. Nell'esempio seguente i gruppi di utenti vengono selezionati in ordine alfabetico. È possibile filtrare gli utenti in base a criteri che corrispondono al modo in cui si desidera elaborare gli utenti.

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > Prima di procedere, aprire SfbUsers.csv file e verificare che i dati utente siano stati esportati correttamente. In un passaggio successivo saranno necessari LineUri (numero di telefono), UserPrincipalName, SamAccountName e SipAddress di questo file.

4. Eliminare le informazioni sull'attributo correlate a Skype for Business Server da Active Directory per il set di utenti che si è pronti per l'aggiornamento.  Questo processo è sottoposto a due passaggi, come illustrato di seguito.

   > [!Important] 
   > Dopo il ciclo di AAD Sync successivo dopo l'esecuzione di questo passaggio, gli utenti con Sistema telefonico che sono stati spostati da un Skype for Business Server locale al cloud perderanno la possibilità di effettuare e ricevere chiamate fino al completamento e alla conferma del passaggio 8 nel passaggio 9. Assicurarsi inoltre di aver salvato i numeri di telefono dell'utente e le informazioni correlate in base al passaggio 2, poiché tali informazioni sono necessarie per tale passaggio.

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   Successivamente, per lo stesso set di utenti, cancellare il valore di msRTCSIP-DeploymentLocator usando Active Directory locale PowerShell:

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. Per aggiungere nuovamente il valore dell'indirizzo sip al Active Directory locale proxyAddresses, eseguire il seguente Active Directory locale Module per Windows PowerShell cmdlet. Questa azione impedirà i problemi di interoperabilità che si basano su questo attributo. 

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

7. Attendere il completamento del provisioning degli utenti. È possibile monitorare lo stato di avanzamento del provisioning degli utenti eseguendo il comando di PowerShell Teams seguente. Il comando di PowerShell Teams seguente restituisce un risultato vuoto non appena il processo viene completato.

   ```PowerShell
   Get-CsOnlineUser -Filter {IsSipEnabled -eq $True} | Where UserValidationErrors -ne $null | Select SipAddress,InterpretedUserType,UserValidationErrors
   ```

8. Per assegnare numeri di telefono e abilitare gli utenti per Sistema telefonico, eseguire il comando di PowerShell Teams seguente:


   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   if($user.LineUri)
        {
             Set-CsPhoneNumberAssignment -Identity $user.SipAddress -PhoneNumber $user.LineUri.Replace("tel:","") -PhoneNumberType DirectRouting
        }
   }
   ```

   > [!Note]
   >  Se sono ancora presenti endpoint Skype for Business (Skype client o telefoni di terze parti), è anche necessario impostare -HostedVoiceMail su $true. Se l'organizzazione usa solo endpoint Teams per gli utenti abilitati per la voce, questa impostazione non è applicabile agli utenti. 

9. Verificare che il provisioning degli utenti con funzionalità Sistema telefonico sia stato eseguito correttamente. Il comando di PowerShell Teams seguente restituisce un risultato vuoto non appena il processo viene completato.

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers)
   {
   if($user.LineUri)
        {
                $u=Get-CsOnlineUser -Identity $user.SipAddress
                if ($u.LineURI -ne $user.LineUri -or $u.EnterpriseVoiceEnabled -ne $true)
                {
                Get-CsOnlineUser -Identity $user.SipAddress | fl SipAddress, InterpretedUserType, OnPremLineURI, LineURI, EnterpriseVoiceEnabled
                }
        }
   }
   ``` 

10. Ripetere i passaggi da 3 a 9 fino a quando tutti gli utenti non vengono elaborati.

11. Verificare che tutti gli utenti siano stati elaborati correttamente eseguendo i due comandi di PowerShell seguenti.

    Comando di PowerShell locale Skype for Business Server locale:

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 

    Teams comando di PowerShell:

    ```PowerShell
    Get-CsOnlineUser -Filter {IsSipEnabled -eq $True} | where {UserValidationErrors -ne $null} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, UserValidationErrors
    ``` 

12. Dopo aver completato tutti i passaggi del metodo 2, vedere [Spostare gli endpoint dell'applicazione ibrida dall'ambiente locale a quello online](decommission-move-on-prem-endpoints.md) e [Rimuovere il Skype for Business Server locale](decommission-remove-on-prem.md) per altri passaggi per rimuovere la distribuzione locale Skype for Business Server.


## <a name="see-also"></a>Vedere anche

- [Consolidamento cloud per Teams e Skype for Business](cloud-consolidation.md)

- [Rimuovi le autorizzazioni dell'ambiente locale Skype for Business](decommission-on-prem-overview.md)

