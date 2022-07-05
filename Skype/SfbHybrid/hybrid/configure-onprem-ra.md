---
title: Configurare un account risorsa in Skype for Business Server 2019
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
ms.localizationpriority: medium
ms.collection: ''
description: Configurare un account risorsa per Skype for Business Server 2019.
ms.openlocfilehash: ebaf79229097df8d3477b4d9b74504c278bfd59c
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615612"
---
# <a name="configure-resource-accounts"></a>Configurare gli account delle risorse

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Skype for Business Server implementazioni ibride 2019 usano solo i servizi cloud forniti da Phone System per la messaggistica unificata e non si integrano con Exchange Online. In Skype for Business Server 2019 è ora possibile usare le code di chiamata cloud e gli operatori automatici descritti in [Ecco cosa si ottiene con Sistema telefonico in Microsoft 365 o Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system).

Per usare un operatore automatico del sistema telefonico o una coda di chiamate con Skype for Business Server 2019, è necessario creare account di risorse che fungono da endpoint dell'applicazione e che possono essere assegnati a numeri di telefono, quindi usare l'interfaccia di amministrazione di Teams online per configurare la coda delle chiamate o l'operatore automatico. Questo account di risorsa può essere disponibile online (vedere [Gestire gli account delle risorse in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) per creare account delle risorse ospitati online) o in locale, come descritto in questo articolo. In genere sono presenti più nodi operatore automatico sistema telefonico o coda di chiamata, ognuno dei quali viene mappato a un account di risorse, che può essere ospitata online o in Skype for Business Server 2019.

Se si dispone di un operatore automatico di messaggistica unificata di Exchange e di un sistema di code di chiamate esistente, prima di passare a Exchange Server 2019 o Exchange Online, sarà necessario registrare manualmente i dettagli come descritto di seguito e quindi implementare un sistema completamente nuovo usando l'interfaccia di amministrazione di Teams.

## <a name="overview"></a>Panoramica

Se l'operatore automatico o la coda delle chiamate del sistema telefonico avrà bisogno di un numero di servizio, le varie dipendenze possono essere soddisfatte nella sequenza seguente:

1. Ottenere un numero di servizio.
2. Ottenere una [licenza gratuita Telefono di Microsoft Teams account risorsa](/MicrosoftTeams/teams-add-on-licensing/virtual-user) o una licenza del sistema telefonico a pagamento da usare con l'account della risorsa.
3. Creare l'account della risorsa. Per avere un account di risorsa associato, è necessario un operatore automatico o una coda di chiamate.
4. Attendere la sincronizzazione di Active Directory tra online e locale.
5. Assegnare la licenza Sistema telefonico all'account della risorsa.
6. Assegnare un numero di servizio all'account della risorsa.
7. Creare una coda di chiamate del sistema telefonico o un operatore automatico.
8. Associare l'account della risorsa a un operatore automatico o a una coda di chiamate: (New-CsApplicationInstanceAssociation).

Se l'operatore automatico o la coda delle chiamate è annidata sotto un operatore automatico di primo livello, l'account della risorsa associato richiede solo un numero di telefono se si vogliono più punti di ingresso nella struttura degli operatori automatici e delle code di chiamata.

Per reindirizzare le chiamate agli utenti dell'organizzazione che sono ospitati online, devono avere una licenza **di Sistema telefonico** ed essere abilitati per VoIP aziendale o avere Microsoft 365 o piani per chiamate Office 365. Vedere [Assegnare licenze di Microsoft Teams](/MicrosoftTeams/assign-teams-licenses). Per abilitarli per VoIP aziendale, è possibile usare Windows PowerShell. Ad esempio, eseguire:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

Se l'operatore automatico del sistema telefonico o la coda di chiamate che si sta creando verrà annidato e non sarà necessario un numero di telefono, il processo è:

1. Creare l'account della risorsa  
2. Attendere una sincronizzazione di Active Directory tra online e locale
3. Creare un operatore automatico o una coda di chiamate del sistema telefonico
4. Associare l'account della risorsa a un operatore automatico del sistema telefonico o a una coda di chiamate

## <a name="create-a-resource-account-with-a-phone-number"></a>Creare un account risorsa con un numero di telefono

La creazione di un account risorsa che usa un numero di telefono richiede l'esecuzione delle attività seguenti nell'ordine seguente:

1. Porta o ottieni un numero di servizio a pagamento o a pagamento. Il numero non può essere assegnato ad altri servizi vocali o account di risorse.

   Prima di assegnare un numero di telefono a un account di risorsa, è necessario ottenere o convertire i numeri di servizio a pagamento o a pagamento esistenti. Dopo aver ottenuto i numeri di telefono del servizio a pagamento o a pagamento, verranno visualizzati nell'interfaccia  >  di **amministrazione di Microsoft Teams****Numeri di telefono** **vocale** >  e il **tipo di numero** elencato sarà elencato come **Servizio - Numero verde**. Per ottenere i numeri di servizio, vedere [Ottenere i numeri di telefono del servizio](/MicrosoftTeams/getting-service-phone-numbers) o se si vuole trasferire un numero di servizio esistente, vedere [Trasferire i numeri di telefono a Teams](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams).

   Se si è al di fuori del Stati Uniti, non è possibile usare l'interfaccia di amministrazione di Microsoft Teams per ottenere i numeri di servizio. Passare invece a [Gestisci numeri di telefono per l'organizzazione](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) per vedere come eseguire questa operazione dall'esterno del Stati Uniti.

2. Acquistare una licenza del sistema telefonico. Vedere:  
   - [Telefono di Microsoft Teams licenza dell'account risorsa](/MicrosoftTeams/teams-add-on-licensing/virtual-user)
   - [Office 365 Enterprise E1 ed E3](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [Office 365 Enterprise E5](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [Office 365 Enterprise E5 Business Software](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. Creare un account di risorsa locale eseguendo il `New-CsHybridApplicationEndpoint` cmdlet per ogni operatore automatico o coda di chiamata del sistema telefonico e assegnando a ognuno un nome, un indirizzo sip e così via.

    ``` Powershell
    New-CsHybridApplicationEndpoint -ApplicationID <GUID> -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    Per altre informazioni su questo comando, vedere [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) .

4. (Facoltativo) Dopo aver creato gli account delle risorse, è possibile attendere la sincronizzazione di ACTIVE Directory tra online e locale oppure forzare una sincronizzazione e passare alla configurazione online dell'operatore automatico o delle code di chiamata del sistema telefonico. Per forzare una sincronizzazione, eseguire il comando seguente nel computer che esegue AAD Connect (se non è già stato fatto, è necessario caricare `import-module adsync` per eseguire il comando):

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    Per altre informazioni su questo comando, vedere [Start-ADSyncSyncCycle](/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) .

    Nota: a questo punto, l'account potrebbe essere stato sincronizzato, ma il provisioning potrebbe non essere completo.  Controllare l'output di [Get-CsOnlineApplicationEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint).  Se l'endpoint sincronizzato non ha ancora completato il provisioning, non verrà visualizzato qui.  È possibile controllare lo stato delle richieste di provisioning nel portale M365 in [Stato di installazione di Teams](https://admin.microsoft.com/AdminPortal/Home#/teamsprovisioning).  Questa fase di provisioning può richiedere fino a 24 ore.

5. Assegnare la licenza **Telefono di Microsoft Teams account risorsa** o **Teams Phone Standard** licenza all'account della risorsa. Vedere [Assegnare licenze per i componenti aggiuntivi di Microsoft Teams](/MicrosoftTeams/teams-add-on-licensing/assign-teams-add-on-licenses) e [Assegnare licenze agli utenti](/microsoft-365/admin/manage/assign-licenses-to-users).

   Se si assegna un numero di telefono a un account di risorsa, è ora possibile usare la licenza gratuita **Telefono di Microsoft Teams Account risorse**. Ciò offre funzionalità di sistema telefonico ai numeri di telefono a livello aziendale e consente di creare funzionalità di operatore automatico e coda di chiamata.

6. Assegnare il numero di servizio all'account della risorsa. Usare il `Set-CsHybridApplicationEndpoint` comando per assegnare un numero di telefono (con l'opzione -LineURI) all'account della risorsa.

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    Per altre informazioni su questo comando, vedere [Set-CsHybridApplicationEndpoint](/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) .

    Per assegnare un routing diretto o un numero ibrido a un account di risorse, usare il cmdlet seguente:

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

   L'account della risorsa avrà bisogno di un numero di telefono assegnato se verrà assegnato a un operatore automatico di primo livello o a una coda di chiamate. I numeri di telefono dell'utente (sottoscrittore) non possono essere assegnati a un account risorsa, è possibile usare solo i numeri di telefono a pagamento o a numero verde del servizio.

     È possibile assegnare un routing diretto o un numero ibrido all'account della risorsa. Per informazioni dettagliate, vedere [Pianificare l'instradamento diretto](/MicrosoftTeams/direct-routing-plan) e [gli operatori automatici di Plan Cloud](plan-cloud-auto-attendant.md).

     > [!NOTE]
     > I numeri di servizio di routing diretto assegnati agli account delle risorse per l'operatore automatico e le code di chiamata sono supportati solo per gli utenti e gli agenti di Microsoft Teams.

7. Creare l'operatore automatico o la coda delle chiamate del sistema telefonico. Visualizzare uno tra:

   - [Configurare un operatore automatico cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [Creare code delle chiamate nel cloud](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. Associare l'account della risorsa all'operatore automatico o alla coda delle chiamate del sistema telefonico scelto in precedenza.

## <a name="create-a-resource-account-without-a-phone-number"></a>Creare un account risorsa senza un numero di telefono

In questa sezione viene illustrata la creazione di un account di risorsa ospitato in locale. La creazione di un account risorsa disponibile online è illustrata [in Gestire gli account delle risorse in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts).

Questi passaggi sono necessari sia che si stia creando un nuovo operatore automatico sistema telefonico o una struttura della coda delle chiamate o ricompilare la struttura creata originariamente nella messaggistica unificata di Exchange.

Accedere al server front-end Skype for Business ed eseguire i cmdlet di PowerShell seguenti:

1. Creare un account di risorsa locale eseguendo il `New-CsHybridApplicationEndpoint` cmdlet per ogni operatore automatico o coda di chiamata del sistema telefonico e assegnando a ognuno un nome, un indirizzo sip e così via.

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    Per altre informazioni su questo comando, vedere [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) .

2. (Facoltativo) Dopo aver creato gli account delle risorse, è possibile attendere la sincronizzazione di ACTIVE Directory tra online e locale oppure forzare una sincronizzazione e passare alla configurazione online dell'operatore automatico o delle code di chiamata del sistema telefonico. Per forzare una sincronizzazione, eseguire il comando seguente nel computer che esegue AAD Connect (se non è già stato fatto, è necessario caricare `import-module adsync` per eseguire il comando):

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    Per altre informazioni su questo comando, vedere [Start-ADSyncSyncCycle](/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) .

3. Creare l'operatore automatico o la coda delle chiamate del sistema telefonico. Visualizzare uno tra:
   - [Configurare un operatore automatico cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [Creare code delle chiamate nel cloud](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. Associare l'account della risorsa e l'operatore automatico o la coda delle chiamate del sistema telefonico scelto in precedenza.

## <a name="test-the-implementation"></a>Testare l'implementazione

Il modo migliore per testare l'implementazione consiste nel chiamare il numero configurato per un operatore automatico o una coda di chiamate del sistema telefonico e connettersi a uno degli agenti o dei menu. È anche possibile effettuare rapidamente una chiamata di test usando il **pulsante Test** nel riquadro azione dell'interfaccia di amministrazione. Se si desidera apportare modifiche a un operatore automatico o a una coda di chiamate del sistema telefonico, selezionarlo e quindi nel riquadro Azione fare clic su **Modifica**. 

> [!TIP]
> Se l'account della risorsa ha difficoltà ad essere assegnato a una coda di chiamate o a un operatore automatico, vedere [Problemi noti per Microsoft Teams](/MicrosoftTeams/Known-issues#phone-system) e la sezione [Come correggere le istanze di applicazioni ibride](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521) nel blog di Microsoft Teams.

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a>Spostamento di un operatore automatico o di una coda di chiamate di messaggistica unificata di Exchange nel sistema telefonico

La migrazione dalla messaggistica unificata di Exchange al sistema telefonico richiederà la ricreazione della coda delle chiamate e della struttura dell'operatore automatico, la migrazione diretta da uno all'altro non è supportata. Per implementare nuovamente un set di code di chiamata e operatori automatici:

1. Ottenere un elenco di tutti gli operatori automatici di messaggistica unificata di Exchange e le code di chiamata eseguendo il comando seguente nel sistema Exchange 2013 o 2016 durante l'accesso come amministratore:

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. Per ogni coda di chiamate di messaggistica unificata di Exchange elencata o operatore automatico, prendere nota della sua posizione nella struttura, nelle impostazioni e nel recupero di copie dei file audio o di sintesi vocale associati (il GUID nell'output sarà il nome di una cartella in cui vengono archiviati i file). È possibile ottenere questi dettagli eseguendo il comando :

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    Per altre informazioni su questo comando, vedere [Get-UMAutoAttendant](/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) . Un elenco completo delle opzioni che potrebbe essere necessario acquisire è disponibile nei [membri UMAutoAttendant](/previous-versions/office/exchange-server-api/ff340649(v=exchg.150)) , ma le opzioni più importanti da prendere in considerazione sono:

    - Ore lavorative
    - Orario non lavorativo
    - Lingua
    - Pianificare festività

3. Creare nuovi endpoint locali come descritto in precedenza.
   Assegnare all'operatore automatico di primo livello un numero temporaneo a scopo di test.

4. Configurare un operatore automatico del sistema telefonico o una coda di chiamate che usa gli endpoint come descritto in precedenza.

5. Testare l'operatore automatico o la coda delle chiamate del sistema telefonico.

6. Riassegnare il numero di telefono collegato alla coda di chiamata o all'operatore automatico di messaggistica unificata di Exchange all'operatore automatico o alla coda delle chiamate del sistema telefonico corrispondente.  

   A questo punto, se è già stata eseguita la migrazione della segreteria telefonica di messaggistica unificata, è consigliabile essere in grado di eseguire la migrazione a Exchange Server 2019.

## <a name="see-also"></a>Vedere anche

[Creare code delle chiamate nel cloud](/MicrosoftTeams/create-a-phone-system-call-queue)

[Cosa sono gli operatori automatici cloud?](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[Configurare un operatore automatico cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[Pianificare gli operatori automatici cloud](plan-cloud-auto-attendant.md)

[Pianificare le code delle chiamate cloud](plan-call-queue.md)

[Pianificare Cloud Voicemail servizio per gli utenti locali](plan-cloud-voicemail.md)

[New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[New-CsOnlineApplicationInstance](/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[Gestire gli account delle risorse in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) - \( per creare account di risorse ospitati online\)