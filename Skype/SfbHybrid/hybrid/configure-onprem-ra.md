---
title: Configurare un account di risorsa in Skype for Business Server 2019
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
ms.openlocfilehash: eb8f82a9551c3607068b0d62cc04518d58d09987
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118935"
---
# <a name="configure-resource-accounts"></a>Configurare gli account delle risorse

Le implementazioni ibride di Skype for Business Server 2019 utilizzano solo i servizi cloud forniti da Sistema telefonico per la messaggistica unificata e non si integrano con Exchange Online. In Skype for Business Server 2019 ora puoi usare le code di chiamata cloud e gli operatori automatici descritti in Ecco cosa ottieni con Sistema telefonico [in Microsoft 365 o Office 365.](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

Per utilizzare un operatore automatico del sistema telefonico o una coda di chiamata con Skype for Business Server 2019, è necessario creare account di risorse che fungono da endpoint dell'applicazione e a cui è possibile assegnare numeri di telefono, quindi utilizzare l'interfaccia di amministrazione di Teams online per configurare la coda di chiamata o l'operatore automatico. Questo account di risorsa può essere ospitato online (vedere Gestire gli account delle risorse [in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) per creare account delle risorse ospitati online) o in locale, come descritto in questo articolo. In genere si avranno più nodi dell'operatore automatico o della coda di chiamata del sistema telefonico, ognuno dei quali è mappato a un account di risorse, che può essere ospitato online o in Skype for Business Server 2019.

Se si dispone di un operatore automatico di messaggistica unificata di Exchange esistente e di un sistema di coda delle chiamate, prima di passare a Exchange Server 2019 o Exchange online, sarà necessario registrare manualmente i dettagli come descritto di seguito e quindi implementare un sistema completamente nuovo utilizzando l'interfaccia di amministrazione di Teams.

## <a name="overview"></a>Panoramica

Se l'operatore automatico del sistema telefonico o la coda di chiamata avrà bisogno di un numero di servizio, le varie dipendenze possono essere soddisfatte nella sequenza seguente:

1. Ottenere un numero di servizio.
2. Ottenere un sistema telefonico gratuito - [Licenza utente virtuale](/MicrosoftTeams/teams-add-on-licensing/virtual-user) o una licenza del sistema telefonico a pagamento da utilizzare con l'account della risorsa.
3. Creare l'account della risorsa. Un operatore automatico o una coda di chiamata deve disporre di un account di risorsa associato.
4. Attendere una sincronizzazione di Active Directory tra online e locale.
5. Assegnare la licenza di Sistema telefonico all'account della risorsa.
6. Assegnare un numero di servizio all'account della risorsa.
7. Creare una coda di chiamata del sistema telefonico o un operatore automatico.
8. Associare l'account della risorsa a un operatore automatico o a una coda di chiamata: (New-CsApplicationInstanceAssociation).

Se l'operatore automatico o la coda di chiamata è annidata sotto un operatore automatico di primo livello, l'account della risorsa associato necessita solo di un numero di telefono se si desidera che più punti di ingresso nella struttura degli operatori automatici e delle code di chiamata.

Per reindirizzare le chiamate agli utenti dell'organizzazione  ospitati online, devono disporre di una licenza di Sistema telefonico ed essere abilitati per VoIP aziendale o disporre di Piani di chiamata di Microsoft 365 o Office 365. Vedere [Assegnare licenze di Microsoft Teams.](/MicrosoftTeams/assign-teams-licenses) Per abilitarli per VoIP aziendale, puoi usare Windows PowerShell. Ad esempio, eseguire:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

Se l'operatore automatico del sistema telefonico o la coda di chiamata che si sta creando sarà annidata e non sarà necessario un numero di telefono, il processo è:

1. Creare l'account della risorsa  
2. Attendere una sincronizzazione di Active Directory tra online e locale
3. Creare un operatore automatico del sistema telefonico o una coda di chiamata
4. Associare l'account della risorsa a un operatore automatico del sistema telefonico o a una coda di chiamata

## <a name="create-a-resource-account-with-a-phone-number"></a>Creare un account di risorsa con un numero di telefono

La creazione di un account di risorsa che utilizza un numero di telefono richiederebbe l'esecuzione delle attività seguenti nell'ordine seguente:

1. Porta o ottieni un numero di servizio a numero verde o a numero verde. Il numero non può essere assegnato ad altri servizi vocali o account di risorse.

   Prima di assegnare un numero di telefono a un account di risorsa, è necessario ottenere o convertire i numeri di servizio a numero verde o a numero verde esistenti. Dopo aver visualizzato i numeri di telefono del servizio a numero verde o a numero verde, questi verranno visualizzati nell'interfaccia di amministrazione di **Microsoft Teams** Numeri di telefono vocali e il tipo di numero elencato verrà elencato come  >    >  Servizio - **Numero verde.**  Per ottenere i numeri di servizio, vedere [Ottenere](/MicrosoftTeams/getting-service-phone-numbers) numeri di telefono del servizio o se si desidera trasferire un numero di servizio esistente, vedere Trasferire numeri di [telefono in Teams](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams).

   Se ci si trova al di fuori degli Stati Uniti, non è possibile utilizzare l'interfaccia di amministrazione di Microsoft Teams per ottenere i numeri di servizio. Vai a [Gestire i numeri di telefono](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) per l'organizzazione invece per vedere come farlo dall'esterno degli Stati Uniti.

2. Acquistare una licenza del sistema telefonico. Vedere:  
   - [Sistema telefonico-Licenza utente virtuale](/MicrosoftTeams/teams-add-on-licensing/virtual-user)
   - [Office 365 Enterprise E1 ed E3](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [Office 365 Enterprise E5](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [Office 365 Enterprise E5 Business Software](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. Creare un account di risorsa locale eseguendo il cmdlet per ogni operatore automatico o coda di chiamata del sistema telefonico e assegnare a ognuno un nome, un indirizzo `New-CsHybridApplicationEndpoint` SIP e così via.

    ``` Powershell
    New-CsHybridApplicationEndpoint -ApplicationID <GUID> -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    Per ulteriori informazioni su questo comando, vedere [New-CsHybridApplicationEndpoint.](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

4. (Facoltativo) Dopo aver creato gli account delle risorse, è possibile attendere la sincronizzazione di Active Directory tra online e locali oppure forzare una sincronizzazione e procedere alla configurazione online dell'operatore automatico del sistema telefonico o delle code di chiamata. Per forzare una sincronizzazione, eseguire il comando seguente nel computer che esegue AAD Connect (se non lo si è già fatto, è necessario caricarlo per `import-module adsync` eseguire il comando):

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    Per ulteriori dettagli su questo comando, vedere [Start-ADSyncSyncCycle.](/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler)
    
    Nota: a questo punto, l'account potrebbe essere stato sincronizzato, ma il provisioning potrebbe non essere completato.  Controllare l'output di [Get-CsOnlineApplicationEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint).  Se l'endpoint sincronizzato non ha ancora completato il provisioning, non verrà visualizzato qui.  Puoi controllare lo stato delle richieste di provisioning nel portale M365 in [Teams Setup Status](https://admin.microsoft.com/AdminPortal/Home#/teamsprovisioning).  Questa fase di provisioning può richiedere fino a 24 ore.

5. Assegnare la licenza Sistema telefonico - Utente virtuale o Sistema telefonico all'account della risorsa. Vedere [Assegnare licenze dei componenti aggiuntivi di Microsoft Teams](/MicrosoftTeams/teams-add-on-licensing/assign-teams-add-on-licenses) e [Assegnare licenze agli utenti.](/microsoft-365/admin/manage/assign-licenses-to-users)

   Se stai assegnando un numero di telefono a un account di risorsa, ora puoi usare la licenza Sistema telefonico gratuito - Utente virtuale. In questo modo sono disponibili funzionalità del sistema telefonico per i numeri di telefono a livello dell'organizzazione e consente di creare funzionalità di operatore automatico e coda di chiamata.


6. Assegnare il numero di servizio all'account della risorsa. Utilizzare il `Set-CsHybridApplicationEndpoint` comando per assegnare un numero di telefono (con l'opzione -LineURI) all'account della risorsa.

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    Per ulteriori informazioni su questo comando, vedere [Set-CsHybridApplicationEndpoint.](/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps)

    Per assegnare un routing diretto o un numero ibrido a un account di risorsa, utilizzare il cmdlet seguente:

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

   L'account della risorsa avrà bisogno di un numero di telefono assegnato se verrà assegnato a un operatore automatico di primo livello o a una coda di chiamata. I numeri di telefono dell'utente (sottoscrittore) non possono essere assegnati a un account di risorsa, ma possono essere utilizzati solo numeri a numero verde o a numero verde del servizio.

     Puoi assegnare un instradamento diretto o un numero ibrido all'account della risorsa. Per informazioni dettagliate, vedere [Plan Direct Routing](/MicrosoftTeams/direct-routing-plan) e Plan Cloud auto [attendants.](plan-cloud-auto-attendant.md)

     > [!NOTE]
     > I numeri di servizio di instradamento diretto assegnati agli account delle risorse per l'operatore automatico e le code di chiamata sono supportati solo per gli utenti e gli agenti di Microsoft Teams.

7. Creare l'operatore automatico sistema telefonico o la coda di chiamata. Visualizzare uno tra:

   - [Configurare un operatore automatico cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [Creare una coda di chiamata cloud](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. Associare l'account della risorsa all'operatore automatico sistema telefonico o alla coda di chiamata scelta in precedenza.

## <a name="create-a-resource-account-without-a-phone-number"></a>Creare un account di risorsa senza un numero di telefono

In questa sezione viene illustrata la creazione di un account di risorsa che si trova in locale. La creazione di un account di risorsa che si trova online è illustrata in [Gestire gli account delle risorse in Microsoft Teams.](/MicrosoftTeams/manage-resource-accounts)

Questi passaggi sono necessari indipendentemente dal fatto che si crei un nuovo operatore automatico sistema telefonico o una struttura della coda di chiamata o che si ricompila la struttura creata originariamente nella messaggistica unificata di Exchange.

Accedere al server front-end Skype for Business ed eseguire i cmdlet di PowerShell seguenti:

1. Creare un account di risorsa locale eseguendo il cmdlet per ogni operatore automatico o coda di chiamata del sistema telefonico e assegnare a ognuno un nome, un indirizzo `New-CsHybridApplicationEndpoint` SIP e così via.

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    Per ulteriori informazioni su questo comando, vedere [New-CsHybridApplicationEndpoint.](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

2. (Facoltativo) Dopo aver creato gli account delle risorse, è possibile attendere la sincronizzazione di Active Directory tra online e locali oppure forzare una sincronizzazione e procedere alla configurazione online dell'operatore automatico del sistema telefonico o delle code di chiamata. Per forzare una sincronizzazione, eseguire il comando seguente nel computer che esegue AAD Connect (se non lo si è già fatto, è necessario caricarlo per `import-module adsync` eseguire il comando):

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    Per ulteriori dettagli su questo comando, vedere [Start-ADSyncSyncCycle.](/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler)

3. Creare l'operatore automatico sistema telefonico o la coda di chiamata. Visualizzare uno tra:
   - [Configurare un operatore automatico cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [Creare una coda di chiamata cloud](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. Associare l'account della risorsa e l'operatore automatico sistema telefonico o la coda di chiamata scelta in precedenza.

## <a name="test-the-implementation"></a>Testare l'implementazione

Il modo migliore per testare l'implementazione è chiamare il numero configurato per un operatore automatico del sistema telefonico o una coda di chiamata e connettersi a uno degli agenti o menu. Puoi anche eseguire rapidamente una chiamata di test usando il **pulsante Test** nel riquadro azioni dell'interfaccia di amministrazione. Se si desidera apportare modifiche a un operatore automatico del sistema telefonico o a una coda di chiamata, selezionarlo e quindi fare clic su Modifica nel riquadro **Azioni.** 

> [!TIP]
> Se l'account della risorsa presenta difficoltà con l'assegnazione a una coda di chiamata o a un operatore automatico, vedere Problemi noti per [Microsoft Teams](/MicrosoftTeams/Known-issues#phone-system) e la sezione [Come](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521) risolvere le istanze dell'applicazione ibrida nel blog di Microsoft Teams.

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a>Spostamento di un operatore automatico di messaggistica unificata di Exchange o di una coda di chiamata nel sistema telefonico

La migrazione dalla messaggistica unificata di Exchange al sistema telefonico richiederà la ricreazione della coda di chiamata e della struttura dell'operatore automatico, non è supportata la migrazione diretta dall'uno all'altro. Per implementare di nuovo un set di code di chiamata e operatori automatici:

1. Ottenere un elenco di tutti gli operatori automatici e le code di chiamata di messaggistica unificata di Exchange eseguendo il comando seguente nel sistema Exchange 2013 o 2016 durante l'accesso come amministratore:

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. Per ogni coda di chiamata o operatore automatico di messaggistica unificata di Exchange elencato, annotare la posizione nella struttura, nelle impostazioni e ottenere copie dei file audio o di sintesi vocale associati (il guid nell'output sarà il nome di una cartella in cui sono archiviati i file). È possibile ottenere questi dettagli eseguendo il comando:

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    Per ulteriori informazioni su questo comando, vedere [Get-UMAutoAttendant.](/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) Un elenco completo delle opzioni che potrebbe essere necessario acquisire è disponibile nei membri [UMAutoAttendant,](/previous-versions/office/exchange-server-api/ff340649(v=exchg.150)) ma le opzioni più importanti da prendere nota sono:

    - Ore lavorative
    - Orario non di ufficio
    - Lingua
    - Pianificazione festività

3. Creare nuovi endpoint locali come descritto in precedenza.
   Assegnare all'operatore automatico di primo livello un numero temporaneo a scopo di test.

4. Configurare un operatore automatico del sistema telefonico o una coda di chiamata che utilizza gli endpoint come descritto in precedenza.

5. Testare l'operatore automatico sistema telefonico o la coda di chiamata.

6. Riassegnare il numero di telefono collegato alla coda di chiamata o all'operatore automatico di messaggistica unificata di Exchange all'operatore automatico sistema telefonico o alla coda di chiamata corrispondente.  

   A questo punto, se è già stata eseguita la migrazione della segreteria telefonica di messaggistica unificata, è necessario essere in grado di eseguire la migrazione a Exchange Server 2019.

## <a name="see-also"></a>Vedere anche

[Creare una coda di chiamata cloud](/MicrosoftTeams/create-a-phone-system-call-queue)

[Cosa sono gli operatori automatici cloud?](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[Configurare un operatore automatico cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[Pianificare gli operatori automatici cloud](plan-cloud-auto-attendant.md)

[Pianificare le code delle chiamate cloud](plan-call-queue.md)

[Pianificare il servizio Cloud Voicemail per gli utenti locali](plan-cloud-voicemail.md)

[New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[New-CsOnlineApplicationInstance](/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[Gestire gli account delle risorse in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts)  -  \( per creare account delle risorse ospitati online\)