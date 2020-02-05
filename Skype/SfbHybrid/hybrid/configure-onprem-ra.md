---
title: Configurare un account delle risorse in Skype for Business Server 2019
ms.author: jambirk
author: jambirk
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
description: Configurare un account delle risorse per Skype for Business Server 2019.
ms.openlocfilehash: e16f75063cfbe794ff0257cb9cccdf44065a5448
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726776"
---
# <a name="configure-resource-accounts"></a>Configurare gli account delle risorse

Le implementazioni ibride di Skype for Business Server 2019 utilizzano solo i servizi cloud forniti dal sistema telefonico per la messaggistica unificata e non si integrano con Exchange Online. In Skype for Business Server 2019 si è ora in grado di utilizzare le code di chiamata cloud e gli operatori automatici descritti in [Ecco cosa si ottiene con il sistema telefonico in Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system).

Per utilizzare un operatore automatico o una coda di chiamata di sistema telefonico con Skype for Business Server 2019, è necessario creare gli account delle risorse che fungono da endpoint dell'applicazione e possono essere assegnati numeri di telefono, quindi utilizzare l'interfaccia di amministrazione dei team online per configurare la coda di chiamata o operatore automatico. Questo account risorse può essere ospitato online (vedere [gestire gli account delle risorse in Microsoft teams](/MicrosoftTeams/manage-resource-accounts) per creare gli account delle risorse ospitati online) o in locale, come descritto in questo articolo. In genere si dispone di più nodi dell'operatore automatico del sistema telefonico o della coda di chiamata, ognuno dei quali è mappato a un account delle risorse, che può essere ospitato online o in Skype for Business Server 2019.

Se si dispone di un operatore automatico di messaggistica unificata di Exchange e di un sistema di coda di chiamata, prima di passare a Exchange Server 2019 o Exchange Online, sarà necessario registrare manualmente i dettagli come descritto di seguito e quindi implementare un sistema completamente nuovo utilizzando l'interfaccia di amministrazione dei team .

## <a name="overview"></a>Panoramica

Se l'operatore automatico del sistema telefonico o la coda di chiamata avranno bisogno di un numero di servizio, le varie dipendenze potranno essere soddisfatte nella sequenza seguente:

1. Ottenere un numero di servizio
2. Ottenere un sistema telefonico gratuito- [licenza utente virtuale](/MicrosoftTeams/teams-add-on-licensing/virtual-user) o una licenza di sistema telefonico a pagamento da utilizzare con l'account delle risorse.
3. Creare l'account della risorsa. Un operatore automatico o una coda di chiamata deve disporre di un account delle risorse associato.
4. Attendere la sincronizzazione di Active Directory tra online e in locale.
5. Assegnare la licenza del sistema telefonico all'account delle risorse.
6. Assegnare un numero di servizio all'account della risorsa.
7. Creare una coda di chiamata di sistema telefonico o un operatore automatico.
8. Associare l'account della risorsa a un operatore automatico o a una coda di chiamata: (New-CsApplicationInstanceAssociation).

Se l'operatore automatico o la coda di chiamata è annidata in un operatore automatico di primo livello, l'account di risorse associato deve disporre di un numero di telefono solo se si desidera che più punti di ingresso nella struttura di operatori automatici e code di chiamata.

Per reindirizzare le chiamate agli utenti dell'organizzazione ospitate online, è necessario che dispongano di una licenza di **sistema telefonico** e che siano abilitati per VoIP aziendale o che dispongano di piani di chiamata di Office 365. Vedere [assegnare licenze Microsoft teams](/MicrosoftTeams/assign-teams-licenses). Per abilitarli per VoIP aziendale, è possibile utilizzare Windows PowerShell. Ad esempio, eseguire:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

Se l'operatore automatico del sistema telefonico o la coda di chiamata che si sta creando sarà annidata e non avrà bisogno di un numero di telefono, il processo è:

1. Creare l'account delle risorse  
2. Attendere la sincronizzazione di Active Directory tra online e in locale
3. Creare un operatore automatico del sistema telefonico o una coda di chiamata
4. Associare l'account della risorsa a un operatore automatico del sistema telefonico o a una coda di chiamata

## <a name="create-a-resource-account-with-a-phone-number"></a>Creare un account risorsa con un numero di telefono

La creazione di un account delle risorse che utilizza un numero di telefono richiede l'esecuzione delle attività seguenti nell'ordine seguente:

1. Porta o ottenere un numero di servizio a pagamento o a pedaggio. Il numero non può essere assegnato a nessun altro account di servizi vocali o risorse.

   Prima di assegnare un numero di telefono a un account delle risorse, è necessario ottenere o trasferire numeri di servizio a pedaggio o a pedaggio esistenti. Dopo aver ottenuto i numeri > **di telefono di** > servizio a pagamento o a pedaggio, verranno visualizzati nei numeri di**telefono**dell'interfaccia di **amministrazione di Microsoft teams**e il **tipo di numero** elencato verrà elencato come **servizio gratuito**. Per ottenere i numeri di servizio, vedere [ottenere numeri di telefono di servizio](/MicrosoftTeams/getting-service-phone-numbers) o se si desidera trasferire un numero di servizio esistente, vedere [trasferire numeri di telefono a teams](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams).

   Se si è al di fuori degli Stati Uniti, non è possibile utilizzare l'interfaccia di amministrazione di Microsoft teams per ottenere i numeri di servizio. Andare a [gestire i numeri di telefono per l'organizzazione](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) , invece, per vedere come farlo dall'esterno degli Stati Uniti.

2. Acquistare una licenza di sistema telefonico. Vedere:  
   - [Sistema telefonico – licenza utente virtuale](/MicrosoftTeams/teams-add-on-licensing/virtual-user)
   - [Office 365 Enterprise E1 ed E3](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [Office 365 Enterprise E5](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [Software aziendale Office 365 Enterprise E5](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. Creare un account di risorse locale eseguendo il `New-CsHybridApplicationEndpoint` cmdlet per ogni operatore automatico del sistema telefonico o coda di chiamata, quindi assegnare un nome, un indirizzo SIP e così via.

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    Per ulteriori informazioni su questo comando, vedere [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) .

4. Optional Dopo aver creato gli account delle risorse, è possibile attendere che Active Directory venga sincronizzato tra online e in locale oppure forzare una sincronizzazione e procedere alla configurazione online dell'operatore automatico del sistema telefonico o delle code di chiamata. Per forzare una sincronizzazione, è possibile eseguire il comando seguente nel computer che esegue AAD Connect (se non lo si è già fatto, è `import-module adsync` necessario caricarlo per eseguire il comando):

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    Per ulteriori informazioni su questo comando, vedere [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) .

5. Assegnare la licenza del sistema telefonico-utente virtuale o del sistema telefonico all'account delle risorse. Vedere [assegnare licenze di Microsoft teams](/MicrosoftTeams/assign-teams-licenses) e [assegnare licenze a un utente](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).

   Se si assegna un numero di telefono a un account delle risorse, è ora possibile utilizzare il sistema telefonico senza costi-licenza utente virtuale. Questo fornisce funzionalità del sistema telefonico ai numeri di telefono a livello di organizzazione e consente di creare funzionalità di operatore automatico e coda di chiamata.


6. Assegnare il numero di servizio all'account della risorsa. Utilizzare il `Set-CsHybridApplicationEndpoint` comando per assegnare un numero di telefono (con l'opzione-LineUri) all'account della risorsa.

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    Per ulteriori informazioni su questo comando, vedere [set-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) .

    Per assegnare un numero di routing diretto o ibrido a un account delle risorse, utilizzare il cmdlet seguente:

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

L'account della risorsa avrà bisogno di un numero di telefono assegnato se verrà assegnato a un operatore automatico o una coda di chiamata di primo livello. I numeri di telefono dell'utente (abbonato) non possono essere assegnati a un account risorsa, è possibile utilizzare solo numeri di telefono a pedaggio o a pedaggio.

  È possibile assegnare un numero ibrido di routing diretto all'account delle risorse.  Per informazioni dettagliate, vedere [Plan Direct routing](/MicrosoftTeams/direct-routing-plan) .

  > [!NOTE]
  > I numeri di servizio di routing diretti assegnati agli account delle risorse per l'operatore automatico e le code di chiamata sono supportati solo per gli utenti e gli agenti di Microsoft teams.

7. Creare l'operatore automatico del sistema telefonico o la coda di chiamata. Visualizzare uno tra:

   - [Configurare un operatore automatico cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [Creare una coda di chiamata cloud](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. Associare l'account delle risorse all'operatore automatico del sistema telefonico o alla coda di chiamata scelta in precedenza.

Un esempio di implementazione di Small Business è disponibile in [Small Business example-configurare un operatore automatico](/microsoftteams/tutorial-org-aa) e un [esempio di Small Business-impostare una coda di chiamata](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq).

## <a name="create-a-resource-account-without-a-phone-number"></a>Creare un account risorsa senza un numero di telefono

In questa sezione viene descritta la creazione di un account della risorsa ospitato in locale. La creazione di un account delle risorse ospitate online è discussa in [Manage Resource Accounts in Microsoft teams](/MicrosoftTeams/manage-resource-accounts).

Questi passaggi sono necessari se si sta creando un nuovo operatore automatico del sistema telefonico o una struttura della coda di chiamata oppure la struttura di ricostruzione creata originariamente nella messaggistica unificata di Exchange.

Accedere al server front end di Skype for business ed eseguire i cmdlet di PowerShell seguenti:

1. Creare un account di risorse locale eseguendo il `New-CsHybridApplicationEndpoint` cmdlet per ogni operatore automatico del sistema telefonico o coda di chiamata, quindi assegnare un nome, un indirizzo SIP e così via.

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    Per ulteriori informazioni su questo comando, vedere [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) .

2. Optional Dopo aver creato gli account delle risorse, è possibile attendere che Active Directory venga sincronizzato tra online e in locale oppure forzare una sincronizzazione e procedere alla configurazione online dell'operatore automatico del sistema telefonico o delle code di chiamata. Per forzare una sincronizzazione, è possibile eseguire il comando seguente nel computer che esegue AAD Connect (se non lo si è già fatto, è `import-module adsync` necessario caricarlo per eseguire il comando):

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    Per ulteriori informazioni su questo comando, vedere [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) .

3. Creare l'operatore automatico del sistema telefonico o la coda di chiamata. Visualizzare uno tra:
   - [Configurare un operatore automatico cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [Creare una coda di chiamata cloud](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. Associare l'account delle risorse e l'operatore automatico del sistema telefonico o la coda di chiamata scelta in precedenza.

Un esempio di implementazione di Small Business è disponibile in [Small Business example-configurare un operatore automatico](/microsoftteams/tutorial-org-aa) e un [esempio di Small Business-impostare una coda di chiamata](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq).

## <a name="test-the-implementation"></a>Testare l'implementazione

Il modo migliore per testare l'implementazione consiste nel chiamare il numero configurato per un operatore automatico del sistema telefonico o la coda di chiamata e connettersi a uno degli agenti o dei menu. È inoltre possibile inserire rapidamente una chiamata di prova utilizzando il **pulsante test** nel riquadro azioni dell'interfaccia di amministrazione. Se si desidera apportare modifiche a un operatore automatico o una coda di chiamata di sistema telefonico, selezionarla e quindi fare clic su **modifica**nel riquadro azioni. 

> [!TIP]
> Se l'account delle risorse ha difficoltà a essere assegnato a una coda di chiamata o a un operatore automatico, vedere i [problemi noti di Microsoft teams](/MicrosoftTeams/Known-issues#phone-system) e la sezione [How to Fix My Hybrid Application instances](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521) nel Blog di Microsoft teams.

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a>Spostamento di un operatore automatico di messaggistica unificata di Exchange o coda di chiamata al sistema telefonico

La migrazione dalla messaggistica unificata di Exchange al sistema telefonico richiede la ricreazione della coda di chiamata e la struttura dell'operatore automatico, che esegue direttamente la migrazione da una a altra non è supportata. Per implementare di nuovo un set di code di chiamata e operatori automatici:

1. Ottenere un elenco di tutti gli operatori automatici di messaggistica unificata di Exchange e le code di chiamata eseguendo il comando riportato di seguito nel sistema Exchange 2013 o 2016 durante l'accesso come amministratore:

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. Per ogni coda o operatore automatico di messaggistica unificata di Exchange elencato, annotarne la posizione nella struttura, nelle impostazioni e ottenere le copie dei file audio o di sintesi vocale associati (il GUID nell'output sarà il nome di una cartella in cui sono archiviati i file). È possibile ottenere questi dettagli eseguendo il comando:

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    Per ulteriori informazioni su questo comando, vedere [Get-UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) . Un elenco completo delle opzioni che potrebbe essere necessario acquisire è nei [membri di UMAutoAttendant](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx) , ma le opzioni più importanti da tenere presenti sono le seguenti:

    - Ore lavorative
    - Orario non di ufficio
    - Lingua
    - Pianificazione festività

3. Creare nuovi endpoint locali come descritto in precedenza.
   Assegnare all'operatore automatico di primo livello un numero temporaneo a scopo di testing.

4. Configurare un operatore automatico del sistema telefonico o una coda di chiamata che utilizza gli endpoint come descritto in precedenza.

   Potrebbe essere utile usare gli esercizi presenti nell'esempio del tutorial intitolato [Small Business: configurare un operatore automatico](/microsoftteams/tutorial-org-aa) per creare una mappa logica delle gerarchie del sistema di messaggistica unificata di Exchange precedente.
5. Testare l'operatore automatico del sistema telefonico o la coda di chiamata.
6. Riassegnare il numero di telefono collegato alla coda di chiamata di messaggistica unificata di Exchange o all'operatore automatico all'operatore automatico del sistema telefonico corrispondente o alla coda di chiamata.  

   A questo punto, se è già stata eseguita la migrazione della segreteria telefonica di messaggistica unificata, è necessario essere in grado di eseguire la migrazione a Exchange Server 2019.

## <a name="see-also"></a>Vedere anche

[Creare una coda di chiamata cloud](/MicrosoftTeams/create-a-phone-system-call-queue)

[Che cosa sono gli operatori automatici cloud?](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[Configurare un operatore automatico cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[Pianificare gli operatori automatici del cloud](plan-cloud-auto-attendant.md)

[Pianificare le code di chiamata cloud](plan-call-queue.md)

[Pianificare il servizio di segreteria cloud per gli utenti locali](plan-cloud-voicemail.md)

[New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[Gestire gli account delle risorse in Microsoft teams](/MicrosoftTeams/manage-resource-accounts) - \(per creare gli account delle risorse ospitati online\)
