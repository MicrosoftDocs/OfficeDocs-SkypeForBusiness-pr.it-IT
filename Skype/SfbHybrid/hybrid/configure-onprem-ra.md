---
title: Configurare un account di risorsa in Skype for Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
ms.audience: ITPro
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Configurare un account di risorsa per Skype for Business Server 2019.
ms.openlocfilehash: 1d8294eb717982b5ac68df06a5370059e83a62c5
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "49919012"
---
# <a name="configure-resource-accounts"></a>Configurare gli account delle risorse

Le implementazioni ibride di Skype for Business Server 2019 utilizzano solo i servizi cloud forniti da Sistema telefonico per la messaggistica unificata e non si integrano con Exchange Online. In Skype for Business Server 2019 ora è possibile usare le code di chiamata cloud e gli operatori automatici descritti in Ecco cosa si ottiene con Sistema telefonico [in Microsoft 365 o Office 365.](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

Per usare un operatore automatico sistema telefonico o una coda di chiamata con Skype for Business Server 2019, è necessario creare account delle risorse che fungono da endpoint applicazione e a cui possono essere assegnati numeri di telefono, quindi utilizzare l'interfaccia di amministrazione di Teams online per configurare la coda di chiamata o l'operatore automatico. Questo account di risorsa può essere ospitato online (vedere Gestire gli account delle risorse [in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) per creare account delle risorse ospitati online) o in locale, come descritto in questo articolo. In genere, saranno presenti più nodi dell'operatore automatico o della coda di chiamata del sistema telefonico, ognuno dei quali è mappato a un account delle risorse, che può essere disponibile online o in Skype for Business Server 2019.

Se si dispone di un operatore automatico di messaggistica unificata di Exchange esistente e di un sistema di coda delle chiamate, prima di passare a Exchange Server 2019 o Exchange online sarà necessario registrare manualmente i dettagli come descritto di seguito e quindi implementare un sistema completamente nuovo utilizzando l'interfaccia di amministrazione di Teams.

## <a name="overview"></a>Panoramica

Se l'operatore automatico o la coda di chiamata del sistema telefonico necessitano di un numero di servizio, le varie dipendenze possono essere soddisfatte nella sequenza seguente:

1. Ottenere un numero di servizio.
2. Ottenere una licenza gratuita sistema telefonico - [Utente virtuale](/MicrosoftTeams/teams-add-on-licensing/virtual-user) o una licenza sistema telefonico a pagamento da usare con l'account della risorsa.
3. Creare l'account della risorsa. È necessario che un operatore automatico o una coda di chiamata abbia un account di risorsa associato.
4. Attendi una sincronizzazione di Active Directory tra online e locale.
5. Assegna la licenza di Sistema telefonico all'account della risorsa.
6. Assegnare un numero di servizio all'account della risorsa.
7. Creare una coda di chiamata o un operatore automatico di Sistema telefonico.
8. Associare l'account della risorsa a un operatore automatico o a una coda di chiamata: (New-CsApplicationInstanceAssociation).

Se l'operatore automatico o la coda di chiamata è annidata sotto un operatore automatico di primo livello, l'account della risorsa associato necessita solo di un numero di telefono se si desidera inserire più punti di ingresso nella struttura degli operatori automatici e delle code di chiamata.

Per reindirizzare le chiamate alle persone dell'organizzazione  ospitate online, devono disporre di una licenza sistema telefonico ed essere abilitate per VoIP aziendale o avere Piani per chiamate di Microsoft 365 o Office 365. Vedere [Assegnare licenze di Microsoft Teams.](/MicrosoftTeams/assign-teams-licenses) Per abilitarli per VoIP aziendale, è possibile utilizzare Windows PowerShell. Ad esempio, eseguire:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

Se l'operatore automatico del sistema telefonico o la coda di chiamata che si sta creando sarà annidata e non sarà necessario un numero di telefono, il processo è:

1. Creare l'account della risorsa  
2. Attendere una sincronizzazione di Active Directory tra online e locale
3. Creare un operatore automatico o una coda di chiamata di Sistema telefonico
4. Associare l'account della risorsa a un operatore automatico o a una coda di chiamata di Sistema telefonico

## <a name="create-a-resource-account-with-a-phone-number"></a>Creare un account della risorsa con un numero di telefono

La creazione di un account di risorsa che utilizza un numero di telefono richiederebbe l'esecuzione delle attività seguenti nell'ordine seguente:

1. Porta o ottieni un numero di servizio a numero verde o a numero verde. Il numero non può essere assegnato ad altri servizi vocali o account di risorse.

   Prima di assegnare un numero di telefono a un account di risorsa, dovrai ottenere o convertire i numeri di servizio a numero verde o a numero verde esistenti. After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center**  >  **Voice**  >  **Phone numbers**, and the Number **type** listed will be listed as Service **- Toll-Free**. Per ottenere i numeri di servizio, [vedere](/MicrosoftTeams/getting-service-phone-numbers) Ottenere numeri di telefono di servizio o se si desidera trasferire un numero di servizio esistente, vedere Trasferire numeri di telefono [in Teams.](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams)

   Se ci si trova al di fuori degli Stati Uniti, non è possibile utilizzare l'interfaccia di amministrazione di Microsoft Teams per ottenere i numeri di servizio. Vai invece [a Gestire i numeri di telefono](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) per la tua organizzazione per vedere come farlo dall'esterno degli Stati Uniti.

2. Acquistare una licenza di Sistema telefonico. Vedere:  
   - [Sistema telefonico -Licenza utente virtuale](/MicrosoftTeams/teams-add-on-licensing/virtual-user)
   - [Office 365 Enterprise E1 ed E3](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [Office 365 Enterprise E5](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [Office 365 Enterprise E5 Business Software](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. Creare un account di risorsa locale eseguendo il cmdlet per ogni operatore automatico o coda di chiamata di Sistema telefonico e assegnare a ognuno un nome, un indirizzo `New-CsHybridApplicationEndpoint` SIP e così via.

    ``` Powershell
    New-CsHybridApplicationEndpoint -ApplicationID <GUID> -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    Per ulteriori informazioni su questo comando, vedere [New-CsHybridApplicationEndpoint.](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

4. (Facoltativo) Dopo aver creato gli account delle risorse, puoi attendere la sincronizzazione di AD tra online e locale oppure forzare una sincronizzazione e procedere alla configurazione online dell'operatore automatico sistema telefonico o delle code di chiamata. Per forzare una sincronizzazione, eseguire il comando seguente nel computer che esegue AAD Connect (se non lo è già stato, è necessario caricarlo per `import-module adsync` eseguire il comando):

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    Per ulteriori dettagli su questo comando, vedere [Start-ADSyncSyncCycle.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler)
    
    Nota: a questo punto, è possibile che l'account sia stato sincronizzato, ma il provisioning potrebbe non essere completato.  Controllare l'output [di Get-CsOnlineApplicationEndpoint.](https://docs.microsoft.com/powershell/module/skype/get-csonlineapplicationendpoint)  Se l'endpoint sincronizzato non ha ancora completato il provisioning, non verrà visualizzato qui.  È possibile controllare lo stato delle richieste di provisioning nel portale M365 in [Stato di installazione di Teams.](https://admin.microsoft.com/AdminPortal/Home#/teamsprovisioning)  Questa fase di provisioning può richiedere fino a 24 ore.

5. Assegna la licenza Sistema telefonico - Utente virtuale o Sistema telefonico all'account della risorsa. Vedere [Assegnare licenze per i componenti aggiuntivi di Microsoft Teams](/MicrosoftTeams/teams-add-on-licensing/assign-teams-add-on-licenses) e [Assegnare licenze agli utenti.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)

   Se si assegna un numero di telefono a un account della risorsa, è ora possibile utilizzare la licenza Sistema telefonico - Utente virtuale gratuita. Ciò offre funzionalità di Sistema telefonico ai numeri di telefono a livello dell'organizzazione e consente di creare funzionalità di operatore automatico e coda di chiamata.


6. Assegnare il numero di servizio all'account della risorsa. Usa il `Set-CsHybridApplicationEndpoint` comando per assegnare un numero di telefono (con l'opzione -LineURI) all'account della risorsa.

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    Per ulteriori informazioni su questo comando, vedere [Set-CsHybridApplicationEndpoint.](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps)

    Per assegnare un instradamento diretto o un numero ibrido a un account di risorsa, utilizzare il cmdlet seguente:

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

   L'account della risorsa avrà bisogno di un numero di telefono assegnato se verrà assegnato a un operatore automatico di primo livello o a una coda di chiamata. I numeri di telefono dell'utente (sottoscrittore) non possono essere assegnati a un account di risorsa, ma solo numeri di telefono a numero verde o a numero verde di servizio.

     È possibile assegnare un instradamento diretto o un numero ibrido all'account della risorsa. Per informazioni dettagliate, vedere [Plan Direct Routing](/MicrosoftTeams/direct-routing-plan) and Plan Cloud auto [attendants.](plan-cloud-auto-attendant.md)

     > [!NOTE]
     > I numeri di servizio instradamento diretto assegnati agli account delle risorse per l'operatore automatico e le code di chiamata sono supportati solo per gli utenti e gli agenti di Microsoft Teams.

7. Creare l'operatore automatico sistema telefonico o la coda di chiamata. Visualizzare uno tra:

   - [Configurare un operatore automatico cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [Creare una coda di chiamata cloud](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. Associare l'account della risorsa all'operatore automatico sistema telefonico o alla coda di chiamata scelta in precedenza.

## <a name="create-a-resource-account-without-a-phone-number"></a>Creare un account della risorsa senza un numero di telefono

In questa sezione viene illustrata la creazione di un account di risorsa che si trova in locale. La creazione di un account di risorsa disponibile online è illustrata in [Gestire gli account delle risorse in Microsoft Teams.](/MicrosoftTeams/manage-resource-accounts)

Questi passaggi sono necessari indipendentemente dal fatto che si crei un operatore automatico sistema telefonico o una struttura della coda di chiamata nuova o che si ricostrui la struttura originariamente creata nella messaggistica unificata di Exchange.

Accedere al front-end server Skype for Business ed eseguire i cmdlet di PowerShell seguenti:

1. Creare un account di risorsa locale eseguendo il cmdlet per ogni operatore automatico o coda di chiamata di Sistema telefonico e assegnare a ognuno un nome, un indirizzo `New-CsHybridApplicationEndpoint` SIP e così via.

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    Per ulteriori informazioni su questo comando, vedere [New-CsHybridApplicationEndpoint.](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

2. (Facoltativo) Dopo aver creato gli account delle risorse, puoi attendere la sincronizzazione di AD tra online e locale oppure forzare una sincronizzazione e procedere alla configurazione online dell'operatore automatico sistema telefonico o delle code di chiamata. Per forzare una sincronizzazione, eseguire il comando seguente nel computer che esegue AAD Connect (se non lo è già stato, è necessario caricarlo per `import-module adsync` eseguire il comando):

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    Per ulteriori dettagli su questo comando, vedere [Start-ADSyncSyncCycle.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler)

3. Creare l'operatore automatico sistema telefonico o la coda di chiamata. Visualizzare uno tra:
   - [Configurare un operatore automatico cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [Creare una coda di chiamata cloud](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. Associare l'account della risorsa e l'operatore automatico sistema telefonico o la coda di chiamata scelta in precedenza.

## <a name="test-the-implementation"></a>Testare l'implementazione

Il modo migliore per testare l'implementazione è chiamare il numero configurato per un operatore automatico o una coda di chiamata di Sistema telefonico e connettersi a uno degli agenti o menu. È inoltre possibile eseguire rapidamente una chiamata di prova utilizzando il **pulsante Test** nel riquadro azioni dell'interfaccia di amministrazione. Se si desidera apportare modifiche a un operatore automatico o a una coda di chiamata di Sistema telefonico, selezionarlo e quindi fare clic su Modifica nel riquadro **Azioni.** 

> [!TIP]
> Se l'account della risorsa presenta difficoltà nell'assegnazione a una coda di [](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521) chiamata o a un operatore automatico, vedere Problemi noti per [Microsoft Teams](/MicrosoftTeams/Known-issues#phone-system) e la sezione come risolvere le istanze dell'applicazione ibrida nel blog di Microsoft Teams.

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a>Spostamento di un operatore automatico o di una coda di chiamata di messaggistica unificata di Exchange in Sistema telefonico

La migrazione dalla messaggistica unificata di Exchange al sistema telefonico richiederà la ricreazione della coda di chiamata e della struttura dell'operatore automatico, la migrazione diretta dall'uno all'altro non è supportata. Per implementare di nuovo un set di code di chiamata e operatori automatici:

1. Ottenere un elenco di tutti gli operatori automatici di messaggistica unificata di Exchange e le code di chiamata eseguendo il seguente comando sul sistema Exchange 2013 o 2016 mentre si è connessi come amministratore:

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. Per ogni coda di chiamata o operatore automatico di messaggistica unificata di Exchange elencato, prendere nota della sua posizione nella struttura, delle impostazioni e ottenere copie dei file audio o di sintesi vocale associati (il GUID nell'output sarà il nome di una cartella in cui sono archiviati i file). Puoi ottenere questi dettagli eseguendo il comando:

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    Per ulteriori informazioni su questo comando, vedere [Get-UMAutoAttendant.](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) Un elenco completo delle opzioni che potrebbe essere necessario acquisire è disponibile presso i membri [umAutoAttendant,](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx) ma le opzioni più importanti da prendere nota sono:

    - Ore lavorative
    - Orario non di ufficio
    - Lingua
    - Pianificazione festività

3. Creare nuovi endpoint locali come descritto in precedenza.
   Assegnare all'operatore automatico di primo livello un numero temporaneo a scopo di test.

4. Configurare un operatore automatico o una coda di chiamata di Sistema telefonico che utilizza gli endpoint come descritto in precedenza.

5. Testare l'operatore automatico o la coda di chiamata di Sistema telefonico.

6. Riassegnare il numero di telefono collegato alla coda di chiamata o all'operatore automatico di messaggistica unificata di Exchange all'operatore automatico sistema telefonico o alla coda di chiamata corrispondente.  

   A questo punto, se è già stata eseguita la migrazione della segreteria telefonica di messaggistica unificata, è necessario essere in grado di eseguire la migrazione a Exchange Server 2019.

## <a name="see-also"></a>Vedere anche

[Creare una coda di chiamata cloud](/MicrosoftTeams/create-a-phone-system-call-queue)

[Cosa sono gli operatori automatici cloud?](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[Configurare un operatore automatico cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[Pianificare gli operatori automatici cloud](plan-cloud-auto-attendant.md)

[Pianificare le code delle chiamate cloud](plan-call-queue.md)

[Pianificare il servizio Cloud Voicemail per gli utenti locali](plan-cloud-voicemail.md)

[New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[Gestire gli account delle risorse in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts)  -  \( per creare account delle risorse ospitati online\)
